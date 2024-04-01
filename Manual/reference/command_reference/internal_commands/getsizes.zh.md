# GetSizes

**GetSizes** 内部命令可以用作以下：

- 计算和显示选定文件夹的总大小
- 计算当前文件列表中的所有文件夹的总大小
- 为所有选定文件计算 MD5 检验和

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

计算所有选定文件夹的总大小。如果当前没有任何选定文件夹，则会计算当前文件列表中的所有文件夹的大小。

*示例：** `GetSizes`
</td></tr><tr><td>
EVERYTHING</td><td>
/O</td><td>

*(无值)*</td><td>

如果可能，使用 [Everything](/Manual/additional_functionality/everything_integration.zh.md) 计算选定文件夹的大小。如果未安装 Everything，或当前文件夹未编入索引，则会手动计算大小（通过递归扫描文件夹内容）。

*示例：** `GetSizes EVERYTHING`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

如果在 [文件夹大小](/Manual/preferences/preferences_categories/folders/folder_sizes/README.zh.md)配置页面上设置选项，以使用 Everything 计算文件夹大小，则此命令将覆盖该选项并手动计算大小。

*示例：** `GetSizes EVERYTHING=no`
</td></tr><tr><td>
</td><td>
</td><td>

**only**</td><td>

如果可能，使用 Everything 计算选定文件夹的大小。如果不可行，则根本不会计算大小（无事发生）。

*示例：** `GetSizes EVERYTHING=only`
</td></tr><tr><td>
HASH</td><td>
/K</td><td>

\<type></td><td>

使用指定的哈希算法，为所有选定文件计算校验和。如果当前在文件列表中未显示适当的哈希列，则会自动添加该列。使用此命令会覆盖配置中 **[其它 / 高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面的 **max_md5_file_size** 设置。

支持的哈希算法为 **md5**、**sha1**、**sha256**、**sha512**、**crc32**、**crc32_php**、**crc32_php_rev** 和 **blake3**。

*示例：** `GetSizes HASH=md5`
</td></tr><tr><td>
IGNOREJUNCTIONS</td><td>
/O</td><td>

*(无值)*</td><td>

在计算文件夹大小时，忽略文件夹中的连接和符号链接。这会覆盖配置中的 **配置 / 文件夹 / 文件夹行为 / 计算文件夹大小时忽略连接和符号链接**配置选项。

*示例：** `GetSizes IGNOREJUNCTIONS`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

计算文件夹大小时，不忽略连接和符号链接。

*示例：** `GetSizes IGNOREJUNCTIONS=no`
</td></tr><tr><td>
NODESELECT</td><td>
/S</td><td>

*(无值)*</td><td>

防止在计算完 **GetSizes** 命令选定的文件和文件夹的大小/检验和后取消选择它们。此选项仅在打开配置中 **[文件操作 / 选项](/Manual/preferences/preferences_categories/file_operations/options.zh.md)** 页面的 **延迟取消选择文件直至函数结束** 选项时才有效。

*示例：** `GetSizes NODESELECT`
</td></tr><tr><td>
USEHASHCACHE</td><td>
/S</td><td>

*(无值)*</td><td>

结合使用 **MD5** 和 **SHA** 选项时，启用使用检验和缓存。如果之前已缓存文件的检验和，且该文件看来未发生更改，则将使用缓存的值。

*示例：** `GetSizes MD5 USEHASHCACHE`
</td></tr></tbody>
</table>