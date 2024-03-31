# Zip 文件

与通过插件系统实现的 7-Zip、RAR 和其他压缩包格式不同，Opus 内置了对 Zip 文件的支持。虽然您真的不必在意其中的区别，但值得一提的是，因为您可能会觉得为什么 Zip 压缩包有时会在某些方面以不同方式处理。例如，影响 Zip 文件的选项在配置中的一个单独页面上，而其他压缩包格式不在该页面上。

虽然您通常可以用相同的方式处理 Zip 文件和其他压缩包格式，但是为 Zip 文件提供了以下几个特殊功能，这些功能不适用于其他格式：

- **Zip 注释**：提供了对设置嵌入式 [注释](/Manual/file_operations/creating_archives/zip_files/zip_comment.zh.md) 的明确支持。
- **只读模式**：仅适用于压缩包文件的一种特殊模式 - 它们可以被打开为 [只读](/Manual/file_operations/creating_archives/zip_files/read-only_mode.zh.md) 模式，以防止意外更改压缩包的内容。
- **自解压 Zip 文件**：Opus 可以将 Zip 文件转换为 [自解压](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.zh.md) 格式 - 一个可执行文件，运行时自动解压其内容。

Opus 还将其自己的某些文件格式内部使用 Zip 文件。例如，如果您 [备份您的配置](/Manual/preferences/backing_up_and_restoring_preferences.zh.md)，Opus 就会创建一个 **.ocb** 文件 - 这实际上是一个 Zip 压缩包，如果您将该文件重命名为 **.zip**，则可以像普通压缩包一样打开它。

更多内容：

[Zip 注释](/Manual/file_operations/creating_archives/zip_files/zip_comment.zh.md)
[只读模式](/Manual/file_operations/creating_archives/zip_files/read-only_mode.zh.md)
[自解压 Zip 文件](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.zh.md)