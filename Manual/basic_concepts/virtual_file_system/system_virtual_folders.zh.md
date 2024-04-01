# 系统虚拟文件夹

Windows 中有许多虚拟文件夹，它们显示为文件系统的一部分（也称为 *shell 文件夹*）。*桌面* 文件夹就是虚拟文件夹的一个示例。它是一个可以包含实际文件的文件目录（例如，如果你将一个文档保存到桌面，则它存储在实际磁盘文件夹中），但它还包含不对应于磁盘上实际文件的虚拟项（例如，桌面包含指向 *回收站* 和 *此电脑* 文件夹的链接）。

### 某些 Shell 文件夹的本机实现

Opus 提供几个虚拟文件夹的本机实现。这意味着你可以在一些常用的虚拟文件夹中使用 Opus 功能，如 [文件夹格式](../folder_options/folder_formats.zh.md)、[增强模式](../the_lister/view_modes.zh.md) 或偏好设置，如 [背景图片](/Manual/preferences/preferences_categories/colors_and_fonts/images.zh.md)。Opus 当前支持的虚拟文件夹如下：

- **桌面**：表示桌面的内容，名义上是 Shell 命名空间的根。它显示基于磁盘的两个文件夹（个人桌面文件夹和 *All Users* 桌面文件夹）的合并内容，以及指向各种虚拟文件夹（如回收站、网络、库等）的链接。Opus 提供的本机视图可以从 **[虚拟文件夹/桌面](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.zh.md)** 配置页面进行配置 - 你可以选择在桌面上显示哪些虚拟文件夹。
- **此电脑**：显示系统中安装的磁盘驱动器和设备。默认情况下，不显示空的磁盘驱动器（例如没有光盘的 DVD 驱动器） - 你可以从 **[虚拟文件夹/此电脑](/Manual/preferences/preferences_categories/folders/virtual_folders/this_pc.zh.md)** 配置页面更改此设置。
- **刻录光盘**：当使用 Windows 光盘刻录系统（仅限于分段刻录 - LiveFS 数据包写入系统像普通磁盘文件夹一样处理）时，Opus 提供可写 CD 和 DVD 光盘的本机视图。

### 其它 Shell 文件夹由资源管理器实现

当你导航到 Opus 未本机实现的虚拟文件夹时，文件窗口会充当一个容器，并托管资源管理器的一个实例以提供显示。这样做的优势是可以让你在 Opus 内部导航整个 Shell 命名空间，包括已安装的任何第三方 *Shell 命名空间扩展*。

托管资源管理器的缺点是，对于 Opus 来说，该文件夹是一个“黑匣子”。Opus 根本不知道文件夹的内容是什么 - 甚至是资源管理器提供的显示，Opus 所做的不过只是为资源管理器的窗口提供一个位置。因此，在这些虚拟文件夹中，许多 Opus 本机功能不可用。

### 完全虚拟还是部分真实？

某些虚拟文件夹（如 *计算机*）是纯粹虚拟的 - 它们不对应于磁盘上的实际文件夹。

其它文件夹（如 *C:\Windows\Fonts* 目录）是实际的磁盘文件夹，在资源管理器中显示时有虚拟“叠加”。

在 **[虚拟文件夹/文件系统](/Manual/preferences/preferences_categories/folders/virtual_folders/file_system.zh.md)** 配置页面上的选项使你可以控制 Opus 如何处理这种类型的目录 - 如果需要，可以选择让 Opus 显示底层的“实际”文件夹，而不是虚拟显示。