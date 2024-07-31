# Blob

一个 **Blob** 对象代表一个二进制数据的块。像 *VBScript* 和 *JScript* 这样的脚本语言没有内置的二进制数据支持 - 这个对象可以用来分配一块内存并以类似于 C 这样的低级语言的方式操作它。您可以将 **Blob** 对象与 **[File](file.zh.md)** 对象结合使用，从磁盘文件读取或写入二进制数据。

**Blob** 对象可以转换为两种类型的 ActiveX 数组，并且可以从两种类型的 ActiveX 数组转换 - 一种是 *SAFEARRAY* 类型 *VT_UI1*（称为 **数组**），另一种是 *SAFEARRAY* 类型 *VT_VARIANT*，每个变体都包含一个 *VT_UI1*（称为 **VB 数组**）。您可以使用这两种类型的数组之一初始化一个 **Blob**（在通过 **DOpusFactory.Blob** 方法创建它时或使用 **Blob.CopyFrom** 方法时），也可以使用 **ToArray** 和 **ToVBArray** 方法将一个 **Blob** 转换回一个数组。对这些数组类型的支持取决于脚本语言。

您可以通过索引从 0 开始的字节偏移量来读取和写入 **Blob** 中的单个字节。例如，*my_blob(5) = 128* 将把 blob 中第六个字节的值设置为 128。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
size</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，表示此 **Blob** 的大小（以字节为单位）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Compare</td><td>

\<<Blob:source>\>  
\<int:to\>  
\<int:from\>  
\<int:size\></td><td>

*int*</td><td>

将此 **Blob** 的内容与另一个 **Blob**（或数组）进行比较。默认情况下，将比较两个 blob 的全部内容。允许您配置操作的可选参数是：

to - 指定要比较的此 **Blob** 中的字节偏移量。默认值为 0。  
from - 指定要比较的源 **Blob** 中的字节偏移量。默认值为 0。  
size - 指定要比较的字节数。默认值为源 **Blob** 的全部大小。

如果两个 blob 相同，则返回值为 **0**。**-1** 的值表示此 blob 小于另一个 blob，**1** 的值表示此 blob 大于另一个 blob。
</td></tr><tr><td>
CopyFrom</td><td>

\<<Blob:source>\>  
\<int:to\>  
\<int:from\>  
\<int:size\>

*或者*  
   
\<string\>  
\<type\></td><td>

*none*</td><td>

将数据从源 **Blob**（或数组）复制到此 **Blob** 中。默认情况下，将把源 **Blob** 的全部内容复制到此 blob 的顶部。允许您配置操作的可选参数是：

to - 指定要复制到的此 **Blob** 中的字节偏移量。默认值为 0。  
from - 指定要复制的源 **Blob** 中的字节偏移量。默认值为 0。  
size - 指定要复制的字节数。默认值为源 **Blob** 的全部大小。

除了从另一个 **Blob** 复制之外，您还可以使用此方法从字符串初始化一个 **Blob**。默认情况下，**Blob** 将设置为字符串的 Unicode 形式；如果您将 **"utf8"** 作为第二个参数传递，它将使用 UTF8 编码形式的字符串初始化 **Blob**。

如果此 **Blob** 当前不够大，无法容纳复制的数据，它将自动调整大小。
</td></tr><tr><td>
Find</td><td>

\<<Blob:search>\>  
\<int:from\>  
\<int:size\></td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

在 此 **Blob** 的内容中搜索另一个 **Blob**（或数组）中包含的数据。默认情况下，将搜索此 **Blob** 的全部内容。可选的 **from** 参数允许您指定搜索的起始位置，可选的 **size** 参数允许您指定在此 Blob 中要搜索的数据的长度。  
如果未找到搜索数据，则返回值为 -1，否则返回从 **Blob** 数据开头处的偏移量。
</td></tr><tr><td>
Free</td><td>

*none*</td><td>

*none*</td><td>

释放与此 **Blob** 关联的内存，并将大小重置为 0。
</td></tr><tr><td>
Init</td><td>

*none*</td><td>

*none*</td><td>

初始化 **Blob** 的内容（blob 中的每个字节都将设置为 0）。等效于 *Set(0)*。
</td></tr><tr><td>
Resize</td><td>

\<int:size\></td><td>

*none*</td><td>

将 **Blob** 的大小调整为指定的字节数。
</td></tr><tr><td>
Reverse</td><td>

*none*</td><td>

*none*</td><td>

反转 **Blob** 的内容。
</td></tr><tr><td>
Set</td><td>

\<byte:value\>  
\<int:to\>  
\<int:size\></td><td>

*none*</td><td>

将 **Blob** 的内容设置为指定的字节值（blob 中的每个字节都将设置为该值）。默认情况下，将影响整个 **Blob**。可选的 *to* 参数允许您指定要开始的字节偏移量，可选的 *size* 参数允许您控制受影响的字节数。
</td></tr><tr><td>
ToArray</td><td>

\<int:from\>  
\<int:size\></td><td>

SAFEARRAY of  
VT_UI1</td><td>

将此 **Blob** 的内容转换为类型为 *VT_UI1* 的 *SAFEARRAY*。默认情况下，将把 **Blob** 的全部内容复制到数组中。允许您配置操作的可选参数是：  
from - 指定要复制的源 **Blob** 中的字节偏移量。默认值为 0。  
size - 指定要复制的字节数。默认值为源 **Blob** 的全部大小。
</td></tr><tr><td>
ToVBArray</td><td>

\<int:from\>  
\<int:size\></td><td>

SAFEARRAY of  
VT_VARIANT</td><td>

将此 **Blob** 的内容转换为类型为 *VT_VARIANT* 的 *SAFEARRAY*。数组中的每个变体都包含一个 *VT_UI1*。默认情况下，将把 **Blob** 的全部内容复制到数组中。允许您配置操作的可选参数是：

from - 指定要复制的源 **Blob** 中的字节偏移量。默认值为 0。  
size - 指定要复制的字节数。默认值为源 **Blob** 的全部大小。
</td></tr></tbody>
</table>