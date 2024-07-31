# File

**File** 对象允许您读取和写入磁盘上的文件（或 Zip 文件、FTP 站点等）中的二进制数据。虽然 Microsoft *Scripting.FileSystemObject* 对象允许您读取和写入文件，但它只支持文本，不支持二进制数据。您还可以使用 **File** 对象修改文件的属性和时间戳。

您可以使用 **[FSUtil](fsutil.zh.md).OpenFile** 和 **[Item](item.zh.md).Open** 方法获取 **File** 对象。您可以以三种模式之一打开文件：

- *读取模式* - 您可以在 **Read** 方法的帮助下从文件中读取数据。您不能写入它或修改它的属性。
- *写入模式* - 您可以在 **Write** 方法的帮助下向文件写入数据，并且您也可以修改文件的属性。您不能从中读取数据。
- *修改模式* - 您可以在 **Read** 方法的帮助下从文件中读取数据。您不能写入它或修改它的属性。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回文件的完整路径名。
</td></tr><tr><td>
error</td><td>

*int*</td><td>

返回一个 Win32 错误代码，指示上次操作的成功或失败。如果前一次操作成功，通常为 **0**。

例如，如果您尝试使用 **FSUtil.OpenFile** 打开一个不存在的文件以进行读取，则将返回一个有效的 **File** 对象 - 但文件本身不会打开。您可以在继续使用 **File** 对象之前检查 **error** 是否返回 **0**。
</td></tr><tr><td>
path</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回文件的完整路径名，作为一个 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
size</td><td>

*对象:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，表示此文件的大小（以字节为单位）。
</td></tr><tr><td>
tell</td><td>

*对象:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，表示此文件内读写光标的当前位置（以字节为单位）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Close</td><td>

*无*</td><td>

*无*</td><td>

关闭底层文件句柄。在此调用之后，**File** 对象仍然有效，但它不能再读取或写入数据。

如果您想使用 **SetAttr** 方法修改您创建的文件的属性，您可能想要先调用 **Close**，否则文件系统将在您想要设置或不想要设置的情况下在文件上设置 *A*（压缩包）属性。

如果您想删除文件，您可能还想手动关闭文件，因为一些脚本语言（例如 *JScript*）具有延迟垃圾回收，否则可能会比您预期的更长时间保持文件句柄打开。
</td></tr><tr><td>
Read</td><td>

\<<blob:target>\>  
\<int:size\></td><td>

*int* 或  
*对象:***[Blob](blob.zh.md)**</td><td>

从文件读取数据。如果您提供一个 *target* **[Blob](blob.zh.md)** 作为第一个参数，数据将存储在该 **Blob** 中。否则，将自动创建一个 **Blob**。  
可选的 *size* 参数指定要读取的字节数 - 默认行为是读取文件的剩余内容。  
每次调用最多可以读取 1 GB（1073741824 字节），无论是否指定或隐式指定大小。要读取更大的文件，您必须多次调用 **Read**。  
如果您提供一个 **Blob**，则返回值表示从文件成功读取的字节数。如果没有提供 **Blob**，则返回值是自动创建的 **Blob** - 您可以使用它的 **size** 属性来发现读取的字节数。  
如果 **Read** 返回零（或空 **Blob**），您可以使用 **error** 属性测试是否出现错误，或者文件是否 simply had no more data.
</td></tr><tr><td>
Seek</td><td>

\<int:delta\>  
\<string:method\></td><td>

*对象:***[FileSize](filesize.zh.md)**</td><td>

移动此文件内的读写光标。*delta* 参数指定要移动的字节数 - 如何解释它取决于可选的 *method* 参数：

*b* - 相对于文件开头移动  
*e* - 相对于文件结尾移动  
*c* - 相对于当前位置移动（这是默认方法）

返回值是一个 **[FileSize](filesize.zh.md)** 对象，指示新的光标位置。
</td></tr><tr><td>
SetAttr</td><td>

*对象:***[FileAttr](fileattr.zh.md)**  
或 \<string:attributes\></td><td>

*bool*</td><td>

修改此文件的属性。您可以传递一个表示要设置的属性的字符串，或者传递一个 **[FileAttr](fileattr.zh.md)** 对象。使用字符串时，有效的属性为：

*a* - 压缩包  
*c* - 压缩  
*e* - 加密  
*h* - 隐藏  
*n* - 正常  
*r* - 只读  
*s* - 系统  
p - 固定  
i - 非内容索引

请注意，*c* 和 *e* 属性不能同时设置。

当您传递字符串时，您还可以使用 **+** 和 **-** 来打开或关闭某些属性，而不会影响其它属性。例如，**SetAttr("-r")** 将关闭只读属性。

返回值为 **True**，如果操作成功。
</td></tr><tr><td>
SetTime</td><td>

\<date:modify\>  
\<date:create\>  
\<date:access\></td><td>

*bool*</td><td>

修改一个或多个文件的时间戳。*create* 和 *access* 参数是可选的。如果您希望指定一个时间戳没有变化，请指定 **0**。

时间戳指定为本地时间 - 使用 **SetTimeUTC** 将它们指定为 UTC。

返回值为 **True**，如果操作成功。
</td></tr><tr><td>
SetTimeUTC</td><td>

\<date:modify\>  
\<date:create\>  
\<date:access\></td><td>

*bool*</td><td>

修改一个或多个文件的时间戳。*create* 和 *access* 参数是可选的。如果您希望指定一个时间戳没有变化，请指定 **0**。

时间戳指定为 UTC 时间 - 使用 **SetTime** 将它们指定为本地时间。

返回值为 **True**，如果操作成功。
</td></tr><tr><td>
Truncate</td><td>

*无*</td><td>

*bool*</td><td>

在写入光标的当前位置截断文件。您可以将此与 **Seek** 方法结合使用，以在磁盘上预分配文件的空间，从而提高性能（即，寻求文件的最终大小，在该点截断，然后返回到起点并写入数据）。

返回值为 **True**，如果操作成功。
</td></tr><tr><td>
Write</td><td>

\<<blob:source>\> 或 \<string:source\>  
\<int:from\>  
\<int:size\></td><td>
int</td><td>

将指定 **Blob**（或数组）或 *string* 中的数据写入文件。  
默认情况下，将写入 **Blob** 的所有内容，但您可以使用可选的 *from* 参数指定源字节偏移量，使用 *size* 参数指定要写入的字节数。  
每次调用最多可以写入 1 GB（1073741824 字节），无论是否指定或隐式指定大小。要写入更大的数据量，您必须多次调用 **Write**。  
如果您提供 *string* 而不是 Blob，则该字符串将自动编码为 UTF-8。  
返回值表示成功写入文件的字节数。  
如果 **Write** 返回零，您可以使用 **error** 属性测试是否出现错误，或者是否 simply had no data to write（例如，指定的 **Blob** 为空）。
</td></tr></tbody>
</table>