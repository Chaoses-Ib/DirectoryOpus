# 启动

此页面上的设置使您能够将 Opus 设置为在 Windows 启动时自动运行。您还可以控制在 Opus 启动时自动打开哪些文件窗口，无论是在 Windows 启动时还是稍后手动启动时。

- **在系统启动时自动启动 Directory Opus**：[Windows 启动时，Directory Opus 将自动开始运行。始终运行 Opus 意味着打开文件窗口要快得多，并且它还使您可以使用可配置的[系统级热键](/Manual/additional_functionality/system-wide_hotkeys.zh.md) 和[浮动工具栏](/Manual/additional_functionality/floating_toolbars/README.zh.md)。通过向开始菜单中的*Startup* 程序组添加快捷方式来实现启动时运行。
  - **不要打开任何文件窗口**： 当 Opus 在系统启动时运行时，不会打开任何文件窗口。如果您退出 Opus，然后手动重新启动它，则以下选项仍适用。

##### Opus 启动时发生的情况

- **打开默认文件窗口**：打开默认文件窗口。
- **打开程序上次关闭时打开的文件窗口**： 当 Opus 退出时，它会记住打开了哪些文件窗口，并在下次启动时还原它们。
  - **自动备份打开文件窗口**： Opus 会根据配置的计划自动保存打开文件窗口（以及关闭时）。
  - **将每个文件窗口还原到其原始虚拟桌面**： 如果 Windows 10 或更高版本使用虚拟桌面，则文件窗口在重新打开时将放回其原始桌面。
- **打开已保存的文件窗口布局**：打开已保存的[文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md)。
- **运行命令**：允许您输入要在启动时运行的命令。这可用于执行更复杂的操作，包括运行外部程序。这必须是在按钮或热键上合理的命令。您可以使用 [Opus 内部命令](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md) 或外部程序（使用 [标准控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md) 向它们传递参数）。如果您希望运行多于一个简单的单行命令，您可以创建一个更复杂的 [用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md)，然后在此处指定用户命令的名称。