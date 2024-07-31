# SortOrder

**SortOrder** 对象由 **[Format](format.zh.md).manual_sort_order** 属性返回，前提是 [手动排序模式](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md) 处于活动状态。它允许您查询和修改排序顺序。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
GetOrder</td><td>

\<string:name\></td><td>

*object:***[Vector](vector.zh.md)**</td><td>

返回一个 **[Vector](vector.zh.md)** 字符串，表示文件夹中文件当前的排序顺序。如果定义了多个手动排序顺序，您可以将特定排序顺序的名称作为参数提供给此方法。如果在没有参数的情况下调用，则默认情况下返回当前排序顺序。
</td></tr><tr><td>
SetOrder</td><td>

\<**[Vector](vector.zh.md)**:order\>  
\<string:name\></td><td>

*none*</td><td>

您可以将 **[Vector](vector.zh.md)** 字符串传递给此方法以更改当前文件夹的排序顺序。如果您定义了多个排序顺序，则可以选择将排序顺序的名称作为第二个参数提供。
</td></tr><tr><td>
ResetOrder</td><td>

\<string:name\></td><td>

*none*</td><td>

将手动排序顺序重置为当前选定的排序顺序（例如，如果文件列表标题指示它按名称排序，**ResetOrder** 将重置为文件名顺序）。如果您定义了多个排序顺序，则可以选择将排序顺序的名称作为第二个参数提供。
</td></tr></tbody>
</table>