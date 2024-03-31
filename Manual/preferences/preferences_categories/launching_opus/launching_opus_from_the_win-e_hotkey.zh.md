# 来自 Win + E 热键

此页面允许你在按下 <kbd>Win+E</kbd> 热键时配置其执行的操作。

此页面仅在 Windows 10 及更高版本中显示，且资源管理器替换可用（正常安装或在 [便携式 .ini 文件](/Manual/additional_functionality/exporting_to_usb.zh.md) 中启用资源管理器替换的便携式安装）。

<kbd>Win+E</kbd> 热键是许多人习惯用于打开一个新文件资源管理器窗口的热键。在使用 Opus 代替资源管理器时，你可能希望热键打开 Opus。

以下选项允许你配置按下热键时所发生的操作：

- **正常打开文件资源管理器**：<kbd>Win+E</kbd> 热键将像 Directory Opus 安装之前一样打开文件资源管理器。
- **将最后一个活动的文件窗口置于前面**：如果已经打开了一个或多个文件窗口，则 <kbd>Win+E</kbd> 热键将激活你最近使用的文件窗口并将其置于前面。如果未打开文件窗口，则将使用默认文件窗口设置打开一个新的文件窗口。如果你正在使用 Windows 10 的*虚拟桌面*功能，那么只有当前活动桌面上的窗口才会被考虑，除非你关闭高级 **[高级](../miscellaneous/advanced_options.zh.md)** 设置。
- **打开默认文件窗口**：始终使用 [默认文件窗口](/Manual/basic_concepts/the_lister/the_default_lister.zh.md) 的设置打开一个新的文件窗口。如果你启用了 **关闭已经存在的文件窗口** 选项，则在打开布局之前任何现有的文件窗口都将关闭 - 如果此选项关闭，则现有的文件窗口将不受影响。
- **运行命令**：允许你在每次按下热键时输入一条要运行的命令。这可用于执行更复杂的操作，包括运行外部程序。这必须是一条在按钮或热键上合理的命令。你可以使用 [Opus 内部命令](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md) 或外部程序（向其传递参数，使用 [标准控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)）。如果你想要运行多于一条简单的单行命令，你可以创建一个更复杂的 [用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md），然后在此处指定用户命令的名称。

##### Windows 10 之前的 Win+E

在早期版本的 Windows 上，我们无法对 Win + E 热键拥有如此多的控制权，它通常会导致在默认文件管理器中打开*此电脑*，如果 Opus 设置为替换资源管理器，那么文件管理器就是 Opus。

如果你希望自定义 <kbd>Win+E</kbd> 在早期版本的 Windows 上执行的操作，请尝试创建一个 [系统级热键](/Manual/additional_functionality/system-wide_hotkeys.zh.md) 来覆盖标准热键。（请注意，如果你在 Windows 10 上通过这种方式设置热键，则它可能会覆盖此配置页面上的设置。仅使用一种方法或另一种方法。）