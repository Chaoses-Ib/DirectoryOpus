# 模式匹配语法

通配符模式可用于 Opus 中的许多函数，包括：

- 使用 [查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md) 工具搜索文件时（匹配文件名或文件内容或元数据）
- 在文件列表中[过滤](/Manual/basic_concepts/searching_and_filtering/README.zh.md)文件时
- 在文件列表中[选择](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md)文件时
- [过滤文件操作](/Manual/file_operations/filtered_operations/README.zh.md)（如复制或移动）时

除了[正则表达式](regular_expression_syntax.zh.md)之外，Opus 还支持更简单的通配符系统，称为*标准模式匹配*系统。使用通配符时，您需要指定一个由文本和特殊**通配符**混合而成的模式。每个标记用于匹配目标字符串中的一个或多个字符。举个简单的例子，模式 **\*.doc** 匹配任何以文本 *.doc* 结尾的内容（换句话说，就是文档文件）。

<table>
<thead><tr><th>
标记</th><th>
说明
</th></tr></thead><tbody><tr><td>

**\#**</td><td>

**\#** 后面的字符或表达式重复 0 次或多次。

例如：  
**a#xb** 匹配 *ab*、*axb*、*axxb*、*axxxb* 等。  
**a#(xyz)b** 匹配 *ab*、*axyzb*、*axyzxyzb* 等。
</td></tr><tr><td>

**?**</td><td>

匹配任意单个字符。

例如：  
**a?b** 匹配 *aab*、*abb*、*acb*、*adb* 等。它**不**匹配 *ab*。
</td></tr><tr><td>

**\|**</td><td>

用于分隔多个表达式，其中任何一个都可以匹配（实际上是一个**或**运算符）。

例如：  
**a(x\|y\|z)b** 匹配 *axb*、*ayb* 和 *azb*。  
**\*.(gif\|bmp\|jpg)** 匹配任何以 *.gif*、*.bmp* 或 *.jpg* 结尾的内容。
</td></tr><tr><td>

**~**</td><td>

这是**非**运算符，它否定后面的表达式。

例如：  
**~(\*.doc)** 匹配任何不以 *.doc* 结尾的内容  
**~(\*.(gif\|bmp))** 匹配任何不以 *.gif* 或 *.bmp* 结尾的内容
</td></tr><tr><td>

**()**</td><td>

括号用于将多个字符组合成一个表达式。以上面的 **a#(xyz)b** 为例，括号用于将 *xyz* 组合成一个表达式。如果没有括号（即 **a#xyzb**），则只有 *x* 会被视为跟在 **\#** 字符之后 - *yzb* 将被视为文本。  
括号可以嵌套（如上面的 **~** 示例），以将多个表达式组合成一个更大的表达式。

例如：  
**NEW-((\*.doc)\|(\*\_backup\_\*))** 匹配以 *NEW-* 开头并以 *.doc* 结尾或后跟字符串 *\_backup\_* 的任何内容。
</td></tr><tr><td>

**\[\]**</td><td>

匹配指定字符集中的任何单个字符。  
您可以将字符集指定为单个字符（例如 **\[abdfg\]**）或字符范围（例如 **\[a-j\]**）或多个范围。

例如：  
**\[abc\]** 匹配 *a*、*b* 或 *c*  
**\[af-j\]** 匹配 *a*、*f*、*g*、*h*、*i* 或 *j*  
**\[a-dh-kq-\]** 匹配 *a*、*b*、*c*、*d*、*h*、*i*、*j*、*k* 或 *q* 之后的任何字符  
**IMGP#\[0-9\].jpg** 匹配 *IMGP0158.jpg*（或任何其它数字）。
</td></tr><tr><td>

**\[~\]**</td><td>

匹配指定字符集中**不**存在的任何字符。有关如何定义集合的信息，请参阅 **\[\]**。

例如：  
**\[~pqr\]** 匹配除 *p*、*q* 或 *r* 之外的任何字符
</td></tr><tr><td>

**\***</td><td>

匹配任意数量的字符，包括零个字符。这是 **\#?** 的同义词。  
**\*.doc** 等价于 **\#?.doc**。  
例如：  
**abc\*xyz.\*q** 匹配以 *abc* 开头、以 *xyz* 结尾并以 *q* 结尾的任何文件扩展名的任何文件名。
</td></tr><tr><td>

**'**</td><td>

撇号称为*转义字符*。

模式字符串中不是通配符的任何字符都将被视为文本 - 文本必须与目标字符串中的字符完全匹配。但是，如果确实希望将通配符用作文本本身，则必须通过在其前面添加撇号来对其进行转义。

例如：  
如上所述，**a#xb** 匹配 *ab*、*axb*、*axxb*、*axxxb* 等。  
**a'#xb** 将只匹配 *a#xb*
</td></tr><tr><td>

**grp:**</td><td>

使用通配符匹配文件名时，这是一种引用由 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 定义的所有文件扩展名的简写方法。  
例如，**Images**组可能包含文件扩展名 *.jpg*、*.bmp* 和 *.gif*。如果您希望某个命令自动选择这些类型的文件，可以使用以下命令：  
**Select \*.(jpg\|bmp\|gif)**  
更好的方法是使用 **grp:** 标记自动包含该组中的所有文件扩展名：  
**Select grp:Images**

这更容易阅读（和输入！），而且如果您曾经在相关组中添加或删除文件类型，则任何引用该组的模式都将自动反映新的更改。

例如：  
**(grp:Images\|grp:Documents)** 匹配**Images**或**Documents**文件类型组中的任何文件
</td></tr></tbody>
</table>