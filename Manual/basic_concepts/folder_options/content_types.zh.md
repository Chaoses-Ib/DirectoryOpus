# 内容类型
> [!TIP]
> 参见 [内容类型格式](/浏览/查看/文件夹格式.md#内容类型格式)

内容类型系统使你能够基于文件夹的内容，为 Opus 配置自动转换文件夹的显示格式。例如，当您导航到含有大部分图像的文件夹时，显示可以自动切换到缩略图模式。

有两个不同的概念组成内容类型系统：

- **文件类型组**: 内容类型建立在已配置的 [文件类型组](/Manual/file_types/file_type_groups.zh.md)。因此您可以为图像、音乐等任何文件类型组拥有内容类型格式。
- **文件夹格式**: [文件夹格式](folder_formats.zh.md) 用于定义应用于各个文件类型组的显示格式。

### 启用内容类型格式

因为让 Opus 在您未预期时改变文件夹格式可能会造成困扰，因此您需要在配置中特别启用内容类型系统。

每个文件类型组都列在配置的 [文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md) 页上的 **内容类型格式** 类别中。使用组名旁边的复选框来启用其内容类型格式。您还可以在此编辑各个内容类型格式。

### 内容类型阈值

要识别一个文件夹是否匹配一个特定内容类型，必须有一定比例的文件归属于相关文件类型组。每个内容类型格式显示一个百分比值，单击该值对阈值进行编辑。

编辑阈值时，**计算内容阈值时考虑子文件夹** 复选框使您能够在考虑文件夹中的项目百分比时，选择对文件夹进行计数还是忽略。

例如，如果 **图片** 内容类型格式的 **内容阈值** 设置为 *25%*，这意味着，如果您导航到一个文件夹，其中至少有 25% 的文件是图像（或文件的扩展名已添加到 **图片** 文件类型组），则显示将更改为使用由内容类型定义的格式。

### 添加新的内容类型

您可以通过 [文件类型](/Manual/file_types/README.zh.md) 编辑器添加新的文件类型组，或编辑现有文件类型组。

当您通过 [文件类型](/Manual/file_types/README.zh.md) 编辑器 [添加一个新分组](/Manual/file_types/file_type_groups.zh.md) 时，一个它的条目将自动在 [文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)配置页的 **内容类型格式** 部分创建。

更多信息：

[文件类型组](/Manual/file_types/file_type_groups.zh.md)

[文件类型](/Manual/file_types/README.zh.md)

[文件夹格式](folder_formats.zh.md)

[文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)