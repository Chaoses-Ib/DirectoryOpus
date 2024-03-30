# SortOrder

The **SortOrder** object is returned by the **[Format](format.md).manual_sort_order** property if [manual sort mode](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is active. It lets you query and modify the sort order.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
GetOrder</td><td>
\<string:name\></td><td>

*object:***[Vector](vector.md)**</td><td>

Returns a **[Vector](vector.md)** of strings representing the current sort order of files in the folder. If multiple manual sort orders have been defined, you can provide the name of a specific sort order as an argument to this method. If called with no arguments it returns the current sort order by default.
</td></tr><tr><td>
SetOrder</td><td>

\<**[Vector](vector.md)**:order\>  
\<string:name\></td><td>

*none*</td><td>

You can pass this method a **[Vector](vector.md)** of strings to change the sort order of the current folder. You can optionally provide the name of a sort order as the second parameter if you’ve got more than one sort order defined.
</td></tr><tr><td>
ResetOrder</td><td>
\<string:name\></td><td>

*none*</td><td>

Resets the manual sort order to the currently selected sort order (e.g. if the file display header indicates that it is sorted by name, **ResetOrder** would reset to filename order). You can optionally provide the name of a sort order as the second parameter if you’ve got more than one sort order defined.
</td></tr></tbody>
</table>

