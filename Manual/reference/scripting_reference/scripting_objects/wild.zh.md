# Wild

**Wild** 对象允许脚本访问 Opus 内置的模式匹配功能。尽管大多数 ActiveX 脚本语言都有自己的模式匹配支持（通常是通过某种正则表达式系统），但您可能希望使用 Opus 提供的模式匹配功能，以便与内部 Opus 函数保持一致。

您可以使用 **[FSUtil](fsutil.zh.md).NewWild** 方法创建 **Wild** 对象。要使用 **Wild** 对象，您必须首先指定要匹配的模式（此步骤称为“解析模式”。您可以在创建时或稍后使用 **Parse** 方法进行此操作。一旦对象具有模式，您就可以调用 **Match** 方法来测试字符串是否与模式匹配。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回 Wild 对象中的当前模式
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
EscapeString</td><td>

\<字符串:输入\>  
\<字符串:类型\></td><td>

*字符串*</td><td>

转义输入字符串中的所有通配符并返回结果。例如，"**the \* 'dog' said** \*" 将被转换为 "**the '\* ''dog'' said '**\*"。

可选的类型参数允许您指定转换：  
*none*: 转义在 [标准模式匹配](../../wildcard_reference/pattern_matching_syntax.zh.md) 中使用的字符  
**r**: 转义在 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 中使用的字符  
**b**: 将所有反斜杠加倍  
**n**: 将所有反斜杠加倍，这些反斜杠位于字母 '**n**' 之前  
请注意，这些模式不能组合。
</td></tr><tr><td>
Match</td><td>

\<字符串:测试\></td><td>

*布尔*</td><td>

将指定的字符串与之前解析的模式进行比较，如果匹配，则返回 **True**。
</td></tr><tr><td>
Parse</td><td>

\<字符串:模式\>  
\<字符串:标志\></td><td>

*布尔*</td><td>

解析提供的模式。标志字符串是可选的 - 如果提供，它必须是一个字符串，包含以下一个或多个字符：

**c** - 区分大小写（否则模式匹配不区分大小写）  
**d** - 仅限 DOS（仅支持标准 MS-DOS 通配符）  
**f** - 文件名模式（对匹配文件名进行特殊处理）  
**r** - 正则表达式（否则使用 [标准模式匹配](../../wildcard_reference/pattern_matching_syntax.zh.md)）
</td></tr></tbody>
</table>