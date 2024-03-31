# 虚拟文件系统

一般来说，*文件系统*是操作系统提供的软件，用于管理磁盘上的文件和文件夹。它会跟踪表示文件的数据在物理磁盘上的存储位置，维护文件名的列表和文件信息，并通常提供与创建和访问磁盘文件相关的所有服务。

### 虚拟文件系统

除了管理存储在硬盘、闪存盘等设备上的标准文件和文件夹以外，Opus 还提供了几个*虚拟文件系统*，用于访问和管理未存储（至少不是直接存储）在传统介质上的文件。

例如，Zip 压缩包是存储在传统文件系统中的单个文件，但 Opus 提供了一个虚拟文件系统来表示该 Zip 文件中包含的所有文件。因此，无需采用传统的方式（将内容解压到文件夹中）来访问压缩包内容，而可以使用虚拟文件系统直接访问内容。通常，Opus 中的虚拟文件系统与真文件系统一样，而且你实际上并不需要意识到它们之间的区别——只需知道这项功能即可。

### 虚拟文件系统类型

Opus 提供的虚拟文件系统包括：

- **[系统虚拟文件夹](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.zh.md)**：*此电脑*和*桌面*等文件夹由 Opus 本机处理。
- **[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)**：文件集合是虚拟文件夹，让你可以创建文件和文件夹集合，而这些文件和文件夹不一定位于同一物理位置。
- **[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md)**：库让你可以将多个文件夹（虚拟地）连接到一起，并显示其内容的统一视图。
- **[压缩包](/Manual/basic_concepts/virtual_file_system/archives.zh.md)**：Opus 支持许多不同的压缩包格式（Zip、RAR、7-zip 等），并让你可以将它们视为普通文件夹。
- **[FTP](/Manual/basic_concepts/virtual_file_system/ftp.zh.md)**：让你可以像访问本地文件夹一样访问远程 FTP 站点。
- **[MTP](/Manual/basic_concepts/virtual_file_system/mtp.zh.md)**：让你可以查看兼容 MTP（*媒体传输协议*）的设备（如手机、平板电脑和相机）中的内容。

### 通过插件扩展

Opus 有一个[插件系统](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.zh.md)，允许第三方开发者添加自己的虚拟文件系统。例如，插件让你可以像访问真实文件夹一样访问系统注册表。