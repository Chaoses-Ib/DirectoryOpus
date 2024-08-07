# 命令修饰符参考

以下是工具栏按钮和热键支持的各种 [命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md) 列表。

<table>
<thead><tr><th>
修饰符</th><th>
描述
</th></tr></thead><tbody><tr><td>
@admin</td><td>

该函数需要管理员权限。此修饰符会导致出现 UAC 提示（除非文件窗口已经处于 [管理员模式](/Manual/file_operations/uac_and_administrator_mode.zh.md)），并且此函数运行的任何外部程序都将被提升。

如果单独使用，此修饰符会影响整个函数。它也可以用来提升特定命令而不是整个按钮。

|                            |                                                                    |
|----------------------------|--------------------------------------------------------------------|
| **@admin**                 | *提升整个函数*                                      |
| **@admin:notepad.exe {f}** | *仅提升记事本*                                            |
| **@admin:no**              | *禁用此函数中任何后续命令的 UAC 提示*                  |
| **@admin:yes**             | *重新启用后续命令的 UAC 提示*                         |
</td></tr><tr><td>
@async</td><td>

此修饰符后的命令将异步运行 - Opus 不会等待它退出，然后才运行函数中的下一个命令（或在为下一个选定文件再次运行此命令之前）。

默认行为是，由单个命令组成的函数会为每个选定文件异步运行该命令；由多个命令组成的函数会同步运行每个命令。可以在配置中的 **[杂项 / 高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上使用 **function_default_async** 选项更改默认行为，或者使用此修饰符按命令覆盖默认行为。

|                            |                               |
|----------------------------|-------------------------------|
| **@async:notepad.exe {f}** | *异步运行记事本* |
</td></tr><tr><td>
@codepage</td><td>

更改 [MS-DOS 批处理命令](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md) 的代码页。如果未指定，默认代码页为 1252 ([Windows-1252](http://en.wikipedia.org/wiki/Windows-1252))。

|                    |                                    |
|--------------------|------------------------------------|
| **@codepage:1258** | *将代码页设置为越南语* |
</td></tr><tr><td>
@confirm</td><td>

显示确认对话框。如果用户单击“取消”按钮，则函数在此处中止。

此修饰符的模板为：**@confirm:***\<message\>***\|***\<positive text\>***\|***\<negative text\>*

*\<message\>* 是在对话框中显示的文本，*\<positive text\>* 是在“确定”按钮上显示的文本，而 *\<negative text\>* 是在“取消”按钮上显示的文本。这三个字符串都是可选的 - 如果未提供，将使用默认字符串。如果您提供 *\<positive text\>* 但不提供 *\<negative text\>*，则对话框将有一个“确定”按钮，但根本没有“取消”按钮。

您可以使用特殊代码 **\n** 在消息文本中包含换行符（如果您需要在文本中包含文字 **\n** 序列，则必须转义 **\\** 字符，例如 **\\n**）。

|                                          |                                                          |
|------------------------------------------|----------------------------------------------------------|
| **@confirm:Really copy files?**          | *使用“确定”和“取消”按钮的默认文本*                 |
| **@confirm:Really proceed?\|Oui!\|Non!** | *为两个按钮指定自定义文本*                             |
| **@confirm:All finished\|Acknowledged**  | *“确定”按钮的自定义文本；根本没有“取消”按钮*       |
</td></tr><tr><td>
@ctx</td><td>

允许您使用 [求值器](/Manual/evaluator/README.zh.md) 定义一个 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。举个简单的例子，

    @ctx:=return "Go DRIVEBUTTONS";

这使用求值器返回一个简单的字符串；从功能上讲，这与在工具栏按钮上简单地放置 **Go DRIVEBUTTONS** 命令没有什么不同。

作为更复杂的示例，默认的 *收藏栏* 工具栏使用 **@ctx** 来构建显示的收藏夹列表，方法是使用求值器使用收藏栏分支的当前本地化名称构建命令行：

    @ctx:=return "Favorites SHOWICONS USEQUALKEYS BRANCH=""" + LanguageStr("FavoritesBar") + """;

这使用求值器 **LanguageStr()** 函数检索已知字符串的翻译名称，并使用 **Favorites** 命令构建一个命令行来显示收藏夹树的该分支。
</td></tr><tr><td>
@dirsonly</td><td>

该函数将仅对选定的文件夹进行操作，忽略任何文件。

|               |                               |
|---------------|-------------------------------|
| **@dirsonly** | *仅对目录进行操作* |
</td></tr><tr><td>
@disableif</td><td>

如果命令子句测试为假，则按钮将被禁用。这类似于下面描述的 **@if** 修饰符提供的条件测试。

|                                 |                                                                   |
|---------------------------------|-------------------------------------------------------------------|
| **@disableif:Set DUAL=toggle**  | *如果文件窗口处于双栏模式，则按钮将被禁用*           |
| **@disableif:!Set DUAL=toggle** | *如果文件窗口不处于双栏模式，则按钮将被禁用*         |
</td></tr><tr><td>

@disableifpath  
@disableifpathr</td><td>

如果当前源路径与指定模式匹配，则按钮将被禁用。您可以提供要测试的绝对路径，或提供通配符模式（对 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 使用 **@disableifpath**，对 [正则表达式](../wildcard_reference/regular_expression_syntax.zh.md) 使用 **@disableifpathr**）。您也可以使用关键字 **shell** 来测试托管的 shell 命名空间扩展（虚拟文件夹）。

|                                 |                                                                     |
|---------------------------------|---------------------------------------------------------------------|
| **@disableifpathr:^C:\\**       | *如果源路径在 C: 驱动器上，则禁用命令*                       |
| **@disableifpath:!\*\Work\\**\* | *除非源路径在名为 **Work** 的文件夹下，否则禁用命令*    |

路径可以使用别名、环境变量、{apppath} 代码等，但仅限于使用通配符（而不是正则表达式）：

|                                           |                                                                   |
|-------------------------------------------|-------------------------------------------------------------------|
| **@disableifpath:!/desktop**              | *除非在桌面文件夹中，否则禁用命令*                            |
| **@disableifpath:!%SystemRoot%\System32** | *除非在 **C:\Windows\System32** 中（在典型系统上），否则禁用命令* |
| **@disableifpath:{apppath\|dopus.exe}**   | *如果在安装 Opus 的文件夹中，则禁用命令*                 |
| **@disableifpath:shell**                  | *如果在托管的虚拟文件夹中，则禁用命令*                           |
</td></tr><tr><td>
@disablenosel</td><td>

当没有选择任何文件或文件夹时，或可选地，当没有选择特定类型的文件时，命令将被禁用。这对于某些标准命令是自动执行的，并且该修饰符使您可以让您自己的命令以类似的方式运行。这类似于 **@hidenosel**。

|                         |                                               |
|-------------------------|-----------------------------------------------|
| **@disablenosel**       | *当没有选择任何内容时，禁用按钮*         |
| **@disablenosel:files** | *当没有选择任何文件时，禁用按钮*       |
| **@disablenosel:dirs**  | *当没有选择任何文件夹时，禁用按钮*     |

对于 lister 工具栏，您可以使用 **minfiles**、**maxfiles** 和 **numfiles** 关键字来指定按钮要启用必须选择的最小、最大或确切文件数量。类似地，**mindirs**、**maxdirs** 和 **numdirs** 可以限制所选文件夹的数量。

|                                       |                                                        |
|---------------------------------------|--------------------------------------------------------|
| **@disablenosel:numfiles=2**          | *除非选择恰好 2 个文件，否则禁用按钮*           |
| **@disablenosel:maxfiles=5**          | *除非选择 5 个或更少的个文件，否则禁用按钮*      |
| **@disablenosel:mindirs=3,maxdirs=5** | *除非选择 3、4 或 5 个文件夹，否则禁用按钮*   |

使用 **type** 关键字，您可以配置一个按钮，除非至少选择一个名称与提供的通配符模式匹配的文件，否则该按钮将被禁用。（不需要所有选定文件都与模式匹配；只需要一个。）您也可以将此与 **dirs** 结合使用，以创建一个在选择文件夹或选择特定类型的文件时有效的按钮。如果使用 **type**，它必须是行中的最后一项，因为 **=** 之后的所有内容都将被视为模式的一部分（允许模式包含在其它情况下会被误认为其它关键字和参数的内容）。

|                                    |                                                                             |
|------------------------------------|-----------------------------------------------------------------------------|
| **@disablenosel:type=\*.jpg**      | *当没有选择以“.jpg”结尾的文件时，禁用按钮*                     |
| **@disablenosel:type=old**         | *当没有选择以“old”开头的文件时，禁用按钮*                     |
| **@disablenosel:dirs,type=\*.png** | *除非选择任何文件夹，或任何以“.png”结尾的文件，否则禁用按钮* |

您还可以使用 **!** 字符来否定测试。它必须是 **:** 之后的第一项。例如，

|                                |                                                           |
|--------------------------------|-----------------------------------------------------------|
| **@disablenosel:!type=\*.jpg** | *如果选择以“.jpg”结尾的文件，则禁用按钮*            |
</td></tr><tr><td>
@enableif</td><td>

如果命令子句测试为真，则按钮将被启用。这类似于下面描述的 **@if** 修饰符提供的条件测试。

|                                |                                                                  |
|--------------------------------|------------------------------------------------------------------|
| **@enableif:Set DUAL=toggle**  | *如果文件窗口处于双栏模式，则按钮将被启用*           |
| **@enableif:!Set DUAL=toggle** | *如果文件窗口不处于双栏模式，则按钮将被启用*         |
</td></tr><tr><td>

@enableifpath  
@enableifpathr</td><td>

如果当前源路径与指定模式匹配，则按钮将被启用。您可以提供要测试的绝对路径，或提供通配符模式（对 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 使用 **@enableifpath**，对 [正则表达式](../wildcard_reference/regular_expression_syntax.zh.md) 使用 **@enableifpathr**）。您也可以使用关键字 **shell** 来测试托管的 shell 命名空间扩展（虚拟文件夹）。

|                                |                                                                    |
|--------------------------------|--------------------------------------------------------------------|
| **@enableifpathr:^C:\\**       | *如果源路径在 C: 驱动器上，则启用命令*                       |
| **@enableifpath:!\*\Work\\**\* | *除非源路径在名为 **Work** 的文件夹下，否则启用命令*    |

路径可以使用别名、环境变量、{apppath} 代码等，但仅限于使用通配符（而不是正则表达式）：

|                                          |                                                                  |
|------------------------------------------|------------------------------------------------------------------|
| **@enableifpath:!/desktop**              | *除非在桌面文件夹中，否则启用命令*                            |
| **@enableifpath:!%SystemRoot%\System32** | *除非在 **C:\Windows\System32** 中（在典型系统上），否则启用命令* |
| **@enableifpath:{apppath\|dopus.exe}**   | *如果在安装 Opus 的文件夹中，则启用命令*                 |
| **@enableifpath:shell**                  | *如果在托管的虚拟文件夹中，则启用命令*                           |
</td></tr><tr><td>

@eval  
@evalalways</td><td>

在动态测试中运行 [求值器](/Manual/evaluator/README.zh.md) 代码，并可选地在命令本身中运行代码。通常，您会使用此代码来设置求值器变量，这些变量可在命令中的后续行中使用。

- `@eval:` 之后的代码仅在动态更新按钮的标签、可见性和启用/禁用状态时运行。它不会在单击按钮时运行。
- `@evalalways:` 之后的代码也会在单击按钮时运行。这使您可以设置在执行命令时使用的变量，例如，在更新其标签时也使用这些变量。

在此示例中，`type` 值在顶行中初始化一次，然后在后续行中多次引用。

    @eval:type = PathType(source);
    fIsFileSystem = (type == "shell" || type == "filesys")
    @showif:=fIsFileSystem
    @label:fIsFileSystem ? ("Open " + FilePart(DisplayName(source)) + " in资源管理器") : ("Disabled (" + type + ")")
</td></tr><tr><td>
@externalonly</td><td>

忽略函数中指定的任何 Opus [内部命令](internal_commands/README.zh.md)，并将所有命令视为外部命令。这使您能够使用诸如 **copy** 之类的命令配置 MS-DOS 批处理函数，这些命令通常会被内部命令集覆盖。

|                   |                          |
|-------------------|--------------------------|
| **@externalonly** | *仅外部命令* |
</td></tr><tr><td>
@filesfromdroponly</td><td>

仅通过拖放接受文件和文件夹。具有此修饰符的按钮将忽略文件窗口中任何选定的文件或文件夹 - 仅将拖放到按钮上的文件将由其中的命令使用。

|                        |                                       |
|------------------------|---------------------------------------|
| **@filesfromdroponly** | *仅通过拖放接受文件* |
</td></tr><tr><td>
@filesonly</td><td>

该函数将仅对选定的文件进行操作，忽略任何文件夹。

|                |                         |
|----------------|-------------------------|
| **@filesonly** | *仅对文件进行操作* |
</td></tr><tr><td>
@firstfileonly</td><td>

该函数将仅对第一个选定的文件进行操作，而不管选择了多少项或拖放到按钮上。

|                    |                                           |
|--------------------|-------------------------------------------|
| **@firstfileonly** | *仅对第一个选定的文件进行操作* |
</td></tr><tr><td>
@functype</td><td>

此指令仅在 [嵌入函数](/Manual/customize/creating_your_own_buttons/embedded_functions.zh.md) 中使用。它允许您指定嵌入函数的类型（如果未指定，则嵌入函数被假定为标准函数 - Opus 或外部命令）。例如，以下命令将在新的文件窗口的上下文中运行一个嵌入式脚本函数，并打开一个新的文件窗口：

    Go NEW
    [
    @functype:script
    @script:vbscript
    ' script function here
    ]

|                      |                                                     |
|----------------------|-----------------------------------------------------|
| **@functype:script** | *嵌入函数是一个脚本*                 |
| **@functype:msdos**  | *嵌入函数是一个 MS-DOS 批处理函数* |
</td></tr><tr><td>
@hideblock</td><td>

**@hideblock** 修饰符允许您使用各种其它修饰符来隐藏或显示多个按钮，而无需在每个按钮中重复测试。

在按钮上使用 **@hideblock:begin** 来开始块，以及任何其它适当的修饰符。块中的按钮将根据第一个按钮的状态进行隐藏或显示。例如，

    @hideif:!Set VIEW=Thumbnails
    @hideblock:begin

此按钮根据当前视图开始一个隐藏/显示块。如果当前视图处于缩略图模式，则按钮将可见 - 否则它们将被隐藏。

在另一个按钮上使用 **@hideblock:end** 来结束块。开始和结束之间的所有按钮将作为一个整体进行隐藏或显示。请注意，开始和结束按钮永远不会在自定义模式之外显示。

|                      |                      |
|----------------------|----------------------|
| **@hideblock:begin** | *开始一个隐藏块* |
| **@hideblock:end**   | *结束一个隐藏块*   |
</td></tr><tr><td>
@hideif</td><td>

如果命令子句测试为假，则按钮将被隐藏。这类似于下面描述的 **@if** 修饰符提供的条件测试。

|                              |                                                                   |
|------------------------------|-------------------------------------------------------------------|
| **@hideif:Set DUAL=toggle**  | *如果文件窗口处于双栏模式，则按钮将被隐藏*           |
| **@hideif:!Set DUAL=toggle** | *如果文件窗口不处于双栏模式，则按钮将被隐藏*         |
</td></tr><tr><td>

@hideifpath  
@hideifpathr</td><td>

如果当前源路径与指定模式不匹配，则按钮将被隐藏。您可以提供要测试的绝对路径，或提供通配符模式（对 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 使用 **@hideifpath**，对 [正则表达式](../wildcard_reference/regular_expression_syntax.zh.md) 使用 **@hideifpathr**）。

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@hideifpathr:^C:\\**       | *如果源路径在 C: 驱动器上，则隐藏命令*                       |
| **@hideifpath:!\*\Work\\**\* | *除非源路径在名为 **Work** 的文件夹下，否则隐藏命令*    |

路径可以使用别名、环境变量、{apppath} 代码等，但仅限于使用通配符（而不是正则表达式）：

|                                        |                                                                |
|----------------------------------------|----------------------------------------------------------------|
| **@hideifpath:!/desktop**              | *除非在桌面文件夹中，否则隐藏命令*                            |
| **@hideifpath:!%SystemRoot%\System32** | *除非在 **C:\Windows\System32** 中（在典型系统上），否则隐藏命令* |
| **@hideifpath:{apppath\|dopus.exe}**   | *如果在安装 Opus 的文件夹中，则隐藏命令*                 |
</td></tr><tr><td>
@hidenosel</td><td>

当没有选择任何文件或文件夹时，或可选地，当没有选择特定类型的文件时，按钮将被隐藏。这类似于 **@disablenosel**。

|                      |                                            |
|----------------------|--------------------------------------------|
| **@hidenosel**       | *当没有选择任何内容时，隐藏按钮*         |
| **@hidenosel:files** | *当没有选择任何文件时，隐藏按钮*       |
| **@hidenosel:dirs**  | *当没有选择任何文件夹时，隐藏按钮*     |

对于 lister 工具栏，您可以使用 **minfiles**、**maxfiles** 和 **numfiles** 关键字来指定按钮要可见必须选择的最小、最大或确切文件数量。类似地，**mindirs**、**maxdirs** 和 **numdirs** 可以限制所选文件夹的数量。

|                                    |                                                     |
|------------------------------------|-----------------------------------------------------|
| **@hidenosel:numfiles=2**          | *除非选择恰好 2 个文件，否则隐藏按钮*           |
| **@hidenosel:maxfiles=5**          | *除非选择 5 个或更少的个文件，否则隐藏按钮*      |
| **@hidenosel:mindirs=3,maxdirs=5** | *除非选择 3、4 或 5 个文件夹，否则隐藏按钮*   |

使用 **type** 关键字，您可以配置一个按钮，除非至少选择一个名称与提供的通配符模式匹配的文件，否则该按钮将被隐藏。（不需要所有选定文件都与模式匹配；只需要一个。）您也可以将此与 **dirs** 结合使用，以创建一个在选择文件夹或选择特定类型的文件时可见的按钮。如果使用 **type**，它必须是行中的最后一项，因为 **=** 之后的所有内容都将被视为模式的一部分（允许模式包含在其它情况下会被误认为其它关键字和参数的内容）。

|                                 |                                                                          |
|---------------------------------|--------------------------------------------------------------------------|
| **@hidenosel:type=\*.jpg**      | *当没有选择以“.jpg”结尾的文件时，隐藏按钮*                     |
| **@hidenosel:type=old**         | *当没有选择以“old”开头的文件时，隐藏按钮*                     |
| **@hidenosel:dirs,type=\*.png** | *除非选择任何文件夹，或任何以“.png”结尾的文件，否则隐藏按钮* |

您还可以使用 **!** 字符来否定测试。它必须是 **:** 之后的第一项。例如，

|                             |                                                        |
|-----------------------------|--------------------------------------------------------|
| **@hidenosel:!type=\*.jpg** | *如果选择以“.jpg”结尾的文件，则隐藏按钮*            |
</td></tr><tr><td>

@icon  
@icon!  
@iconp</td><td>

**@icon** 指令允许您创建动态更改其图标的按钮，这些图标基于命令子句的测试，通常通过 **Set** 命令（类似于 **@if** 和 **@ifset**）。默认的 *视图模式循环* 按钮使用此方法将它的图标更改为反映当前视图模式。

    Set VIEW=Cycle
    @icon:largeicons,Set VIEW=LargeIcons
    @icon:smallicons,Set VIEW=SmallIcons
    @icon:listmode,Set VIEW=List
    @icon:powermode,Set VIEW=Power
    @icon:thumbnails,Set VIEW=Thumbnails
    @icon:tile,Set VIEW=Tiles
    @icon:detailsmode,Set VIEW=Details

按钮中的每个 **@icon** 指令都指定要使用的图标以及要测试的命令指令。例如，如果 **Set VIEW=LargeIcons** 测试结果为真，则将在按钮上显示名为 **largeicons** 的图标。如果没有任何 **@icon** 测试匹配，则将使用按钮本身中设置的图标作为默认图像。

在三按钮按钮的特殊情况下，**@iconp:** 和 **@icon!:** 指令也可以在任何子按钮中使用来更改父级的图标。**@iconp:** 在子按钮中使用将设置父级的图标（但不会对子按钮做任何操作）。**icon!:** 在子按钮中使用将设置父级和该子按钮的图标。

如果您正在根据 **Set** 命令进行测试，则命令名称在技术上是可选的，可以省略。例如，**VIEW=LargeIcons** 本身与 **Set VIEW=LargeIcons** 相同。这种能力是为了避免破坏旧的按钮，对于新的按钮，我们建议您始终包含命令名称，以避免将来出现问题。

在命令编辑器中，您可以 **Ctrl**+单击 **@icon:** 字符串来直接选择图标。

**@icon** 可以使用 **RECYCLEBINEMPTY** 参数来测试回收站是否为空。例如，

    @icon:c:\icons\empty.png,RECYCLEBINEMPTY

使用 **@icon** 和 **RECYCLEBINEMPTY** 的工具栏按钮将在回收站状态发生变化时自动刷新自身（这使您可以拥有一个图标反映回收站状态的按钮）。
</td></tr><tr><td>

@if  
@ifset</td><td>

允许根据对各种命令的测试进行简单的条件行为。

**@if** 是一个针对任何命令的通用测试，而 **@ifset** 是一个特定的测试，它只适用于 **[Set](internal_commands/set.zh.md)** 命令条件。例如，**@ifset:DUAL=on** 等效于 **@if:Set DUAL=on**。
**@if** 实际执行的测试是求值具有指定命令的工具栏按钮是否会突出显示。例如，如果文件窗口处于双栏模式，则具有 **Set DUAL=toggle** 命令的按钮将突出显示。因此，**@if:Set DUAL=toggle** 修饰符将求值为真。

您还可以使用 **@if:enabled** 来求值工具栏按钮是否会被启用。例如，[导航锁定](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.zh.md) 仅在文件窗口处于双栏模式时才启用。因此，当文件窗口处于双栏模式时，**@if:enabled Set NAVLOCK=Toggle** 修饰符将求值为真。

您还可以测试变量是否已由 **@set** 指令设置。此外，[文件列表工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.zh.md) 上的按钮可以测试它是否绑定到左侧或右侧文件列表。

例如，您可以配置一个按钮，将文件夹读入双栏文件窗口中的右侧文件列表，或读入其它文件列表。

    @if:Set DUAL=on             // 如果 DUAL 模式已开启
    Set FOCUS=right             // 将焦点设置到右侧文件列表
    Go /mypictures OPENINRIGHT  // 将目录读入该文件列表
    @if:else                    // 否则
    Go /mypictures              // 将目录读入当前文件列表
    @if:common                  // 通用命令（始终执行）
    Set VIEW=thumbnails         // 将视图设置为缩略图模式

另一个例子是，**@ifset** 可以使用 **RECYCLEBINEMPTY** 参数来测试回收站是否为空：

    @ifset:RECYCLEBINEMPTY
    @confirm The recycle bin is empty!
    @ifset:else
    Delete EMPTYRECYCLE

条件测试也可以用在 [独立查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 中的按钮上。以下函数将通过使用 **@if** 测试当前缩放模式，在 100% 缩放和 *扩展至页面* 模式之间切换显示：

    @if:Show VIEWERCMD=zoom,reset
    Show VIEWERCMD=zoom,grow
    @if:else
    Show VIEWERCMD=zoom,reset

此修饰符的可能形式为：

|                                       |                                                                                                                                    |
|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| **@if:\<command line\>**              | *测试特定命令条件是否为真*                                                                                     |
| **@ifset:***\<Set command argument\>* | *测试特定 Set 命令条件*                                                                                        |
| **@if:enabled** *\<command\>*         | *测试命令按钮是否会被启用（而不是突出显示）*                                                              |
| **@if:\$foo**                         | *测试名为“foo”的变量是否已设置*                                                                                     |
| **@if:\$glob:bar**                    | *测试名为“bar”的全局变量是否已设置*                                                                              |
| **@if:SIDE=left**                     | *测试工具栏是否绑定到左侧文件列表*                                                                             |
| **@if:SIDE=right**                    | *测试工具栏是否绑定到右侧文件列表*                                                                            |
| **@if:&&ARG&&=value**                 | *测试 [用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md) 参数是否与给定值匹配*      |
| **@if:&&ARG&&!=value**                | *测试 [用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md) 参数是否与给定值不匹配* |
| **@if:else**                          | *如果没有任何其它匹配项，则执行“else”子句*                                                                        |
| **@if:common**                        | *始终执行的通用指令*                                                                                     |

您可以通过在条件前面添加 **!** 字符来否定条件。例如，以下四个都是等效的：

    @if:!Set DUAL=on
    @if:Set DUAL=off
    @ifset:!DUAL=on
    @ifset:DUAL=off
</td></tr><tr><td>
@ifexists</td><td>

允许根据指定的驱动器或路径是否存在进行简单的条件行为。如果使用 **wild:** 前缀，路径的最后一个组件可以包含 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md)。

|                      |                                                                                                  |
|----------------------|--------------------------------------------------------------------------------------------------|
| **@ifexists:**       | *\<drive or path\> - 测试驱动器或路径是否存在*                                               |
| **@ifexists:wild:**  | *\<drive or path\> - 测试驱动器或路径是否存在。允许在路径的最后一个组件中使用通配符* |
| **@ifexists:!**      | *\<drive or path\> - 测试驱动器或路径是否不存在*                                       |
| **@ifexists:else**   | *如果路径不存在，则执行“else”子句*                                    |
| **@ifexists:common** | *始终执行的通用指令*                                                   |
</td></tr><tr><td>
@ifsel</td><td>

允许函数根据文件或文件夹的选择执行不同的操作。可用的测试与 **@disablenosel** 修饰符相同（如上所述）。

例如，

    @ifsel:numfiles=2
    <run program that accepts exactly two files>
    @ifsel:else
    <show an error message>
</td></tr><tr><td>

@ifpath  
@ifpathr</td><td>

允许根据当前源路径进行简单的条件行为。您可以提供要测试的绝对路径，或提供通配符模式（对 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 使用 **@ifpath**，对 [正则表达式](../wildcard_reference/regular_expression_syntax.zh.md) 使用 **@ifpathr**）。

例如，您可以使用此方法在双击图像文件时打开不同的程序，具体取决于文件存储的位置。如果将以下命令添加到 **Images** [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的 *左双击* [事件](/Manual/file_types/filetype_editor/events.zh.md)，则位于网络上的图片将在双击时使用 Opus 查看器打开，而位于本地驱动器上的文件将在 Photoshop 中打开。

    @ifpath:\\*                      // 如果路径以 \\ 开头
    Show                             // 调用 Opus 查看器
    @ifpath:else                     // 否则...
    Photoshop.exe {f}                // 在 Photoshop 中打开（通常需要指定完整路径 - 这只是一个示例）

此修饰符的可能形式为：

|                                       |                                                             |
|---------------------------------------|-------------------------------------------------------------|
| **@ifpath:***\<path or wildcard\>*    | *测试路径（使用标准模式匹配）*                             |
| **@ifpathr:***\<regular expression\>* | *测试路径（使用正则表达式）*                               |
| **@ifpath:else**                      | *如果没有任何其它匹配项，则执行“else”子句*                 |
| **@ifpath:common**                    | *始终执行的通用指令*                                     |

您可以通过在条件前面添加 **!** 字符来否定条件。

示例：

|                                   |                                                                                           |
|-----------------------------------|-------------------------------------------------------------------------------------------|
| **@ifpath:C:\Program Files**      | *测试您是否在 C:\Program Files 中*                                                       |
| **@ifpath:!C:\Program Files**     | *测试您是否不在 C:\Program Files 中*                                             |
| **@ifpath:C:\Program Files\\**\*  | *测试您是否在 C:\Program Files 下面的文件夹中（不包括 Program Files 本身）* |
| **@ifpath:!C:\Program Files\\**\* | *测试您是否不在 C:\Program Files 下面的文件夹中*                                    |
</td></tr><tr><td>
@ifrunning</td><td>

允许根据指定的进程当前是否正在运行进行简单的条件行为。您可以使用通配符或（通过在模式前面添加 **regex:**）正则表达式。

|                            |                                                                  |
|----------------------------|------------------------------------------------------------------|
| **@ifrunning:notepad.exe** | *测试记事本是否正在运行*                                     |
| **@ifrunning:!note**\*     | *测试以“note”开头的进程是否未运行*                          |
| **@ifrunning:else**        | *如果进程不存在，则执行“else”子句*                         |
| **@ifrunning:common**      | *始终执行的通用指令*                                      |
</td></tr><tr><td>
@keydown</td><td>

允许根据在运行函数时是否按下了各种修饰键进行简单的条件行为。

要测试的修饰符使用一个或多个关键字（**shift**、**ctrl** 和 **alt**）来指定，这些关键字分别代表 <kbd>Shift</kbd>、<kbd>Ctrl</kbd> 和 <kbd>Alt</kbd> 键。例如，您可以配置一个按钮来选择所有文件，然后根据按下的键将它们复制、移动或创建快捷方式。

    Select ALL              // 选择所有项目（始终执行）
    @keydown:none           // 如果没有按下修饰符
    Copy                    // 将文件复制到目标
    @keydown:shift          // 否则，如果按下 Shift 键
    Copy MOVE               // 将文件移动到目标
    @keydown:ctrlshift      // 否则，如果同时按下 Ctrl 和 Shift 键
    Copy MAKELINK           // 在目标中创建快捷方式

此修饰符的可能形式为：

|                                |                                                                                                                                                                                                                   |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **@keydown:***\<qualifiers\>*  | *测试修饰键或修饰键组合*                                                                                                                                                                 |
| **@keydown:!***\<qualifiers\>* | *测试修饰键或修饰键组合是否未按下*                                                                                                                                                  |
| **@keydown:any**               | // 测试是否按下了**任何**修饰键*\| \|**@keydown:none**\|*如果未按下任何修饰键，则执行的指令*\| \|**@keydown:common**\|*始终执行的通用指令// |
</td></tr><tr><td>
@label</td><td>

TOBEDONE

如果某些内容修改了变量，或其它影响动态标签的因素，它应该通知 Opus，以便可以更新标签和工具栏布局。命令应该使用 **@toggle:update**（见下文），而脚本可以使用 [Command.UpdateToggle](/Manual/reference/scripting_reference/scripting_objects/command.zh.md) 来做到这一点。
</td></tr><tr><td>
@leavedoswindowopen</td><td>

为 [MS-DOS 批处理函数](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md) 打开的控制台窗口将在函数完成后保持打开状态。如果没有此修饰符，窗口将在函数完成后关闭，这可能难以阅读任何命令行程序的输出。
保留 DOS 窗口打开依赖于向系统命令解释器 **cmd.exe** 传递特定参数（**/K**）。如果您通过设置 **%ComSpec%** 环境变量修改了系统上的默认命令处理器，Opus 不会传递 **/K**，因为它无法知道此参数是否会被新的命令处理器理解。相反，您可以设置 **%ComSpecLeaveOpenArg%** 环境变量，它将在每次使用 **@leavedoswindowopen** 时用作 **%ComSpec%** 的替代。

|                         |                                                |
|-------------------------|------------------------------------------------|
| **@leavedoswindowopen** | *在函数完成后保留 DOS 提示符打开* |
</td></tr><tr><td>
@logusage</td><td>

指示 Windows 记录此函数打开的程序或文档的使用情况。通常这意味着任何使用的文件都将添加到最近的文档列表，并且任何启动的程序都将添加到最近的应用程序列表。

|               |                                       |
|---------------|---------------------------------------|
| **@logusage** | *记录文件和应用程序的使用情况* |
</td></tr><tr><td>
@nocall</td><td>

[MS-DOS 批处理函数](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md) 调用外部 **.bat** 文件的函数将直接运行它，而不是使用 ***call*** 语义。这意味着一旦外部 **.bat** 文件完成，控制权将不会返回到父函数。默认行为是使用 DOS **call** 指令，该指令在结束时将控制权返回到父函数。

|                              |                                                                      |
|------------------------------|----------------------------------------------------------------------|
| **@nocall:***\<batch file\>* | *调用外部批处理文件，不将控制权返回到此函数*                 |
</td></tr><tr><td>
@nodeselect</td><td>

文件和文件夹将在函数结束时保持选中状态。这使您可以在每个函数的基础上覆盖配置中的 **[文件操作 / 选项](/Manual/preferences/preferences_categories/file_operations/options.zh.md)** 页面上的 **取消选择函数中使用的文件** 选项。

|                 |                                               |
|-----------------|-----------------------------------------------|
| **@nodeselect** | *不要取消选择此函数使用的项目* |
</td></tr><tr><td>
@noexpandenv</td><td>

防止扩展函数中的任何环境变量。通常，环境变量（如 **%USERPROFILE%**）会在函数解析阶段扩展 - 此修饰符会导致变量名保持不变。

|                  |                                       |
|------------------|---------------------------------------|
| **@noexpandenv** | *不要扩展环境变量* |
</td></tr><tr><td>
@nofilenamequoting</td><td>

禁用 Opus 在使用 [外部代码](external_control_codes/README.zh.md)（如 **{filepath}**）传递包含空格的文件名称时执行的自动引号。默认情况下，Opus 会将包含嵌入空格的名称括在引号中，但有时您可能希望禁用此功能 - 一些外部程序可能不需要或不理解其命令行上的引号，而且您可能还希望在函数中提供显式引号，以防自动引号因复杂的命令结构而混乱。

|                        |                                                   |
|------------------------|---------------------------------------------------|
| **@nofilenamequoting** | *不要自动引用文件名和路径* |
</td></tr><tr><td>
@nolocalizefiles</td><td>

防止 Opus 在将非文件系统文件的路径传递给外部程序时自动下载或提取这些文件。例如，您可能希望使用 **{filepath}** 将远程 FTP 服务器上的文件的 **ftp://** 路径传递给外部程序。默认情况下，Opus 会将文件下载到临时文件，并将临时文件的名称传递给程序 - 使用此修饰符，Opus 将改为传递原始文件路径。

|                      |                                                         |
|----------------------|---------------------------------------------------------|
| **@nolocalizefiles** | *不要自动本地化（下载）远程文件* |
</td></tr><tr><td>
@noprogress</td><td>

禁用此函数的自动进度指示器显示。您应该谨慎使用此功能，因为如果没有进度指示器，就无法中止命令或监控其进度。通常，只有在想要提供和控制自己的进度指示器时，脚本函数才会使用此功能。

|                 |                                                                 |
|-----------------|-----------------------------------------------------------------|
| **@noprogress** | *不要为此函数显示自动进度对话框*                       |
</td></tr><tr><td>
@norunbatch</td><td>

当 [MS-DOS 批处理函数](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md) 结合使用内部命令和外部命令时，默认行为是 Opus 在每个内部命令处拆分函数，并执行之前的所有外部命令。例如，假设以下（相当无用的）函数：

    echo one
    Help ABOUT
    echo two
    @leavedoswindowopen

此函数的默认行为是打开一个 DOS 窗口并打印字符串“one”，然后显示 Opus **About** 对话框，然后打开另一个 DOS 窗口并打印字符串“two”。但是，如果将函数更改为以下形式：

    @norunbatch
    echo one
    Help ABOUT
    echo two
    @leavedoswindowopen

新的行为是首先显示 **About** 对话框，然后打开一个 DOS 窗口并打印字符串“one”和“two”。**@norunbatch** 修饰符会导致先执行所有 Opus 内部命令，然后执行所有外部命令。

|                 |                                                             |
|-----------------|-------------------------------------------------------------|
| **@norunbatch** | *不要因为内部命令而拆分批处理函数*                       |
</td></tr><tr><td>
@output</td><td>

将行中剩余的所有文本输出到脚本日志。对调试很有用。在命令编辑器处于 \*运行带日志记录\* 模式时，也可以查看输出。

|                           |                                       |     |
|---------------------------|---------------------------------------|-----|
| **@output** *\<message\>* | *将 \<message\> 发送到脚本日志* |     |
</td></tr><tr><td>
@perfile</td><td>

允许对每个文件运行一组命令。通常，包含多行命令的函数会对所有选定文件分别运行每个命令。

例如，

    echo 1 {file}
    echo 2 {file}

如果选择了两个文件“Apple.txt”和“Banana.txt”，这将输出：

    1 Apple.txt
    1 Banana.txt
    2 Apple.txt
    2 Banana.txt

在这些命令周围使用 **@perfile**，如下所示：

    @perfile:begin
    echo 1 {file}
    echo 2 {file}
    @perfile:end

这将输出：

    1 Apple.txt
    2 Apple.txt
    1 Banana.txt
    2 Banana.txt

使用 **@perfile:begin** 来标记每个文件块的开始，并使用 **@perfile:end** 来标记结束。
</td></tr><tr><td>
@resolvelinks</td><td>

传递给此函数中命令的快捷方式或链接将被解析为其目标。如果没有此修饰符，选定的 **.lnk** 文件将按原样传递。

|                   |                                                               |
|-------------------|---------------------------------------------------------------|
| **@resolvelinks** | *在将文件名传递给命令时解析快捷方式目标* |
</td></tr><tr><td>
@runbatch</td><td>

强制在某个点执行 MS-DOS 批处理函数。默认行为是将此类函数在函数的最后执行 - 使用此修饰符，您可以在任何行强制中断函数。例如：

    echo one
    @runbatch
    echo two
    @leavedoswindowopen

这将导致打开两个独立的 DOS 窗口，一个显示文本“one”，另一个显示“two”。如果没有 **@runbatch** 指令，这两个命令将在同一个窗口中执行。

|               |                                                            |
|---------------|------------------------------------------------------------|
| **@runbatch** | *强制在某个点执行 DOS 批处理函数*                       |
</td></tr><tr><td>
@runmode</td><td>

修改函数启动的外部程序的“运行”状态 - 即其主窗口的显示方式。这等效于 [简单命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/simple_command_editor.zh.md) 上的 **运行** 下拉列表。并非所有程序都支持此设置，因此您需要在一定程度上进行试用。只有在确定您在做什么的情况下，才应将模式设置为 **hide** - 它最适合在运行 DOS 程序时隐藏 DOS 窗口的短暂闪现。

|                   |                                      |
|-------------------|--------------------------------------|
| **@runmode:min**  | *最小化程序的主窗口*                 |
| **@runmode:max**  | *最大化程序的主窗口*                 |
| **@runmode:hide** | *隐藏程序的主窗口*                     |
</td></tr><tr><td>
@runonce</td><td>

强制修饰符后的命令在每个函数中只运行一次，而不是每个文件运行一次。

|                            |                                               |
|----------------------------|-----------------------------------------------|
| **@runonce:***\<command\>* | *指定的命令将只运行一次*                    |
</td></tr><tr><td>
@script</td><td>

指定用于脚本的脚本语言。这主要用于 [嵌入式重命名脚本](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.zh.md)，因为否则脚本语言将通过脚本编辑器顶部的下拉列表选择。**@script** 修饰符后面必须跟一个关键字，该关键字指定脚本语言（或者在 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的情况下，插件本身的文件扩展名指定语言）。

例如，

    Rename PATTERN * TO *
    @script:vbscript
    Function ....

|                            |                                                   |
|----------------------------|---------------------------------------------------|
| **@script:***\<language\>* | *为重命名命令指定脚本语言*                     |
</td></tr><tr><td>
@set</td><td>

设置一个命名变量的值，该变量可以在函数中剩余的命令中使用。您可以使用 **{\$}** [控制代码](external_control_codes/codes_for_clipboard_and_variables.zh.md) 将变量的值传递给内部命令和外部命令。变量在值由 **{dlgstring}** 代码定义的情况下最有用。例如，

    @set dir={dlgstring|Enter new folder name to copy files to}
    CreateFolder ".\{$dir}"
    Copy TO ".\{$dir}"

通常，变量不会从函数的一次调用持续到下一次调用，并且您无法从一个函数引用另一个函数中设置的变量。但是，可以通过在变量名称前面添加一个特殊的范围标记来实现这一点，该标记确定变量将在哪个范围内存在。

|                      |                                                                |
|----------------------|----------------------------------------------------------------|
| **src:***\<name\>*   | *变量将限定在源文件夹标签页范围内*             |
| **dst:***\<name\>*   | *变量将限定在目标文件夹标签页范围内*        |
| **left:***\<name\>*  | *变量将限定在左侧文件夹标签页范围内*               |
| **right:***\<name\>* | *变量将限定在右侧文件夹标签页范围内*              |
| **tab:***\<name\>*   | *变量将限定在活动文件夹标签页范围内（见下文）* |
| **lst:***\<name\>*   | *变量将限定在文件窗口（整个窗口）范围内*     |
| **glob:***\<name\>*  | *变量将限定在全局范围内*                             |

**src:** 和 **tab:** 范围通常指向命令中的同一个文件夹标签页。（**tab:** 范围的引入是为了使 [使用变量的 status bar 代码](../status_bar_codes/other_codes.zh.md) 可以引用 status bar 所在的一侧，而无需担心它是否是源、目标、左侧还是右侧。为了保持一致性，它在命令中得到支持。）

您还可以标记变量以保存在磁盘上 - 它们的值将从一个 Opus 会话记住到下一个会话。要做到这一点，只需在范围标记中添加一个感叹号（!）。例如，

|                                     |                                                                      |
|-------------------------------------|----------------------------------------------------------------------|
| **glob!:***\<name\>*                | *引用一个具有全局范围并将保存在磁盘上的变量*                 |
| **@set** *\<name\>***=***\<value\>* | *将命名变量设置为指定的值*                                 |
| **@set** *\<name\>*                 | *删除命名变量*                                                    |

如果您有 按钮或 status bar 代码对变量更改做出反应，您可能需要运行特殊的 **@toggle:update** 命令以使它们在更改变量后更新外观。请参见下面的 **@toggle** 文档。
</td></tr><tr><td>
@showif</td><td>

如果命令子句测试为假，则按钮将被显示。这类似于 **@if** 修饰符提供的条件测试。

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@showif:Set DUAL=toggle**  | *如果文件窗口处于双栏模式，则按钮将被显示*           |
| **@showif:!Set DUAL=toggle** | *如果文件窗口不处于双栏模式，则按钮将被显示*         |
</td></tr><tr><td>
@sendkey</td><td>

向系统发送指定的按键。该键将被路由到当前具有焦点的窗口。例如，`@sendkey:win+v` 向系统发送 <kbd>Win</kbd>+<kbd>V</kbd> 键，这将打开 Windows 剪贴板查看器。

支持的修饰键是 `shift`、`ctrl`、`alt` 和 `win`。

除了字母和数字之外，还支持以下命名键：`backspace`、`capslock`、`delete`、`down`、`end`、`enter`、`escape`、`home`、`insert`、`left`、`numlock`、`pagedown`、`pageup`、`pause`、`printscr`、`right`、`scrlock`、`space`、`tab`、`up`。
</td></tr><tr><td>

@showifpath  
@showifpathr</td><td>

如果当前源路径与指定模式不匹配，则按钮将被显示。您可以提供要测试的绝对路径，或提供通配符模式（对 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 使用 **@showifpath**，对 [正则表达式](../wildcard_reference/regular_expression_syntax.zh.md) 使用 **@showifpathr**）。

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@showifpathr:^C:\\**       | *如果源路径在 C: 驱动器上，则显示命令*                       |
| **@showifpath:!\*\Work\\**\* | *除非源路径在名为 **Work** 的文件夹下，否则显示命令*    |

路径可以使用别名、环境变量、{apppath} 代码等，但仅限于使用通配符（而不是正则表达式）：

|                                        |                                                                |
|----------------------------------------|----------------------------------------------------------------|
| **@showifpath:!/desktop**              | *除非在桌面文件夹中，否则显示命令*                            |
| **@showifpath:!%SystemRoot%\System32** | *除非在 **C:\Windows\System32** 中（在典型系统上），否则显示命令* |
| **@showifpath:{apppath\|dopus.exe}**   | *如果在安装 Opus 的文件夹中，则显示命令*                 |
</td></tr><tr><td>
@sync</td><td>

此修饰符后的命令将同步运行 - Opus 将等待它退出，然后才运行函数中的下一个命令（或在为下一个选定文件再次运行此命令之前）。

默认行为是，由单个命令组成的函数会为每个选定文件异步运行该命令；由多个命令组成的函数会同步运行每个命令。可以在配置中的 **[杂项 / 高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上使用 **function_default_async** 选项更改默认行为，或者使用此修饰符按命令覆盖默认行为。

|                           |                              |
|---------------------------|------------------------------|
| **@sync:notepad.exe {f}** | *同步运行记事本* |
</td></tr><tr><td>
@toggle</td><td>

对于指示或更改状态的按钮（例如 **Set VIEW=details**），此修饰符允许您更改按钮 何时 显示为突出显示。

根据 按钮的显示位置，突出显示可能显示为 复选标记（例如，在纯文本菜单中），或图标或标签背景以不同的颜色或样式绘制（类似于按钮被按下时）。

以 **Set VIEW=details** 命令为例，通常情况下，当文件列表处于详细信息模式时，按钮将显示为突出显示，而在任何其它模式下则不会突出显示。**@toggle** 修饰符可以更改这一点：

|                     |                                                           |
|---------------------|-----------------------------------------------------------|
| **@toggle:invert**  | *反转工具栏按钮的通常突出显示状态*                 |
| **@toggle:disable** | *阻止按钮永远显示为突出显示*                         |

@**toggle** 修饰符还可以通过测试 命令来控制 何时 按钮 显示为 突出显示 ，类似于 **@if** 和 **@ifset** 测试命令的方式来决定要运行什么**.** 您可以使用此方法根据与按钮实际运行的命令不同或除了按钮实际运行的命令之外的命令来突出显示按钮。

例如，以下没有 **@toggle** 行的按钮将在单击时将您切换到 *Details* 模式，并且在您处于 *Details* 模式时也会显示为突出显示：

    Set VIEW=Details

当不给出 **@toggle** 时，突出显示（如果有）基于按钮中的第一个命令。

使用 **@toggle**，您可以执行诸如运行一个 **Set** 命令 并在测试另一个命令时进行操作。作为一个简单而有些人为的例子，下面的按钮在单击时切换到 *Details* 模式，但在处于增强模式时显示为突出显示：

    Set VIEW=Details
    @toggle:if Set VIEW=Power

您可以使 **@toggle** 测试除了第一个命令之外，而不是代替第一个命令， 方法是在“if”之后添加一个“&”字符：

    Set VIEW=Details
    Set COLUMNSADD=thumbnail(0,96)
    @toggle:if&Set COLUMNSTOGGLE=thumbnail

如果没有 **@toggle** 行，上面的按钮将在视图为 *Details* 时（由于命令）被突出显示，并且突出显示不会受到 *Thumbnail* 列的影响（突出显示不会考虑第二个命令）。添加了 **@toggle** 行后，按钮只有在视图设置为 *Details* 并且存在 *Thumbnail* 列时才会被突出显示。
您可以从 **@toggle** 行中省略“Set”命令名称；如果没有指定名称，它将假设您指的是 **Set** 命令。但是，这种允许是为了避免破坏旧的按钮，我们建议您在制作新的按钮时始终指定命令。

您可以通过分号分隔多个命令来一次性测试多个命令。例如，您可以省略“&”符号，并使用以下指令来测试 *Details* 模式和 *Thumbnail* 列（这将在按钮中的任何其它命令的情况下有效，甚至作为按钮中的唯一一行）：

    @toggle:if Set VIEW=Details;Set COLUMNSTOGGLE=thumbnail

您还可以使用 **Set** 子句前面的感叹号来否定测试结果。例如，要使按钮在除 Details 之外的任何模式下显示为选中状态：

    @toggle:if !Set VIEW=Details

**@toggle** 指令也可以测试变量是否存在（一个通过 **@set** 指令设置的变量）。为了使这起作用，指令必须是按钮的第一行，并且您要测试的变量必须具有标签页、文件窗口或全局范围。您可以使用此方法创建您自己的自定义切换按钮，这些按钮使用范围变量来跟踪它们的状态。例如：

    @toggle:if $glob:TestVar
    @if:$glob:TestVar
    @set glob:TestVar
    @if:else
    @set glob:TestVar=on

此按钮测试名为 *TestVar* 的全局变量是否存在。如果变量存在，按钮将显示为突出显示。单击按钮将求值 **@ifset:** 指令，并反转变量的状态：如果变量已设置，则将其删除；否则，将其设置。最终结果是一个按钮，除了在每次单击时切换变量及其可见状态之外，它不执行任何功能。（这很有用，如果变量控制其它内容，例如其它命令或脚本的行为，或者 [status bar 元素](../status_bar_codes/other_codes.zh.md) 的可见性。）

以 **@toggle:if** 开头的按钮将在按钮中使用 **@set** 时自动更新其外观（以反映变量状态的更改）。如果您在单独的按钮或热键中使用 **@set** 来更改变量，则需要使用特殊命令 **@toggle:update** 强制更新切换按钮的外观。

例如，如果您有一个按钮根据变量突出显示，但不会更改该变量：

    @toggle:if $glob:TestVar

如果您有另一个按钮更改该变量，但不根据它突出显示，那么您需要添加 **@toggle:update** 行以确保在单击第二个按钮时更新第一个按钮的突出显示：

    @if:$glob:TestVar
    @set glob:TestVar
    @if:else
    @set glob:TestVar=on
    @if:common
    @toggle:update

**@toggle:update** 命令也会强制所有 **status bars** 刷新，以防它们 [使用变量](../status_bar_codes/other_codes.zh.md) 来显示或隐藏信息。

您也可以使用 **@toggle:update** 来确保具有动态标签（通过上面的 **@label**）的按钮在更改标签所依赖的变量或其它详细信息后更新。这也确保如果标签宽度发生变化，工具栏布局也会进行调整。
</td></tr><tr><td>
@useactivelister</td><td>

该函数将作用于活动文件窗口而不是当前源文件窗口。通常情况下，它们是同一个东西，但这对于您想要让它作用于当前活动的文件窗口窗口的热键很有用，而无需先确保该文件窗口设置为源。

|                      |                                              |
|----------------------|----------------------------------------------|
| **@useactivelister** | *使用活动文件窗口而不是源 lister* |
</td></tr></tbody>
</table>