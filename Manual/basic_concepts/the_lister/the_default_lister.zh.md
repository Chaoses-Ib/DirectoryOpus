# 默认文件窗口

无论何时打开“新”目录查看器，通常都会使用默认文件窗口。默认情况下，每当你关闭目录查看器时，默认文件窗口的配置都会自动更新——所以从最简单的意义上讲，如果你关闭一台目录查看器，然后打开另一台，你通常会找回之前的内容。

### 何时使用默认文件窗口？

打开新的目录查看器有许多不同的方式，默认文件窗口的使用与否取决于你打开目录查看器的方法以及可能影响特定方法的任何设置。

- 双击 Directory Opus 程序快捷方式，或在将它固定到任务栏后单击其图标，通常会在 Opus 已在运行的情况下使用默认文件窗口。
如果 Opus 尚未运行，则 **[启动 Opus/启动](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.zh.md)** 配置页面中的选项将控制是否使用默认文件窗口。

- 如果在 [启动 Opus/从桌面](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_desktop.zh.md) 配置页面上启用了 **打开默认文件窗口** 选项，则双击桌面上的一处空白位置将打开默认文件窗口。
- 如果启用了 [资源管理器替换](../explorer_replacement.zh.md) 模式，则由于资源管理器替换（例如，双击桌面上的文件夹快捷方式）而打开新的目录查看器时将使用默认文件窗口。
- 按 <kbd>Win+E</kbd> 可以根据 [启动 Opus/从 Win + E 快捷键](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.zh.md) 配置页面中的设置打开默认文件窗口。
- 如果在 **[启动 Opus/从任务栏图标](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_taskbar_icon.zh.md)** 配置页面中启用了相应选项，则双击 Opus 任务栏通知图标将打开默认文件窗口。
- 使用原始 `Go NEW` 命令打开的目录查看器通常会使用默认文件窗口。

### 何时不使用默认文件窗口？

无论何时打开已保存的 [目录查看器布局](layouts/README.zh.md) 时，都不会使用默认文件窗口——无论是手动打开布局，还是触发配置为打开布局的操作（例如在桌面上双击）。

### 默认文件窗口选项

[默认文件窗口](/Manual/preferences/preferences_categories/layouts_and_styles/default_lister.zh.md) 配置页面包含控制默认文件窗口如何使用的选项。此处值得提及三个选项：

- **忽略默认文件窗口的文件夹格式**：由于默认文件窗口实际上是一种已保存的布局，因此它会存储布局保存或更新时所使用的文件夹格式。如果此选项已启用，则存储在默认文件窗口内的文件夹格式会被忽略——而新目录查看器中显示的路径的正常文件夹格式将被使用。
- **忽略默认文件窗口的工具栏**：同样，如果此选项已启用，则存储在默认文件窗口中的工具栏将被忽略，而 [默认工具栏集](toolbars/the_default_toolbars/README.zh.md) 将被用作替代。
- **在关闭目录查看器时自动更新默认文件窗口选项**：如果将其关闭，则你可以使用 **设置** 下拉菜单中的 **设置为默认文件窗口** 命令手动更新默认文件窗口设置。

### 手动更新默认文件窗口

TOBEDONE