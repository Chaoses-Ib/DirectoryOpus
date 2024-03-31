# 文件合集

文件合集是一个虚拟文件夹，能够充当其他文件和文件夹的容器。文件合集中的项目不必存储在同个物理文件夹中——它们可以保存在其他文件夹、其他磁盘中，甚至在其他（比如 FTP）[虚拟文件系统](/Manual/basic_concepts/virtual_file_system/README.zh.md) 中。当您向合集中添加项目时，实际上并不会移动或修改它们——Opus 仅仅存储原始文件的引用。

##### 合集用于搜索结果

文件合集由 **[快速搜索](../searching_and_filtering/windows_search.zh.md)**、**[查找文件](../searching_and_filtering/find_files/README.zh.md)** 和 **[重复文件查找器](/Manual/additional_functionality/duplicate_file_finder.zh.md)** 功能用于显示搜索结果。

当您使用这些工具执行搜索时，任何匹配的文件都将自动添加到指定的文件夹合集中。

您可以将快速搜索另存为 [存储查询](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md) - 这是一种特殊类型的文件合集，每次导航到该文件夹时都能自动重新生成其搜索结果。

##### 使用合集中的文件

您可以处理文件合集中的文件（复制、重命名、删除等），就像处理真实文件一样。

> [!NOTE]
> 当您删除合集中的文件时，不仅会从合集中将其删除，还将删除**真实文件**。要从合集中删除一个文件而无需删除真实文件，请使用 **删除** 下拉菜单上的 **从合集中移除** 命令。

##### 文件合集路径

文件合集使用带有 `coll://` 前缀的 URL 样式路径格式在内部进行引用。

例如，默认查找结果合集的路径为 `coll://Find Results/`。

您可以在位置字段中键入此类路径，或在按钮和热键中使用它，其内部命令设置为自动使用合集。例如，按钮上的命令 `Copy TO "coll://Favorite Photos"` 会自动将所有选定的文件添加到名为"Favorite Photos"的合集中。

##### 文件合集根文件夹

文件合集根文件夹包含您的所有顶级文件合集（您不能向根目录本身添加项目）。要访问文件合集根目录，您可以：

- 单击文件夹树中的 **文件合集** 项目（除非您已在偏好设置的 **[文件夹树 / 内容](/Manual/preferences/preferences_categories/folder_tree/contents.zh.md)** 页面中禁用此功能）
- 双击桌面上的 **文件合集** 项目（除非已在 **[虚拟文件夹 / 桌面](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.zh.md)** 偏好设置页面中禁用此功能）
- 从 [位置字段](../the_lister/navigation/breadcrumbs_location_field.zh.md) 中的下拉菜单中选择 **文件合集** 项目
- 单击 [位置字段](../the_lister/navigation/breadcrumbs_location_field.zh.md) 并输入路径 `coll://`

##### 创建新合集

在文件合集根目录中，您可以使用工具栏上的 **新建文件夹** 功能来创建新合集。您可以通过其属性对话框为文件合集指定自己的图标——如果需要，您还可以指定描述字符串。

##### 子合集

您还可以创建子合集，就像创建子文件夹一样——只需导航到父合集并像往常一样创建新文件夹。

##### 文件夹格式

您可以定义合集的默认 [文件夹格式](../folder_options/README.zh.md) ——无论何时导航到合集，都会预先配置为添加 **位置** 列。此列很有用，因为它显示合集中项目的真实位置。

##### 合集中项目的上下文菜单

**[文件类型](/Manual/file_types/README.zh.md)** 对话框可用于为合集中项目的上下文菜单添加命令。预定义了两个命令；**从合集中移除**（如上所述）和 **打开所在文件夹**。后一个命令使用 `Go OPENCONTAINER` 功能来打开包含选定合集项目的真实文件夹。

##### 在 Opus 外部使用合集

不幸的是，文件合集系统仅在 Directory Opus 中可用——您无法通过其他程序或资源管理器访问您的合集。然而，在偏好设置的 **[杂项 / Windows 集成](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.zh.md)** 选项中提供了几个选项，它们可以将合集更紧密地集成到系统中：

- **向桌面添加“文件合集”图标**：如果启用此选项，Opus 将在您的桌面上放置一个代表根文件合集文件夹的图标；双击它将打开一个显示文件合集的文件窗口。
- **向“发送到”菜单中添加文件合集列表**：此选项会导致 Opus 为您的文件合集向 *发送到* 菜单（在右键单击文件并从其上下文菜单中选择 *发送到* 时显示的菜单）中添加链接。这允许您在 Opus 外部向文件合集添加项目。

##### 从外部脚本使用文件合集

**[DOpusRT](/Manual/reference/dopusrt_reference/README.zh.md)** 命令可用于在 Opus 外部访问和操作文件合集——有关更多信息，请参见 **[文件合集的外部操作](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.zh.md)**。