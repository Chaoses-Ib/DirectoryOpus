# 压缩包

Directory Opus 支持多种不同的档案格式。内置对 Zip 文件（最常见的 Windows 压缩包格式）的支持，并通过插件系统支持许多其他格式（如 RAR、7-zip、ISO 等）。

##### 压缩包表现为文件夹

格式支持是内置的还是通过插件实现的，Opus 都允许您将所有支持的压缩包格式视为普通文件夹。

双击支持的压缩包格式会像文件夹一样导航到其中，您可以复制其中的文件或直接查看其内容，就像普通文件一样。对于支持创建压缩包的格式，可以使用复制粘贴或拖放等普通复制功能将文件添加到压缩包中。

##### 压缩包格式选项

配置中有大量选项可用于配置 Opus 中的压缩包支持。

对于 Zip 文件，请参阅 **[Zip 及其他压缩包 / Zip 文件](/Manual/preferences/preferences_categories/zip_and_other_archives/zip_file_options.zh.md)** 页面。

对于所有其他格式，请参阅 **[Zip 及其他压缩包 / 压缩包和 VFS 插件](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.zh.md)** 页面。

您还可以在 **[文件夹树 / 内容](/Manual/preferences/preferences_categories/folder_tree/contents.zh.md)** 页面上的 **在文件夹树中显示** 设置中选择是否在文件夹树中显示压缩包。

##### 创建新压缩包

默认工具栏上的 **压缩包文件** 按钮允许您将选定的文件添加到新压缩包中。附加到该按钮的下拉列表包含许多其他与压缩包相关的命令，这些命令允许您创建或提取压缩包文件。

##### 压缩包上下文菜单

还通过上下文菜单为支持的格式提供对压缩包的广泛控制 - 您可以从配置中的 **[Zip 及其他压缩包 / 压缩包上下文菜单](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.zh.md)** 页面配置为每个格式显示哪些上下文菜单项。

##### 禁用压缩包格式

如果您想在 Opus 中禁用对某种格式的支持，可以通过 **[Zip 及其他压缩包](/Manual/preferences/preferences_categories/zip_and_other_archives/README.zh.md)** 配置部分来实现。

##### 压缩包文件类型组

默认情况下，Opus 支持的所有压缩包格式都包含在 **压缩包** [文件类型组](/Manual/file_types/file_type_groups.zh.md) 中。您可以使用此组一次性更改双击操作或为所有支持的压缩包格式添加上下文菜单项。