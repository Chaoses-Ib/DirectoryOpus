# Recent
**Recent** 内部命令可用于：

- 显示 [Recent 文件夹](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.zh.md) 的动态列表
- 过滤 Recent 以仅显示某个路径下的文件夹
- 清除 Recent 列表

**命令参数**：

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*（无参数）*</td><td>
-</td><td>
-</td><td>

显示 [最近访问的文件夹](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.zh.md) 的动态生成列表——你可以通过从该列表中选择该文件夹以导航到该文件夹。作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。

此命令的某些参数可以修改动态列表的外观和行为。

*示例：* `Recent`
</td></tr><tr><td>
CLEAR</td><td>
/S</td><td>

*（无值）*</td><td>

清除最近文件夹列表。

*示例：* `Recent CLEAR`
</td></tr><tr><td>
COPY</td><td>
/O</td><td>

\<复制命令参数\></td><td>

从 Recent 列表中选择文件夹会触发包含指定参数的 **复制** 命令。例如，你可以拥有一个 **复制** 最近列表的下拉列表和一个 **移动** 最近列表的下拉列表，使用不同的参数。请注意，如果指定了多个 **复制** 命令参数，则必须用引号将它们括起来。

*示例：* `Recent COPY`  
*示例：* `Recent COPY MOVE`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*（无值）*</td><td>

与生成项目列表的命令同时使用时（参见 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表开头添加一个小标题。当列表为空时，标题将隐藏。标题仅针对在按钮本身的同一级别可能生成多个项目的命令有效。

当 **HEADING** 单独使用时，而不指定文本值，则使用主按钮的标签文本作为标题。

*示例：* `Recent HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果你希望标题文本与按钮的标签不同，则可以指定标题文本。

*示例：* `Recent HEADING="Recent Paths"`
</td></tr><tr><td>
KEYARGS</td><td>
/K/M</td><td>

*\<限定符：参数\> ...*</td><td>

在显示 Recent 列表时，此参数让你可以在按住限定符键时为列表中的项目分配不同的行为。这是一个多值参数——对于列出的每个限定符键组合，你可以定义当选择列表中的项目时要使用的一组单独的参数。

例如，你可以将 Recent 菜单配置为在默认情况下在新标签页中打开文件夹，但在按住 <kbd>Ctrl</kbd> 键时在新文件窗口中打开文件夹。

值的限定符部分由一个或多个表示限定符键的关键词组成——**ctrl**、**shift** 和 **alt**。它们可以组合，例如 **ctrlshift** 表示必须同时按住 <kbd>Ctrl</kbd> 和 <kbd>Shift</kbd> 键。你还可以使用关键词 **none** 来指示在没有按住限定符时应用的参数。

你还可以将 **复制** 命令分配给特定的键组合；然后，使用适当的键按住从 Recent 列表中选择一个项目，之后会将选定的文件复制（或移动）到 Recent 位置。

*示例：* `Recent KEYARGS "ctrl:NEW" "shift:Copy MOVE" "none:NEWTAB=findexisting"`
</td></tr><tr><td>
MULTIFUNC</td><td>
/O</td><td>

*（无值）*</td><td>

生成的最近文件夹列表将是 [多功能按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.zh.md)（三按钮按钮）——用鼠标左键单击它们将起作用如同 **OPENINLEFT** 被设置了一样，右键会起作用如同 **OPENINRIGHT** 被设置了一样，而鼠标中键将起作用如同 **NEW** 被设置了一样。

*示例：* `Recent MULTIFUNC`
</td></tr><tr><td>
</td><td>
</td><td>

**tabs**</td><td>

与上述类似，除了左右鼠标按钮功能将在文件窗口的相应侧打开一个新标签页。你可以使用 **NEWTAB** 参数控制新标签页的打开方式。

*示例：* `Recent MULTIFUNC=tabs`
</td></tr><tr><td>
NAMESONLY</td><td>
/S</td><td>

*（无值）*</td><td>

列表中的每个项目将仅显示其各自文件夹的名称，而不是完整路径。完整路径将以工具提示的形式显示。

*示例：* `Recent NAMESONLY`
</td></tr><tr><td>
NEW</td><td>
/S</td><td>

*（无值）*</td><td>

从该命令生成的列表中选择的 Recent 文件夹将在新文件窗口中打开，而不是当前文件窗口中。

*示例：* `Recent NEW`
</td></tr><tr><td>
NEWTAB</td><td>
/O</td><td>

*（无值）*</td><td>

从该命令生成的列表中选择的 Recent 文件夹将在 [新标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md) 中打开。

*示例：* `Recent NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**deflister**</td><td>

如果不存在文件窗口，则将使用新标签页打开默认文件窗口。如果存在文件窗口，则文件夹将在现有文件窗口中的新标签页中正常打开。

*示例：* `Recent NEWTAB=deflister`
</td></tr><tr><td>
</td><td>
</td><td>

**findexisting**</td><td>

在打开新标签页之前，在现有标签页中查找文件夹。如果找到，则将现有标签页置于顶部；否则，将打开新标签页。首先检查活动标签页，如果活动标签页已经显示选定的路径，则不会发生任何事情。

*示例：* `Recent NEWTAB=findexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**findinactive**</td><td>

与 **findexisting** 类似，但如果活动标签页已经具有选定的路径，则将打开新标签页。适用于用于切换到现有标签页的按钮，以在需要时减少混乱，同时保留打开同一文件夹的第二个标签页的能力。

*示例：* `Recent NEWTAB=findinactive`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

从列表中选择的 Recent 文件夹打开的新标签页不会置于顶部。

*示例：* `Recent NEWTAB=nofocus OPENINDUAL`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

如果在现有标签页中找到文件夹，请将该标签页置于顶部（仅与 **findexisting** 一起使用）。

*示例：* `Recent NEWTAB=findexisting,tofront`
</td></tr><tr><td>
NOLABEL</td><td>
/S</td><td>

*（无值）*</td><td>

此命令显示的 Recent 列表不会显示任何文件夹标签。

*示例：* `Recent NOLABEL`
</td></tr><tr><td>
OPENINDEST</td><td>
/S</td><td>

*（无值）*</td><td>

从列表中选择的 Recent 文件夹将在目标文件列表或文件窗口中打开。

*示例：* `Recent OPENINDEST`
</td></tr><tr><td>
OPENINDUAL</td><td>
/S</td><td>

*（无值）*</td><td>

从列表中选择的 Recent 文件夹将在双栏文件窗口的另一个文件列表中打开。如果文件窗口尚未处于该模式，则将文件窗口设置为双栏模式。

*示例：* `Recent OPENINDUAL`
| 参数 | 类型 | 值 | 描述 |
|---|---|---|---|
| OPENINLEFT | /S | *(无值)* | 最近的文件夹将在双栏文件窗口的左侧（或顶部）显示中打开。
| *示例：* | `Recent KEYARGS none:OPENINLEFT ctrl:OPENINRIGHT` | |
| OPENINRIGHT | /S | *(无值)* | 最近的文件夹将在双栏文件窗口的右侧（或底部）显示中打开。
| *示例：* | `Recent NEWTAB OPENINRIGHT` | |
| PATH | | *\<path\>* | 将显示的最近列表过滤为只显示与指定路径匹配或低于指定路径的文件夹。这是 **Recent** 命令的默认参数，因此无需指定 **PATH** 关键字。如果路径中包含空格，请确保用引号将其引起来。
| |  | `Recent C:\\` |
| SHOWICONS | /S | *(无值)* | 此命令显示的最近列表将显示其中的项目的图标。请注意，包含 **Recent** 命令的按钮也必须打开其 **显示图像** 选项。
| *示例：* | `Recent SHOWICONS` | |
| USEQUALKEYS | /S | *(无值)* | 激活主限定符键的预配置行为 - **Control** 将在双栏中打开最近的文件夹，**Shift** 在新的文件窗口中打开，**Alt** 在新的标签页中打开。
| 等同于 | `Recent KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB` | |
| *示例：* | `Recent USEQUALKEYS` | |