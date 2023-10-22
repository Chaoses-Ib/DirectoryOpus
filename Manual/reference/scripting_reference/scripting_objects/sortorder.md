# SortOrder

The **SortOrder** object is returned by the **[Format](format.md).manual_sort_order** property if [manual sort mode](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is active. It lets you query and modify the sort order.

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| GetOrder | \<string:name\> | *object:***[Vector](vector.md)** | Returns a **[Vector](vector.md)** of strings representing the current sort order of files in the folder. If multiple manual sort orders have been defined, you can provide the name of a specific sort order as an argument to this method. If called with no arguments it returns the current sort order by default. |
| SetOrder | \<**[Vector](vector.md)**:order\>  <br />\<string:name\> | *none* | You can pass this method a **[Vector](vector.md)** of strings to change the sort order of the current folder. You can optionally provide the name of a sort order as the second parameter if you’ve got more than one sort order defined. |
| ResetOrder | \<string:name\> | *none* | Resets the manual sort order to the currently selected sort order (e.g. if the file display header indicates that it is sorted by name, **ResetOrder** would reset to filename order). You can optionally provide the name of a sort order as the second parameter if you’ve got more than one sort order defined. |

