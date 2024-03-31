**FileSize** 对象提供了方便处理表示文件大小的变量的功能。如今，文件大于 4GB 的情况非常普遍，但不幸的是，ActiveX 脚本不支持表示此类大数字所需的 64 位整数。因此，每次 Opus 脚本对象返回表示文件大小或字节数的数字时，返回的都是一个 **FileSize** 对象。例如，**[Item](item.zh.md).size** 属性返回一个 **FileSize** 以表示特定文件或文件夹的大小。

你可以使用 **[FSUtil](fsutil.zh.md).NewFileSize** 方法创建新的 **FileSize** 对象。FileSize 对象通常表示一个 *无符号* 的 64 位整数，但是如果你在创建时指定了 *"s"* 标志，它将存储一个 *有符号* 的整数。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>

以 *字符串* 返回此 **FileSize** 对象表示的字节数。
</td></tr><tr><td>
cy</td><td>

*货币*</td><td>

以 *货币* 值返回字节数。这是一个 64 位数据类型，但存储为分数值，因此你必须将返回的值乘以 10000 以获取实际字节大小。
</td></tr><tr><td>
fmt</td><td>

*字符串*</td><td>

以自动格式化的字符串返回字节数（例如，如果 **FileSize** 值为 1024，则会返回字符串 *1 KB*）。
</td></tr><tr><td>
high</td><td>

*十进制*</td><td>

返回文件大小的最高（最显着）32 位。并非所有脚本语言都支持此数据类型（例如，VBScript 不支持）。
</td></tr><tr><td>
highhex</td><td>

*字符串*</td><td>

以十六进制字符串返回文件大小的最高 32 位。
</td></tr><tr><td>
low</td><td>

*十进制*</td><td>

返回文件大小的最低（最不显着）32 位。
</td></tr><tr><td>
lowhex</td><td>

*字符串*</td><td>

以十六进制字符串返回文件大小的最低 32 位。
</td></tr><tr><td>
val</td><td>

*十进制*</td><td>

以十进制值返回字节数。这是一个 64 位数据类型，但并非所有脚本语言都支持（例如，VBScript 不支持）。
</td></tr><tr><td>
valhex</td><td>

*字符串*</td><td>

以十六进制字符串返回字节数。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Add</td><td>

*变体*</td><td>

*无*</td><td>

将提供的值添加到此 **FileSize** 对象的值中。你可以传递 *字符串*、*int* 或 *货币* 类型，或另一个 **FileSize** 对象。部分 **FileSize** 对象是只读的，如果你尝试修改它们，它们会出错。这包括 **[Item](item.zh.md).size** 返回的对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Clone</td><td>

*无*</td><td>

*对象:***FileSize**</td><td>

克隆此 **FileSize** 对象并返回一个新对象，该对象设置为相同的值。
</td></tr><tr><td>
Compare</td><td>

*变体*</td><td>

*int*</td><td>

将提供的值与此 **FileSize** 对象的值进行比较。返回值为 **0**（相等）、**1**（大于）或 **-1**（小于）。
</td></tr><tr><td>
Div</td><td>

*变体*</td><td>

*无*</td><td>

将此 **FileSize** 对象的值除以提供的值。你可以传递 *字符串*、*int* 或 *货币* 类型，或另一个 **FileSize** 对象。部分 **FileSize** 对象是只读的，如果你尝试修改它们，它们会出错。这包括 **[Item](item.zh.md).size** 返回的对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Mult</td><td>

*变体*</td><td>

*无*</td><td>

将此 **FileSize** 对象的值乘以提供的值。你可以传递 *字符串*、*int* 或 *货币* 类型，或另一个 **FileSize** 对象。部分 **FileSize** 对象是只读的，如果你尝试修改它们，它们会出错。这包括 **[Item](item.zh.md).size** 返回的对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
Set</td><td>

*变体*</td><td>

*无*</td><td>

将 **FileSize** 设置为提供的值。你可以传递 *字符串*、*int*、// 十进制 *或* 货币 // 类型，或另一个 **FileSize** 对象。你还可以传递一个 **[Blob](blob.zh.md)**，该 Blob 恰好包含 1、2、4 或 8 个字节，在这种情况下，**[Blob](blob.zh.md)** 中包含的数据将用于形成数字。你可以通过在前面加上 **\$** 或 **0x** 来使用十六进制字符串。
如果 **FileSize** 对象是只读的，那么如果你尝试修改它，它会出错。使用 **Clone** 或 **[FSUtil](fsutil.zh.md).NewFileSize** 创建一个可以修改的新对象。
</td></tr><tr><td>
Sub</td><td>

*变体*</td><td>

*无*</td><td>

从此 **FileSize** 对象的值中减去提供的值，你可以传递 *字符串*、*int* 或 *货币* 类型，或另一个 **FileSize** 对象。请注意，**FileSize** 对象是 *无符号的*，因此该值不能低于零。部分 **FileSize** 对象是只读的，如果你尝试修改它们，它们会出错。这包括 **[Item](item.zh.md).size** 返回的对象。使用 **Clone** 方法创建一个可修改的副本。
</td></tr><tr><td>
ToBlob</td><td>

*int*</td><td>

*对象:***[Blob](blob.zh.md)**</td><td>

返回一个 **[Blob](blob.zh.md)**，其中包含表示当前值的字节。默认情况下，将把 8 个字节复制到 **[Blob](blob.zh.md)**（完整的 64 位数字），但你可以传递替代的字节数（1、2 或 4）作为参数来截断值。
</td></tr></tbody>
</table>