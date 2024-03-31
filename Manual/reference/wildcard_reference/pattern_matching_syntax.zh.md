# 模式匹配语法

很多 Opus 函数中都可以使用通配符模式，其中包括：

- 使用 [查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md) 工具搜索文件时（匹配文件名、文件内容或元数据）
- 对显示范围内外的文件进行 [过滤](/Manual/basic_concepts/searching_and_filtering/README.zh.md) 时
- 在文件列表中 [选择](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md) 文件时
- 对复制或移动等 [文件操作](/Manual/file_operations/filtered_operations/README.zh.md) 进行过滤时

除了 [正则表达式](regular_expression_syntax.zh.md)，Opus 还支持一种更简单的通配符系统，称为 *标准模式匹配* 系统。在使用通配符时，可以指定一个由文字和特殊 *通配符标记* 混合组成的模式。每个标记都用来匹配目标字符串中的一个或多个字符。举一个简单的例子，模式 **\*.doc** 匹配任何以文字字符 *.doc* 结尾的内容（换句话说，匹配文档文件）。

<table>
<thead><tr><th>
标记</th><th>
描述
</th></tr></thead><tbody><tr><td>

**  \#**</td><td>

紧跟 **\#** 处的字符或表达式重复 0 次或多次。

例如：  
**a#xb** 匹配 *ab*, *axb*, *axxb*, *axxxb* 等。  
**a#(xyz)b** 匹配 *ab*, *axyzb*, *axyzxyzb* 等。
</td></tr><tr><td>

**  ?**</td><td>

匹配任意单个字符。

例如：  
**a?b** 匹配 *aab*, *abb*, *acb*, *adb* 等。它 **不** 匹配 *ab*。
</td></tr><tr><td>

**  \|**</td><td>

用来分隔多个表达式，其中任何一个都可以匹配（实际上是一个 **或** 运算符）。

例如：  
**a(x\|y\|z)b** 匹配 *axb*, *ayb* 和 *azb*。  
**\*.(gif\|bmp\|jpg)** 匹配任何以 *.gif*, *.bmp* 或 *.jpg* 结尾的内容。
</td></tr><tr><td>

**  ~**</td><td>

这是 **非** 运算符，它对后面的表达式取反。

例如：  
**~(\*.doc)** 匹配除以 *.doc* 结尾的内容之外的任何内容  
**~(\*.(gif\|bmp))** 匹配除以 *.gif* 或 *.bmp* 结尾的内容之外的任何内容
</td></tr><tr><td>

**  ()**</td><td>

括号用来将多个字符组合成一个表达式。如果我们取上面的 **a#(xyz)b** 为例，括号用来将 *xyz* 组成一个表达式。如果没有括号（即 **a#xyzb**），将认为只有 *x* 紧跟在 **\#** 字符后面 - *yzb* 将被当作文字对待。  
可以在括号内嵌套括号（如上 **~** 的示例）来将多个表达式组合成一个更大的表达式。

例如：  
**NEW-((\*.doc)\|(\*\_backup\_\*))** 匹配所有以 *NEW-* 开头并以 *.doc* 结尾或后跟 *\_backup\_* 字符串的内容。
</td></tr><tr><td>

**  \[\]**</td><td>

匹配指定字符集中的任意单个字符。  
可以将字符集指定为单个字符（例如 **\[abdfg\]**）或字符范围（例如 **\[a-j\]**）或多个范围。

例如：  
**\[abc\]** 匹配 *a*, *b* 或 *c*  
**\[af-j\]** 匹配 *a*, *f*, *g*, *h*, *i* 或 *j*  
**\[a-dh-kq-\]** 匹配 *a*, *b*, *c*, *d*, *h*, *i*, *j*, *k* 或从 *q* 开始的任意字符  
**IMGP#\[0-9\].jpg** 匹配 *IMGP0158.jpg*（或任何其他数字）。
</td></tr><tr><td>

**  \[~\]**</td><td>

匹配指定字符集中的 **任意** 字符。有关如何定义集合的信息，请参阅 **\[\]**。

例如：  
**\[~pqr\]** 匹配除 *p*, *q* 或 *r* 之外的任何字符
</td></tr><tr><td>

** ** \*</td><td>

匹配任意数量的字符，包括零个。这是 **\#?** 的同义词。  
**\*.doc** 等价于 **\#?.doc**。  
例如：  
**abc\*xyz.\*q** 匹配以 *abc* 开头、后跟 *xyz* 且以以 *q* 结尾的任意文件扩展名的任何文件名。
</td></tr><tr><td>

**'**</td><td>

称作 *转义字符* 的撇号。

在模式字符串中，任何不是通配符标记的字符都视为文字字符 - 文字字符必须与目标字符串中的字符完全匹配。但是，如果您实际上是想将通配符标记用作文字字符本身，则必须在通配符标记前加撇号对其进行转义。

例如：  
**a#xb** 匹配 *ab*, *axb*, *axxb*, *axxxb* 等，如上所见  
**a'#xb** 将仅匹配 *a#xb*
</td></tr><tr><td>

**grp:**</td><td>

当使用通配符匹配文件名时，这是引用 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 定义的所有文件扩展名的简写方式。  
例如，**Images** 组可能包含文件扩展名 *.jpg*, *.bmp* 和 *.gif*。如果您希望命令自动选择这些类型的文件，可以使用以下命令：  
**Select \*.(jpg\|bmp\|gif)**  
更好的办法是使用 **grp:** 标记自动包含该组中的所有文件扩展名：  
**Select grp:Images**

这样既便于阅读（和输入！），而且如果您将来会在这个组中添加或删除文件类型，那么引用该组的任何模式都会自动反映新的更改。

例如：  
**(grp:Images\|grp:Documents)** 匹配 **Images** 或 **Documents** 文件类型组中的任何文件
</td></tr></tbody>
</table>