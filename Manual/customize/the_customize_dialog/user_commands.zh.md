一个用户命令是您自己创建的已定义命令。实际上，这就像在工具栏上创建一个带有您自己的功能的按钮，但它不是工具栏上的按钮，而是命令列表中的命令，其他按钮或菜单可以使用它们，就像[内部命令](/Manual/reference/command_reference/README.zh.md)一样。

使用工具栏创建和管理用户命令。

### 编辑用户命令

![](/Manual/images/media/13/user_command.png)

编辑用户命令类似于[编辑普通工具栏按钮](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md)，尽管有一些针对用户命令的特定字段：

- **名称**：这是命令的原始名称 - 这是您需要使用的名称才能从按钮和菜单运行该命令。
- **标签**：这是命令的默认标签。如果您从*命令*标签页拖动您的命令并将其放到工具栏上，创建的按钮将以此作为其标签（当然可以编辑）。
- **描述**：当您从*命令*标签页拖动命令时，这将变为按钮的默认工具提示。
- **模板**：这指定了命令的*参数模板* - 更多详细信息，请参阅以下内容。
- **从命令菜单中隐藏**：该命令将不会显示在下拉命令列表中。这允许您创建用户命令，您仍然可以在按钮和热键（或者例如在配置页面上，例如[文件夹树选择事件](/Manual/preferences/preferences_categories/folder_tree/selection_events.zh.md)）中使用它们，但它们不会弄乱命令列表。

### 参数模板

如果您想将参数传递给您的用户命令，您需要为它提供一个参数模板。这使用与内部 Opus 命令 [相同的语法](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md)。

在上面的示例中，我们只想要一个字符串值。已在模板字段中为参数指定了 `EXT` 名称。这不是参数的*值*（在某物使用此用户命令之前，它并不存在），而是参数的*名称*。

用户命令 `Select *.&EXT&` 的功能调用内部 `Select` 命令，并向其传递一个通配符字符串，该字符串由提供的 `EXT` 参数构建。参数名称在函数定义中提供，并用 &（& 字符）包围，这表示 Opus 将该参数的值插入命令行。

您可以如下所示从工具栏按钮使用这个示例命令：

|               |                                                                 |
|---------------|-----------------------------------------------------------------|
| 命令行: | `Select_Files_Of_Type txt` |
| 运行:         | `Select *.txt`             |

### 更复杂的模板

在上面的示例中，`EXT` 是一个字符串参数，因此提供的值会原样传递给用户命令，但对于布尔选项，行为不同。例如，考虑以下用户命令：

|           |                                                                                  |
|-----------|----------------------------------------------------------------------------------|
| 名称:     | `ExampleCmd`                                |
| 模板: | `EXAMPLE1/S,EXAMPLE2/O`                     |
| 函数: | `C:\DummyProgram.exe &EXAMPLE1& &EXAMPLE2&` |

`ExampleCmd` 用户命令将在调用它时运行 `C:\DummyProgram.exe` 程序。它的模板有两个布尔选项：

- `EXAMPLE1`：直开式开关参数，可以打开或关闭。
- `EXAMPLE2`：选项开关参数，可以关闭、打开或提供字符串值。

默认情况下，开关参数将在设置时插入值 `1`，在未设置时插入值 `0`。例如，以下用户命令用法将为 *DummyProgram* 生成以下命令行：

|               |                                                                |
|---------------|----------------------------------------------------------------|
| 命令行: | `ExampleCmd EXAMPLE1`     |
| 运行:         | `C:\DummyProgram.exe 1 0` |

但是，您可以使用 `&..&` 插入符来指定实际为该参数传递的字符串。例如：

|               |                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------|
| 函数:     | `C:\DummyProgram.exe &EXAMPLE1:yes:no& &EXAMPLE2:one:two&` |
| 命令行: | `ExampleCmd EXAMPLE2`                                      |
| 运行:         | `C:\DummyProgram.exe no one`                               |

对于选项开关 (**/O**) 参数，这仅适用于参数作为开关使用的情况，而不适用于提供字符串值 - 如果提供字符串值，则会原样传递。例如：

|               |                                                                          |
|---------------|--------------------------------------------------------------------------|
| 命令行: | `ExampleCmd EXAMPLE1 EXAMPLE2=test` |
| 运行:         | `C:\DummyProgram.exe yes test`      |

您的模板还可以为选项开关指定一个值列表，然后这些值将显示在 [命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 中的下拉列表中，便于选择参数值。如果您使用此功能，您还可以指定一个默认值，如果该选项没有给出值，则会传递该默认值。考虑以下模板和两个示例用法：

|               |                                                                           |
|---------------|---------------------------------------------------------------------------|
| 名称:         | `ExampleCmd`                         |
| 模板:     | `EXAMPLE/O[<default>,one,two,three]` |
| 函数:     | `C:\DummyProgram.exe &EXAMPLE&`      |
| 命令行: | `ExampleCmd EXAMPLE`                 |
| 运行:         | `C:\DummyProgram.exe default`        |
| 命令行: | `ExampleCmd EXAMPLE=two`             |
| 运行:         | `C:\DummyProgram.exe two`            |

### 条件测试

您可以使用 [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) `@if:` 来测试用户命令参数的值，以便为用户命令引入简单的条件行为（无需求助于脚本）。例如：

    @if:&&EXAMPLE&&=one
    C:\Program1.exe
    @if:&&EXAMPLE&&=two
    C:\Program2.exe
    @if:else
    C:\DummyProgram.exe

您还可以使用 [求值器](/Manual/evaluator/README.zh.md) 中的 [Arg()](/Manual/reference/evaluator/arg.zh.md) 函数从用户命令内的求值器代码中访问命令行参数。例如：

    @if:=(Arg("NAME")=="jon")
    echo 嗨，乔恩！
@if:else
    echo 您是谁？