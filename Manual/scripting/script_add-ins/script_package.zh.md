# 脚本包

为使向他人分发脚本更为轻松，可以将一个或多个脚本加载项捆绑至称为的压缩文件中，称为 *脚本包*（带有 **.osp** 后缀的 zip 文件）。

还可以包含一组图标，该组图标可以为您脚本添加的任何内部命令提供默认图标图像。

制作脚本包：

- 创建 Zip 压缩文件（目前将其后缀保留为 **.zip**）。
- 将脚本文件（**.js**、**.vbs** 等）复制到压缩文件中。
- 完成后，重命名压缩文件，使其具有 **.osp** 后缀。

如果您愿意，可以将 **.osp** 添加到配置中“**[Zip 和其他压缩文件/Zip 文件](/Manual/preferences/preferences_categories/zip_and_other_archives/README.zh.md)**”页面中识别出的 Zip 文件扩展名列表，以便在 Opus 中更轻松地处理脚本包。

如果您想添加脚本可以引用的图标：

- 编写图标组，依据参考部分中 [图标组](/Manual/reference/icon_sets/README.zh.md) 的说明进行操作。*请勿将其压缩为 **.dis** 文件。*
- 在脚本包压缩文件中创建一个名为 **icons** 的子文件夹。
- 将图标组的所有文件复制到 **icons** 子文件夹中。

在脚本中，可以使用图标组中的图标作为所添加的任何 [内部命令](../example_scripts/adding_a_new_internal_command.zh.md) 的默认工具栏按钮图像，方法是使用 **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.zh.md).icon** 属性。

脚本包还可以包含外部 [脚本资源](../resources/README.zh.md) 文件。这些文件必须带有 **.odxml** 文件扩展名的 XML 文件。可以使用脚本中的 **[Script](/Manual/reference/scripting_reference/scripting_objects/script.zh.md).LoadResources** 方法从包中加载脚本资源文件。