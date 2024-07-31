# Column

**Column** 对象表示在标签页中显示的信息列（例如，名称、大小、属性等）。可以通过 **[Format](format.zh.md).columns** 属性检索 **Column** 对象的集合。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回列的名称。
</td></tr><tr><td>
autosize</td><td>

*布尔*</td><td>

如果列宽度设置为 *自动*，则返回 **True**。
</td></tr><tr><td>
collapse</td><td>

*布尔*</td><td>

如果列宽度设置为 *折叠*，则返回 **True**。
</td></tr><tr><td>
expand</td><td>

*布尔*</td><td>

如果列宽度设置为 *扩展*，则返回 **True**。
</td></tr><tr><td>
fill</td><td>

*布尔*</td><td>

如果列宽度设置为 *填充*，则返回 **True**。
</td></tr><tr><td>
header</td><td>

*字符串*</td><td>
返回在文件窗口列标题中显示的列名称。
</td></tr><tr><td>
label</td><td>

*字符串*</td><td>

返回在 *文件夹选项* 对话框中的 *列* 标签页中显示的列名称。
</td></tr><tr><td>
max</td><td>

*整数* 或 *字符串*</td><td>

返回列的最大宽度（以像素为单位），如果最大宽度设置为 *填充*，则返回字符串 "fill"。
</td></tr><tr><td>
min</td><td>

*整数*</td><td>
返回列的最小宽度（以像素为单位）。
</td></tr><tr><td>
name</td><td>

*字符串*</td><td>
返回列的名称。
</td></tr><tr><td>
reverse</td><td>

*布尔*</td><td>

如果列的排序方向反转，则返回 **True**。
</td></tr><tr><td>
sort</td><td>

*整数*</td><td>
返回列的排序顺序（例如，主要排序字段为 1，次要排序字段为 2 等）。如果显示未按此列排序，则返回 0。
</td></tr><tr><td>
width</td><td>

*整数*</td><td>
返回列的当前显示宽度（以像素为单位）。
</td></tr></tbody>
</table>