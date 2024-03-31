# 来自桌面

此处的选项使你能够在 Windows 桌面中双击以启动 Opus 或运行另一个命令。当当前没有打开窗户时，这会提供一种非常快速的访问文件窗口的方式 - 只要找到桌面上一个空白区域（上面没有图标），然后双击。

- **禁用**：选择此选项可以禁用在桌面上双击。
- **将最后激活的文件窗口带到最前面**：如果已有一个或多个文件窗口打开，则在桌面上双击将把最近一个使用过的文件窗口带到最前面。如果没有打开文件窗口，则使用默认文件窗口设置打开一个新的文件窗口。如果你使用 Windows 10 的*虚拟桌面*功能，则只考虑当前活动桌面上的窗口，除非你关闭高级**[高级](../miscellaneous/advanced_options.zh.md)**设置。
- **打开默认文件窗口**：使用[默认文件窗口](/Manual/basic_concepts/the_lister/the_default_lister.zh.md)的设置打开一个新的文件窗口。如果你打开**关闭现有的文件窗口**选项，那么在打开布局之前任何现有的文件窗口都将会被关闭 - 如果关闭，则现有的文件窗口将不受影响。
- **运行一个命令**：使你能够在双击桌面时输入要运行的命令。这可以用来执行更复杂的操作，包括运行外部程序。这必须是一个在按钮或热键上有意义的命令。你可以使用[Opus 内部命令](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md)或外部程序（使用[标准控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)将参数传递给它们）。如果你想要运行一个简单单行命令更多，你可以创建更复杂的[用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md），然后在这里指定用户命令的名称。

##### DOpusRT

当启用任何双击选项时，Opus 会启动一个名为**[DOpusRT.exe](/Manual/reference/dopusrt_reference/README.zh.md)**的小型帮助程序，它会在后台持续运行。它被添加到注册表中以在启动时自动运行，这意味着即使 Opus 自身未运行，双击桌面同样可以工作（**DOpusRT.exe** 会在双击时自动启动 Opus，如果它在未运行）。

为了捕获桌面的双击（它在另一个进程中运行 Opus），必须将“注入代码”到资源管理器中 - 如果你安装了反病毒或反间谍软件工具，你可能会发现它检测到此并抱怨。如果你发现双击桌面不起作用，请检查是否有阻止 **DOpusRT.exe** 钩入资源管理器或在启动时运行的东西。

**重新启动 DOpusRT.exe** 按钮可用于在故障排除中使用。它将尝试停止 DOpusRT.exe 的任何当前实例并启动一个新的实例。它还将告诉你整个 Opus 进程是否以提升身份运行，这可能会导致资源管理器中的消息无法到达 Opus 从而引发问题。

如果你点击了**重新启动 DOpusRT.exe**按钮，发现桌面双击开始工作，但在下次重启后又再次失败，一种可能是与在重启时 DOpusRT.exe 之后启动的另一个程序冲突。你可以使用**延迟 DOpusRT.exe**选项，使其在开始解决此类问题前等待指定秒数。所需的确切延迟将取决于导致冲突的软件。