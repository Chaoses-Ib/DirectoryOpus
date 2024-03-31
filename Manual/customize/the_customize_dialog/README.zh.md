# 自定义对话框

当你进入 [自定义](/Manual/customize/README.zh.md) 模式时，*自定义* 对话框会出现。它被划分为多个标签页。

- **[工具栏](/Manual/customize/the_customize_dialog/toolbars.zh.md)**：显示你的工具栏列表，让你可以打开或关闭它们，以及创建和编辑新的工具栏。
- **[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)**：这是各种上下文菜单可以被编辑的地方。文件和文件的文件的上下文菜单不是通过这里编辑的 - 相反它们通过 [文件类型](/Manual/file_types/README.zh.md) 系统控制。这里的上下文菜单是为了用户界面元素，比如在一个细节模式文件列表中的列标题、任务栏图标等等。
- **[按键](/Manual/customize/the_customize_dialog/keys.zh.md)**：显示所有已配置热键的列表，并让你编辑它们并创建新的热键。
- **[命令](/Manual/customize/the_customize_dialog/commands.zh.md)**：显示一个命令列表，可以通过拖放轻松添加到工具栏中。你也可以使用底层 [命令集](/Manual/reference/command_reference/README.zh.md) 手动构建命令。
- **[用户命令](/Manual/customize/the_customize_dialog/user_commands.zh.md)**：让你可以将你自己的命令添加到内部命令集中。你可以在任何可以使用内部命令的位置使用用户命令。
- **[默认工具栏](/Manual/customize/the_customize_dialog/default_toolbars.zh.md)**：显示默认工具栏，并让你可以将按钮拖到你的工具栏中。此页还可以高亮显示在不同时间点添加的新命令，使更容易使你自己的自定义工具栏保持最新。

##### 页面菜单

在 Customize 对话框的右上角，![](/Manual/images/media/13/prefs_menu.png) 页面菜单包含许多命令：

- **导入**：此命令的行为取决于当前选定的 Customize 对话框中的页面。
- **导出**：这个也是这样；实际导出什么取决于当前页面。
- **保存浮动工具栏**：此命令保存任何当前显示的浮动工具栏的状态和位置。例如，如果你想设置一个浮动工具栏作为程序启动器，你会浮动它，将它定位在所需位置，然后选择此命令使 Opus 记住此设置以备将来使用。如果你启用了 [工具栏选项](/Manual/preferences/preferences_categories/toolbars/toolbar_options.zh.md) 配置页面上的 **在退出时自动保存浮动工具栏的状态** 选项，则当 Opus 关闭时会自动记住你的浮动工具栏。
- **恢复出厂设置**：让你在某些上下文中重置选定项目。
- **撤消更改**：此命令取决于当前页面中的当前选择。例如，在工具栏页面中，它允许你恢复当前选定的工具栏，撤消自进入自定义模式以来对它的任何更改。
- **撤消所有更改**：此命令将撤消自进入自定义模式以来对所有可以撤消的内容的所有更改。单击 Customize 对话框上的 **取消** 按钮会产生同样的效果。

##### 自定义快捷方式

当你在自定义模式时，一个微型工具栏会出现在任何打开的文件窗口的标题栏中。

![](/Manual/images/media/13/mini_customize.png)

这样即使它隐藏在文件窗口的下面也容易返回到 Customize 对话框。单击工具栏的主体部分（标记）以将 Customize 对话框带到前面。复选标记和叉号按钮还允许你在不需要首先将其带到前台的情况下许可/取消 Customize 对话框。