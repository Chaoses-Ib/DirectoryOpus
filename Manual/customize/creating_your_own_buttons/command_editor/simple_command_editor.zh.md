# 简单命令编辑器

![](/Manual/images/media/command_editor_1.png)

有关简单和高级模式通用的元素的描述，请参阅 [命令编辑器]() 页面。该页面仅介绍简单模式中独有的功能。

在上所示的命令编辑器简单模式中，**函数**字段仅为单行。在此模式下，您可以使用三种不同的方式指定函数（点击按钮后的实际功能）：

- 使用字段旁边的下拉菜单可以选择预定义命令（如自定义对话框的 [命令标签页](../../the_customize_dialog/commands.zh.md) 中所示）。从下拉菜单中选择预定义命令时，功能字段将填充基础 Opus 内部命令和参数。例如，从下拉菜单中选择“查看器窗格”将在字段中填充 **Set VIEWPANE=Toggle**，如上所示。
- 您可以直接输入 [Opus 内部命令](/Manual/reference/command_reference/internal_commands/README.zh.md) 的名称及其可选参数。
- 您可以使用浏览按钮选择要运行的外部程序（![](/Manual/images/media/browse.png)）。为了向程序 [传递所选文件的文件名](../passing_files_to_external_programs.zh.md)，您可以将各种 [外部控件代码](/Manual/reference/command_reference/external_control_codes/README.zh.md) 附加到外部程序的命令行。

![](/Manual/images/media/function_-_notepad.png)

这将启动 **Notepad**，并向其传递文件列表中第一个所选文件的文件名。

当您选择要运行的外部程序时，将启用**在下列目录中启动**和**运行**字段。

- **在下列目录中启动**：当命令运行外部程序时，此字段指定程序启动的文件夹（换句话说，即新程序的当前目录）。
- **运行**：运行外部程序时，此选项允许您指定程序窗口的显示方式。您可以从 *普通窗口*（程序自身定义窗口大小）、*最小化*（程序最小化后打开到任务栏）、*最大化*（全屏打开）和 *隐藏*（根本不显示窗口）中选择。并非所有程序都会遵循这些设置。使用 *隐藏* 时要小心，因为它可能导致程序在没有任何可见用户界面运行 - 只有在您明确知道自己想要这样做时才应使用此设置。最有用的是在启动快速运行然后退出的 DOS 脚本时使用，因为它可以隐藏 DOS 命令提示符快速“闪现”。

点击 **高级** 按钮切换到 [高级模式](advanced_command_editor.zh.md)。