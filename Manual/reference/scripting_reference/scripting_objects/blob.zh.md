一个 **Blob** 对象表示一个二进制数据块。*VBScript* 和 *JScript* 等脚本语言没有对二进制数据的内置支持 - 可以使用该对象分配一块内存，并以类似于 C 等低级语言的方式操作该对象。可以将 **Blob** 对象与 **[File](file.zh.md)** 对象结合使用，以读取或写入磁盘文件中的二进制数据。

**Blob** 对象可转换为 ActiveX 数组的两种类型，即 *SAFEARRAY*，类型为 *VT_UI1*（称为 **array**）和 *SAFEARRAY*，类型为 *VT_VARIANT*，其中每个变量都持有 *VT_UI1*（称为 **VB array**）。可以使用这两种类型中的任何一种数组初始化一个 **Blob**（在通过 **DOpusFactory.Blob** 方法或 **Blob.CopyFrom** 方法创建它时，以及在使用 **ToArray** 和 **ToVBArray** 方法将 **Blob** 转换回数组时）。这些数组类型的支持取决于脚本语言。

可以通过从 0 开始对字节偏移量进行索引来读写 **Blob** 中的各个字节。例如，*my_blob(5) = 128* 会将中该 blob 中的第六个字节的值设置为 128。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
size</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，表示此 **Blob** 的大小（以字节为单位）。
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

将此 **Blob** 的内容与另一个 **Blob**（或数组）进行比较。默认情况下，比较这两个 blob 的整个内容。可以让你配置操作的可选参数是：

to - 指定要与之进行比较的此 **Blob** 中的字节偏移量。默认为 0。 
from - 指定要在其中进行比较的源 **Blob** 中的字节偏移量。默认为 0。 
size - 指定要比较的字节数。默认为源 **Blob** 的大小。

如果这两个 blob 相同，则返回值为 **0**。**-1** 的值表示此 blob 小于其它 blob，**1** 表示此 blob 大于其它 blob。
</td></tr><tr><td>
CopyFrom</td><td>

\<<Blob:source>\>  
\<int:to\>  
\<int:from\>  
\<int:size\>

*或*  
   
\<string\>  
\<type\></td><td>

*none*</td><td>

将数据从源 **Blob**（或数组）复制到此 **Blob** 中。默认情况下，源 **Blob** 的整个内容将被完全复制到此 **Blob** 的内容。可以让你配置操作的可选参数是：

to - 指定要复制到的此 **Blob** 中的字节偏移量。默认为 0。 
from - 指定要从中复制的源 **Blob** 中的字节偏移量。默认为 0。 
size - 指定要复制的字节数。默认为源 **Blob** 的大小。

除了从另一个 **Blob** 复制外，还可以使用此方法从字符串初始化一个 **Blob**。默认情况下，**Blob** 将设置为字符串的 Unicode 形式；如果将 **"utf8"** 传递为第二个参数，它将使用字符串的 UTF8 编码形式初始化 **Blob**。

如果此 **Blob** 当前不够大，无法容纳所复制的数据，则它将自动调整大小。
</td></tr><tr><td>
Find</td><td>

\<<Blob:search>\>  
\<int:from\>  
\<int:size\></td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

在该 **Blob** 的内容中搜索另一个 **Blob**（或数组）中包含的数据。默认情况下，搜索该 **Blob** 的整个内容。可选的 **from** 参数允许你指定搜索的起始位置，而可选的 **size** 参数允许你指定在该 Blob 中搜索的数据长度。  
如果未找到搜索数据，则返回值为 -1，否则，返回从 **Blob** 数据开始的偏移量。
</td></tr><tr><td>
Free</td><td>

*none*</td><td>

*none*</td><td>

释放与此 **Blob** 关联的内存，并将大小重置为 0。相当于 *Set(0)*。
</td></tr><tr><td>
Init</td><td>

*none*</td><td>

*none*</td><td>

初始化 **Blob** 的内容（blob 中的每个字节都将设置为 0）。相当于 *Set(0)*。
</td></tr><tr><td>
Resize</td><td>

\<int:size\></td><td>

*none*</td><td>

将该 **Blob** 大小调整为指定字节数。
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

将 **Blob** 的内容设置为指定的字节值（blob 中的每个字节都将设置为该值）。默认情况下，整个 **Blob** 将受到影响。选项 *to* 参数允许你指定一个字节偏移量以作为起点，而可选 *size* 参数允许你控制受影响的字节数。
</td></tr><tr><td>
ToArray</td><td>

\<int:from\>  
\<int:size\></td><td>

VT_UI1 类型 SAFEARRAY</td><td>

将此 **Blob** 的内容转换为类型为 *VT_UI1* 的 *SAFEARRAY*。默认情况下，**Blob** 的整个内容将被复制到该数组。可以让你配置操作的可选参数是： 
from - 指定要从中复制的源 **Blob** 中的字节偏移量。默认为 0。 
size - 指定要复制的字节数。默认为源 **Blob** 的大小。
</td></tr><tr><td>
ToVBArray</td><td>

\<int:from\>  
\<int:size\></td><td>

VT_VARIANT 类型 SAFEARRAY</td><td>

将此 **Blob** 的内容转换为类型为 *VT_VARIANT* 的 *SAFEARRAY*。数组中的每个变量都包含一个 *VT_UI1*。默认情况下，**Blob** 的整个内容将被复制到该数组。可以让你配置操作的可选参数是：

from - 指定要从中复制的源 **Blob** 中的字节偏移量。默认为 0。 
size - 指定要复制的字节数。默认为源 **Blob** 的大小。
</td></tr></tbody>