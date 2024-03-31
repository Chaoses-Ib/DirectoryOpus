# 系统级热键

热键（也称为键盘快捷键）是一种用于触发操作的单个键或按键组合，通常用来运行指令或启动程序。Opus 让您创建多种类型的热键。

- 工具栏和菜单按钮可以与热键相关联。在文件窗口中按此键将激活按钮的功能。
- 列在您的 [收藏夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md) 中的文件夹可以附加热键。在文件窗口中按该键将读取收藏夹文件夹。
- 您可以创建不关联到按钮、工具栏或任何其他项的热键，它们是“纯”热键，独立存在。

真正的热键通过 [Customize](/Manual/customize/README.zh.md) 对话框的 [Hotkeys](/Manual/customize/the_customize_dialog/keys.zh.md) 页面创建。您会发现可以通过此方式创建两种类型的热键：

- 局部热键（默认）仅当文件窗口窗口处于活动状态时才能使用。
- 全局或系统级热键可在系统中的任何地方使用，只要 Opus 在后台运行即可。

![](/Manual/images/media/hotkeys.png) 

系统级热键的一种用途是作为启动程序的快捷方式，例如您可以重新分配 **Ctrl+Shift+W** 以启动 Microsoft Word。

![](/Manual/images/media/word_hotkey.png)

由于 Opus 拦截系统级热键（无论您使用的是哪个程序），因此在选择要使用的键时必须小心。例如，您当然可以创建一个系统级热键，每当您按 **空格键** 时激发，但这样的话您将永远无法键入空格！因此，我们通常建议对系统级热键使用多键组合。Opus 甚至允许您重新分配资源管理器通常为自己保留的 **Windows** 键热键。例如，您可以将 **Windows+E** 重新映射为即便在 [资源管理器替代](/Manual/basic_concepts/explorer_replacement.zh.md) 模式关闭的情况下也能专门打开一个 Opus文件窗口。

有关创建热键的详细信息，请参阅 [自定义](/Manual/customize/README.zh.md) 部分中的 [Hotkeys](/Manual/customize/the_customize_dialog/keys.zh.md) 页面。