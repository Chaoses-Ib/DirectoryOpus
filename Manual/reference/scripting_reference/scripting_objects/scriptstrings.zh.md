# ScriptStrings

**ScriptStrings** 对象由 **[DOpus](dopus.zh.md).strings** 属性返回。它允许您访问通过 [字符串资源](/Manual/scripting/resources/string_resources.zh.md) 定义的任何字符串。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
langs</td><td>

*对象:***[Vector](vector.zh.md)**</td><td>

返回一个 **[Vector](vector.zh.md)** ，表示已定义字符串的语言的字符串。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Get</td><td>

\<string:name\>  
\<string:language\></td><td>

*string*</td><td>

返回由名称指定的字符串的文本。名称必须与字符串资源中使用的名称匹配。  
您可以选择提供语言名称作为第二个参数，以从特定语言检索字符串。否则，将以当前语言返回字符串。
</td></tr><tr><td>
HasLanguage</td><td>

\<string:language\></td><td>

*bool*</td><td>

如果资源中定义了指定语言的字符串，则返回 **True**。
</td></tr></tbody>
</table>