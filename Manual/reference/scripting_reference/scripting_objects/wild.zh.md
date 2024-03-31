# 工具

**Wild** 对象允许脚本访问 Opus 中的内置模式匹配函数。虽然大多数 ActiveX 脚本语言都有自己的模式匹配支持（通常通过某种形式的正则表达式系统），但出于与 Opus 内部函数一致的目的，您可能希望使用 Opus 提供的那个。

可以使用 **[FSUtil](fsutil.zh.md).NewWild** 方法创建 **Wild** 对象。要使用 **Wild** 对象，您必须先向其提供要匹配的模式（此步骤称为“解析模式”）。在创建对象时或稍后使用 **Parse** 方法执行此操作。对象一旦有了模式，您可以调用 **Match** 方法来针对模式测试字符串。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回 Wild 对象中的当前模式。
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

\<字符串：输入\>  
\<字符串：类型\></td><td>

*字符串*</td><td>

转义输入字符串中的所有通配符并返回结果。例如，“**the \* 'dog' said** \*" 会转换为 “**the '\* ''dog'' said '**\*”。

可选的类型参数可以指定转换：  
*无*：转义 [标准模式匹配](../../wildcard_reference/pattern_matching_syntax.zh.md) 中使用的字符  
**r**: 转义 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 中使用的字符   
**b**: 双倍所有反斜杠  
**n**: 双倍 **‘n’** 字母前的所有反斜杠  
请注意，这些模式不能组合。
</td></tr><tr><td>
Match</td><td>

\<字符串：测试\></td><td>

*布尔值*</td><td>

将指定字符串与之前解析的模式进行比较，如果匹配，则返回 **True**。
</td></tr><tr><td>
Parse</td><td>

\<字符串：模式\>  
\<字符串：标志\></td><td>

*布尔值*</td><td>

解析提供的模式。flags 字符串是可选的——如果提供，它必须是一个字符串，包含以下一个或多个字符：

**c** - 区分大小写（否则模式匹配不区分大小写）   
**d** - 仅限 DOS（仅支持 MS-DOS 通配符）  
**f** - 文件名模式（匹配文件名时的特殊处理）  
**r** - 正则表达式（否则使用 [标准模式匹配](../../wildcard_reference/pattern_matching_syntax.zh.md)）
</td></tr></tbody>
</table>