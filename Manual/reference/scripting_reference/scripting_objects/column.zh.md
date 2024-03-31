# 列

**Column** 对象表示标签页中显示的信息列（例如，名称、大小、属性等）。可以从 **[Format](format.zh.md).columns** 属性检索 **Column** 对象的集合。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*<默认值>*</td><td>

*string*</td><td>
返回列的名称。
</td></tr><tr><td>
autosize</td><td>

*bool*</td><td>

如果列宽设置为 *auto*，则返回 **True**。
</td></tr><tr><td>
collapse</td><td>

*bool*</td><td>

如果列宽设置为 *collapse*，则返回 **True**。
</td></tr><tr><td>
expand</td><td>

*bool*</td><td>

如果列宽设置为 *expand*，则返回 **True**。
</td></tr><tr><td>
fill</td><td>

*bool*</td><td>

如果列宽设置为 *fill*，则返回 **True**。
</td></tr><tr><td>
header</td><td>

*string*</td><td>
返回文件窗口列标题中显示的列的名称。
</td></tr><tr><td>
label</td><td>

*string*</td><td>

返回 *文件夹选项* 对话框中 *列* 标签页中显示的列的名称。
</td></tr><tr><td>
max</td><td>

*int* 或 *string*</td><td>

返回列的最大宽度（以像素为单位），如果最大值设置为 *fill*，则返回字符串 "fill"。
</td></tr><tr><td>
min</td><td>

*int*</td><td>
返回列的最小宽度（以像素为单位）。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回列的名称。
</td></tr><tr><td>
reverse</td><td>

*bool*</td><td>

如果列的排序方向为反向，则返回 **True**。
</td></tr><tr><td>
sort</td><td>

*int*</td><td>
返回列的排序顺序（例如，主排序字段为 1，辅助排序字段为 2，依此类推）。如果显示未按此列排序，则返回 0。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
返回列当前的显示宽度（以像素为单位）。
</td></tr></tbody>
</table>