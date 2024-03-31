# 默认文件窗口

默认文件窗口是一个特殊的 [已保存布局]()，由一个文件窗口组成。它通常在打开一个“新”文件窗口且未指定特定已保存布局时使用。默认文件窗口会自动创建 - 不需要您自己创建 - 而且在默认情况下，当您关闭一个文件窗口时，它会自动更新。

##### 何时使用默认文件窗口？

有很多种打开一个新文件窗口的方法，是否使用默认文件窗口取决于您打开文件窗口的方法和可能影响该特定方法的任何设置。

- 双击 Directory Opus 程序快捷方式，或在将程序图标固定到任务栏时单击该图标，若 Opus 已在运行，则通常会使用默认文件窗口。
  若 Opus 尚未运行，则 **[启动 Opus / 启动](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.zh.md)** 配置页面上的选项会控制是否使用默认文件窗口。

- 如果在 [启动 Opus / 从桌面](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_desktop.zh.md) 配置页面上启用了 **打开默认文件窗口** 选项，则双击桌面上空的位置将打开默认文件窗口。
- 如果启用了 [资源管理器替换](../../explorer_replacement.zh.md) 模式，则每当因资源管理器替换而打开一个新文件窗口时都会使用默认文件窗口（例如，双击桌面上某个文件夹的快捷方式）。
- 根据 [启动 Opus / 从 Win + E 热键](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.zh.md) 配置页面上的设置，按 <kbd>Win+E</kbd> 可以打开默认文件窗口。
- 如果在 **[启动 Opus / 从任务栏图标](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_taskbar_icon.zh.md)** 配置页面上启用了相应选项，则双击 Opus 任务栏通知图标将打开默认文件窗口。
- 使用原始 `Go NEW` 命令打开的文件窗口一般会使用默认文件窗口。

##### 何时不使用默认文件窗口？

无论通过手动打开布局，还是触发配置为打开布局的动作（例如在桌面上双击）来打开已保存的文件窗口布局时，都不会使用默认文件窗口。

##### 默认文件窗口选项

[默认文件窗口](/Manual/preferences/preferences_categories/layouts_and_styles/default_lister.zh.md) 配置页面包含控制如何使用默认文件窗口的选项。这里值得一提的三个选项：

- **忽略默认文件窗口的文件夹格式**：因为默认文件窗口实际上是一个已保存的布局，所以它在布局被保存或更新时存储了当时使用的文件夹格式。如果打开此选项，则会忽略存储在默认文件窗口中的文件夹格式 - 相反，将使用新文件窗口中显示的路径的正常文件夹格式。
- **忽略默认文件窗口的工具栏**：类似地，如果打开此选项，则将忽略存储在默认文件窗口中的工具栏，而将使用 [默认工具栏设置](../toolbars/the_default_toolbars/README.zh.md)。
- **关闭文件窗口时自动更新默认文件窗口**：如果关闭此选项，则可以使用 **设置** 下拉菜单中的 **设为默认文件窗口** 命令手动更新默认文件窗口设置。