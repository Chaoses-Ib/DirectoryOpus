# 任务栏图标

Opus 可以将一个图标添加到任务栏通知区域（也称为“托盘”或“系统托盘”图标），您还可以配置双击它时发生的情况。您还可以编辑右键单击时显示的 [上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)。

请注意，Windows 默认可能会隐藏图标并将其移至溢出区域。如果您希望图标始终可见（使本页上的双击选项更有用），您需要告诉 Windows 始终显示它。

- **将图标添加到任务栏通知区域**: 启用任务栏图标。
- **双击时不执行任何操作**: 双击图标时不会发生任何事情 - 但您可以右键单击它以使用上下文菜单。
- **将上次活动的侧边栏置于最前**: 如果已打开一个或多个侧边栏，双击任务栏图标将置最常使用的侧边栏于最前。如果没有打开任何侧边栏，将使用默认侧边栏设置打开一个新的侧边栏。如果您正在使用 Windows 10 的*虚拟桌面*功能，则只考虑当前处于活动状态的桌面的窗口，除非您关闭高级**[高级](../miscellaneous/advanced_options.zh.md)**设置。
- **打开默认侧边栏**: 使用 [默认侧边栏](/Manual/basic_concepts/the_lister/the_default_lister.zh.md) 的设置打开一个新的侧边栏。如果您打开**关闭现有的侧边栏**选项，那么在打开布局之前将关闭任何现有的侧边栏 - 如果关闭此选项，则现有侧边栏将不受影响。
- **运行命令**: 允许您输入一个命令，以便在桌面被双击时运行。这可用于执行更复杂的操作，包括运行外部程序。这必须是一个可以在按钮或热键上有意义的命令。您可以使用 [Opus 内部命令](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md) 或外部程序（使用 [标准控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md) 将参数传递给它们）。如果您想要运行多于一条简单的单行命令，您可以创建一个更复杂的 [用户自定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md），然后在此处指定用户命令的名称。