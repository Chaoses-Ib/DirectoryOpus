**SortOrder**对象由**[格式](format.zh.md)。manual_sort_order**属性返回，如果[手动排序模式](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md)处于活动状态。它允许你查询和修改排序顺序。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
GetOrder</td><td>

\<字符串:名称\></td><td>

*对象:***[向量](vector.zh.md)**</td><td>

返回**[向量](vector.zh.md)**，该向量由表示文件夹中文件当前排序顺序的字符串组成。如果已经定义了多个手动排序顺序，你可以向此方法提供一个特定排序顺序的名称作为参数。如果在不带任何参数的情况下调用它，则它默认返回当前排序顺序。
</td></tr><tr><td>
SetOrder</td><td>

\<**[向量](vector.zh.md)**:order\>  
\<字符串:名称\></td><td>

*无*</td><td>

你可以向此方法传递**[向量](vector.zh.md)**字符串来更改当前文件夹的排序顺序。如果已经定义了多个排序顺序，你还可以提供排序顺序的名称作为第二个参数。
</td></tr><tr><td>
ResetOrder</td><td>

\<字符串:名称\></td><td>

*无*</td><td>

将手动排序顺序重置为当前选定的排序顺序（例如，如果文件列表标题指示它按名称进行排序，则**ResetOrder**会重置为文件名顺序）。如果已经定义了多个排序顺序，你还可以提供排序顺序的名称作为第二个参数。
</td></tr></tbody>
</table>