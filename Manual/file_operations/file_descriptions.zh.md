# 文件说明

文件说明是用户定义的字符串，可指定给文件或文件夹，通常用来保存有关文件内容的备注。遗憾的是，Windows 未提供标准化的系统来为文件和文件夹添加用户定义的说明。Opus 允许您这样做，并提供了两种不同的存储说明的机制：

- *descript.ion* 系统是一个旧的、伪标准，将文件夹中所有项目的说明另存到一个独立的文件（称为 “descript.ion”）中，此文件位于同一文件夹中。
- *NTFS 注释* 系统使用 NTFS 文件系统的 [备用数据流](http://en.wikipedia.org/wiki/Alternate_Data_Stream#NTFS) 功能，将文件的说明存储在附加到该文件的独立数据流中。

这两个系统各有优缺点。*descript.ion* 系统可能受到其他程序的支持 - 例如，一些图像查看工具支持此系统，您可能需要在 Opus 中启用此功能，以便可在其他程序中看到由一个程序添加的说明。*descript.ion* 的缺点是效率较低 - 每次读取或写入说明时，都必须打开和解析 *descript.ion* 文件。*descript.ion* 文件还会使您的文件列表变得杂乱，尽管 Opus 提供了隐藏它们的功能（如果需要）。

使用 *NTFS 注释* 系统比 *descript.ion* 系统更高效，由于备用数据流通常不可见，所以它可以为使用文件注释带来更优雅和统一的感觉。其主要缺点是不仅支持 NTFS 格式化的驱动器 - 如果您使用 FAT32 等其他文件系统，则此系统不起作用。

您可以从配置中的 [文件运算/元数据](/Manual/preferences/preferences_categories/file_operations/metadata/README.zh.md) 页面选择要使用的系统。

[复制文件/元数据](/Manual/preferences/preferences_categories/file_operations/copying_files/metadata.zh.md) 页面上的选项允许您控制在复制文件时是否保留文件说明。

无论您选择哪种系统，您都可以通过两种方式为文件指定说明。

##### 设置说明对话框

使用默认工具栏上的**属性**下拉中的**说明**命令（或按 <kbd>Ctrl+P</kbd>），以显示 *设置说明* 对话框。

此对话框显示当前说明（如果有），并允许您清除或编辑它。

![](/Manual/images/media/13/setdesc_menu_001.png)

- **应用于所有选定项目**：将对所有选定项目设置相同的说明。如果关闭此功能，则只有第一个选定项目将设置其说明，且对话框将重新打开以供下一个项目使用。
- **应用于选定文件夹内的所有文件**：此功能将递归运行 -所有选定文件夹内的所有文件都将获得相同的说明。

##### 元数据编辑器

您还可以通过 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md) 或 [设置元数据](editing_metadata/README.zh.md) 对话框来设置说明。这些选项允许您使用 **扩展属性** 类别中的 **注释** 栏位来编辑所选文件说明。

![](/Manual/images/media/13/meta_desc.png)

有关使用元数据编辑器的详细信息，请参阅 [编辑元数据](editing_metadata/README.zh.md) 页面。