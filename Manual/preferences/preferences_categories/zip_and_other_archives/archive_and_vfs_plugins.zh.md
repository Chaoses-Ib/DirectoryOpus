# 压缩包与 VFS 插件

VFS 插件是 Opus 的第三方扩展，它们扩展了 Opus 列出、解压和创建压缩包文件的能力。**VFS** 是虚拟文件系统的首字母缩写，它表示插件也可以实现整个文件系统（基于格式化为 URL 的路径，如用于 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 的 `coll://`）。然而，目前为止，插件最常见的用法是为 Opus 添加对压缩包文件的支持。

此页面显示您当前已安装的插件处理的所有压缩包类型的列表。插件必须安装在 *[/home](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)/VFSPlugins* 文件夹中。列表顶部的刷新按钮可用于刷新列表以检测新添加的插件。

可以使用复选框按钮开启或关闭每个单独的压缩包类型。某些插件支持其自己的配置 - 项目旁边有一个“齿轮”图标表示此功能。单击齿轮（或选择插件并单击列表上方的 **配置** 按钮）进行配置。

请注意，Opus内置了对 zip 文件的支持，因此插件列表中没有 zip 项。您可以改为在[单独的页面](zip_file_options.zh.md) 上配置 zip 选项。

当插件为 Opus 提供受支持的压缩包格式列表时，这些格式将自动添加到 **压缩包** [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的成员中，这意味着您应该能够自动像访问文件夹一样访问它们（通过双击显示其内容）。