# FTP 日志

Opus 可以为连接到的每个 FTP 站点维护一个单独日志。若要启用 FTP 站点的日志记录，请开启 **[显示](ftp_address_book/display_page.zh.md)** 页上站点条目中 **[地址簿](ftp_address_book/README.zh.md)** 的 **启用日志** 选项（以及可选的 **启用调试** 选项）。或者，若要启用所有 FTP 连接的日志记录，请为 **[默认设置](ftp_address_book/default_settings.zh.md)** 条目开启相同的选项。

FTP 日志显示在文件窗口的 [实用工具面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 中，该面板位于文件窗口的底部。若要显示日志，请在工具栏上的 **FTP** 下拉菜单中选择 **显示 FTP 日志** 命令，或者从 **帮助** 菜单中的 **日志** 子菜单中选择。您还可以为站点条目使用 **自动显示日志** 选项，这样，只要连接到该站点，就会自动显示日志。

![](/Manual/images/media/ftp_log.png)

日志顶部的按钮允许您将日志 **保存** (![](/Manual/images/media/ftp_log_-_save.png)) 到文本文件，将任何选中的文本 **复制** (![](/Manual/images/media/ftp_log_-_copy.png)) 到剪贴板，以及 **清除** (![](/Manual/images/media/ftp_log_-_clear.png)) 日志。附加到 **清除** 按钮的下拉框提供了清除所有日志的选项，否则只清除当前显示的日志。

**日志** 下拉框允许您选择查看哪个站点的日志。您连接的每个 FTP 站点都会维护一个单独的日志。下拉框还包含一个 **所有活动** 选项，该选项是一个统一的日志，显示所有 FTP 输出。如果您同时连接到多个站点，则可以使用统一日志同时关注所有 FTP 活动。

日志面板右侧的 **浮动** (![](/Manual/images/media/ftp_log_-_float.png)) 按钮允许您让 FTP 日志显示脱离文件窗口。这样做时，实用工具面板会缩小以占用最小的空间。如果您想将 FTP 日志放在另一台显示器上以关注您的 FTP 活动，这可能会很方便。当您关闭浮动日志时，它会自动返回到来源文件窗口。

[配置](/Manual/preferences/README.zh.md) 中有一些选项会影响 FTP 日志：

- FTP 日志字体可以在配置的 [字体](/Manual/preferences/preferences_categories/colors_and_fonts/fonts.zh.md) 页面上进行配置。
- 每个单独日志的最大大小可以在 [文件操作/日志记录](/Manual/preferences/preferences_categories/file_operations/logging.zh.md) 页面上进行配置。