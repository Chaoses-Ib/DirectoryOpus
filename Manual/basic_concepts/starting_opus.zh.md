# 启动 Opus

我们建议你利用配置中的 **[启动 Opus / 启动](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.zh.md)** 页面上的选项，在 Windows 启动时将 Opus 设为自动启动。Opus 在设计中的目的是持续在后台运行，即便没有窗口开启。此举具备以下几个优点：

- 如果 Opus 已先行在后台加载，那么开启窗口（称为“文件窗口”）将快很多。在桌面上双击或（如果启用了 [替换资源管理器](/Manual/basic_concepts/explorer_replacement.zh.md)）按下 <kbd>Win+E</kbd> 或双击文件夹图标将会在 Opus 已经运行的情况下几乎立刻开启一个文件窗口，而如果 Opus 之前尚未载入内存，则可能会延迟几秒钟。
- Opus 让你能够创建 [浮动工具栏](/Manual/additional_functionality/floating_toolbars/README.zh.md)，你可用其作为命令启动器，而这些启动器只能在 Opus 运行时使用。
- 你可以配置 [系统级热键](/Manual/additional_functionality/system-wide_hotkeys.zh.md) 来运行程序或启动 Opus 功能，同样，这些热键也只在 Opus 运行时有效。

你也可以把 Opus 视作传统的档案管理器，只在需要时运行，不使用时就退出。安装程序可以在桌面上和开始菜单中建立快捷方式图标，而且你可用这些图标来运行 Opus。你也可以将图标固定到任务栏，然后通过这个方式启动 Opus。

### 退出 Opus

当使用 Opus 完成后，如果你要退出，请在文件窗口中从 **文件** 菜单选择 **退出 Directory Opus** 命令，或右击任务栏通知图标（如果已经启用）并从该菜单中选择退出命令。

你也可以设置 Opus 在关闭最后一个文件窗口时自动退出，方法是在配置的 [文件操作 / 选项](/Manual/preferences/preferences_categories/file_operations/options.zh.md) 页面上选择 **所有功能完成后关闭 Directory Opus** 选项。当启用此选项（并且 Opus 未设为启动时运行）时，它将表现得像一个传统的、一体化的档案管理器。

我们不建议通过任务管理器强行终止 Opus 进程，因为你最终可能会导致配置文件无法保存或损坏。