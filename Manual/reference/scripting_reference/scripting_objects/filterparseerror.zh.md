如果 **[Filter](filter.zh.md)** 对象未能解析您提供的 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 字符串，可以从 **Filter.lasterror** 属性中提取此对象，以找出出错原因。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
length</td><td>

*int*</td><td>
返回导致解析错误的标记的长度。
</td></tr><tr><td>
message</td><td>

*string*</td><td>
返回错误描述。
</td></tr><tr><td>
position</td><td>

*int*</td><td>
返回输入字符串中解析错误的位置。
</td></tr><tr><td>
token</td><td>

*string*</td><td>
返回导致解析错误的标记。
</td></tr></tbody>
</table>