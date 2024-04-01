# 添加到压缩包对话框

当你使用 **压缩包文件** 按钮或上下文菜单命令时，将显示 **添加到压缩包** 对话框。

![](/Manual/images/media/13/add_to_archive.png)

此对话框的顶部始终相同，在这里可以选择压缩包类型、路径和名称。

**压缩包类型** 下拉列表允许你从 Opus 能够写入的任何压缩包格式中进行选择。（某些格式为只读，这里将不会显示。）Opus 支持多种压缩包格式，内置 Zip，而诸如 7z 和 RAR 的格式则由插件处理。第三方插件还可添加到此列表。

这两个文本字段分别允许你指定压缩包的位置和名称。它们的下拉列表显示你最近使用的位置和压缩包名称。（如果你从历史记录中选择了一个压缩包名称，那么如果它与你现在创建的压缩包类型不匹配，则会自动调整它的扩展名。）

除了添加到新压缩包之外，你还可以选择一个现有压缩包来为其添加更多文件。这两个 **浏览** 按钮允许你找到现有的文件夹和压缩包。使用路径旁边的浏览按钮保留名称，只更改位置。使用名称旁边的浏览按钮选择现有压缩包；它最初会向你显示当前路径下的压缩包，但你也可以使用它从其它位置选择压缩包。

如果你的剪贴板中包含要使用的压缩包的完整路径，则可以将其粘贴到名称字段中，以一次自动填写两个文本字段。

若要从两个文本字段复制完整的组合路径，请按 <kbd>Ctrl+Shift+C</kbd>。

对话框的底部显示特定于所选压缩包类型的选项。当你更改 **压缩包类型** 下拉列表中的所选内容时，这些选项将发生变化。某些压缩包格式没有任何选项，而另一些格式允许你选择压缩模式和加密选项等内容。

更多信息：

[Zip 选项](/Manual/file_operations/creating_archives/add_to_archive_dialog/zip_options.zh.md)

[7z 选项](/Manual/file_operations/creating_archives/add_to_archive_dialog/7z_options.zh.md)

[RAR 选项](/Manual/file_operations/creating_archives/add_to_archive_dialog/rar_options.zh.md)

[TAR BZip2 选项](/Manual/file_operations/creating_archives/add_to_archive_dialog/tar_bzip2_options.zh.md)

[TAR GZip 选项](/Manual/file_operations/creating_archives/add_to_archive_dialog/tar_gzip_options.zh.md)