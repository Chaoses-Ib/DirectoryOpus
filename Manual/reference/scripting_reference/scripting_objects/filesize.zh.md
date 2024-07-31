# FileSize

**FileSize** 对象用于更方便地处理表示文件大小的变量。如今，文件大小超过 4GB 非常常见，但不幸的是，ActiveX 脚本对表示此类大数字所需的 64 位整数没有适当的支持。因此，只要 Opus 脚本对象返回文件大小或表示字节数的数字，它都是以 **FileSize** 对象的形式。例如，**[Item](item.zh.md).size** 属性返回一个表示特定文件或文件夹大小的 **FileSize**。

您可以使用 **[FSUtil](fsutil.zh.md).NewFileSize** 方法创建一个新的 **FileSize** 对象。FileSize 对象通常表示一个 *无符号* 64 位整数，但如果您在创建时指定 *"s"* 标志，它将改为存储一个 *有符号* 整数。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>

返回此 **FileSize** 对象所代表的字节数作为 *string*。
</td></tr><tr><td>
cy</td><td>

*currency*</td><td>

返回字节数作为 *currency* 值。这是一个 64 位数据类型，但它存储为小数，因此您必须将返回值乘以 10000 以获得实际的字节大小。
</td></tr><tr><td>
fmt</td><td>

*string*</td><td>

返回字节数作为自动格式化的字符串（例如，如果 **FileSize** 值为 1024，则将返回字符串 *1 KB*）。
</td></tr><tr><td>
high</td><td>

*decimal*</td><td>
返回文件大小的最高（最显著） 32 位。并非所有脚本语言都支持这种数据类型（例如 VBScript 不支持）。
</td></tr><tr><td>
highhex</td><td>

*string*</td><td>
返回文件大小的最高 32 位作为十六进制字符串。
</td></tr><tr><td>
low</td><td>

*decimal*</td><td>
返回文件大小的最低（最低有效） 32 位。
</td></tr><tr><td>
lowhex</td><td>

*string*</td><td>
返回文件大小的最低 32 位作为十六进制字符串。
</td></tr><tr><td>
val</td><td>

*decimal*</td><td>
返回字节数作为十进制值。这是一个 64 位数据类型，但并非所有脚本语言都支持它（例如 VBScript 不支持）。
</td></tr><tr><td>
valhex</td><td>

*string*</td><td>
返回字节数作为十六进制字符串。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Add</td><td>

*variant*</td><td>

*none*</td><td>

将提供的 value 加到此 **FileSize** 对象的值中。您可以传递 *string*、*int* 或 *currency* 类型，或另一个 **FileSize** 对象。
一些 **FileSize** 对象是只读的，如果您尝试修改它们，将出错。这包括 **[Item](item.zh.md).size** 返回的那些对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Clone</td><td>

*none*</td><td>

*object:***FileSize**</td><td>

克隆此 **FileSize** 对象并返回一个设置为相同值的新对象。
</td></tr><tr><td>
Compare</td><td>

*variant*</td><td>

*int*</td><td>

将提供的 value 与此 **FileSize** 对象的值进行比较。返回值将为 **0**（相等）、**1**（大于）或 **-1**（小于）。
</td></tr><tr><td>
Div</td><td>

*variant*</td><td>

*none*</td><td>

用提供的 value 除以此 **FileSize** 对象的值。您可以传递 *string*、*int* 或 *currency* 类型，或另一个 **FileSize** 对象。
一些 **FileSize** 对象是只读的，如果您尝试修改它们，将出错。这包括 **[Item](item.zh.md).size** 返回的那些对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Mult</td><td>

*variant*</td><td>

*none*</td><td>

将此 **FileSize** 对象的值乘以提供的 value。您可以传递 *string*、*int* 或 *currency* 类型，或另一个 **FileSize** 对象。
一些 **FileSize** 对象是只读的，如果您尝试修改它们，将出错。这包括 **[Item](item.zh.md).size** 返回的那些对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Set</td><td>

*variant*</td><td>

*none*</td><td>

将 **FileSize** 设置为提供的 value。您可以传递 *string*、*int*、// decimal *或 *currency// 类型，或另一个 **FileSize** 对象。您还可以传递一个 **[Blob](blob.zh.md)**，其中包含正好 1、2、4 或 8 个字节，在这种情况下，**[Blob](blob.zh.md)** 中包含的数据将用于形成数字。您可以通过在前面添加 **\$** 或 **0x** 来使用十六进制字符串。
如果 **FileSize** 对象是只读的，如果您尝试修改它，将出错。使用 **Clone** 或 **[FSUtil](fsutil.zh.md).NewFileSize** 创建一个您可以修改的新对象。
</td></tr><tr><td>
Sub</td><td>

*variant*</td><td>

*none*</td><td>

从此 **FileSize** 对象的值中减去提供的 value。您可以传递 *string*、*int* 或 *currency* 类型，或另一个 **FileSize** 对象。请注意，**FileSize** 对象是 *无符号* 的，因此该值不能低于零。
一些 **FileSize** 对象是只读的，如果您尝试修改它们，将出错。这包括 **[Item](item.zh.md).size** 返回的那些对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
ToBlob</td><td>

*int*</td><td>

*object:***[Blob](blob.zh.md)**</td><td>

返回一个 **[Blob](blob.zh.md)**，其中包含构成当前值的字节。默认情况下，将把 8 个字节复制到 **[Blob](blob.zh.md)**（完整的 64 位数字），但您可以传递一个可选的字节数（1、2 或 4）作为参数来截断该值。
</td></tr></tbody>
</table>