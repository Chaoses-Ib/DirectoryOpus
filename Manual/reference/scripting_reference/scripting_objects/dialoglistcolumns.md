# DialogListColumns

The **DialogListColumns** object lets you query or modify the columns in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) Use the **[Control](control.md).columns** property to obtain a **DialogListColumns** object.

You can enumerate this object to query the current columns. Each column is represented by a **[DialogListColumn](dialoglistcolumn.md)** object.  

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AddColumn | \<string:name\> | *int* | Adds a new column to the list view, and returns the index of the new column. |
| AutoSize | *none* | *none* | Automatically sizes all columns in the list view to fit their content. |
| DeleteColumn | \<int:index\> | *none* | Deletes the specified column. |
| GetColumnAt | \<int:index\> | *object:*  <br />**[DialogListColumn](dialoglistcolumn.md)** | Returns a **[DialogListColumn](dialoglistcolumn.md)** object representing the column in the specified position. |
| GetDisplayOrder | *none* | object:**[Vector](vector.md)** | Returns the order which the list's columns are displayed on the screen. This may differ from their natural order if you have previously changed it via **SetDisplayOrder**.  <br />The vector contains the index of each column in the order it appears. As an example, if you create a list with three columns (indexes 0, 1, 2) and move the last one (2) to the start, the returned vector will contain three integers: 2,0,1. |
| InsertColumn | \<string:name\>  <br />\<int:position\> | *int* | Inserts a new column in the list view at the specified position, and returns the index of the new column. |
| SetDisplayOrder | \<int:indexA\>  <br />\<int:indexB\>  <br />\<int:indexC\>  <br />...  <br />or  <br />\<**[Vector](vector.md)**:indexes\> | *none* | Changes the order in which the list's columns are displayed.  <br />This can be particularly useful when you want to place one or more columns before the main one, which is not possible when initially creating the columns (due to the way Windows list controls behave). The main column is special, in that it is the only one which can have a checkbox or editable label, but you may not always want it to be displayed first.  <br />You can either pass the column indexes directly as arguments, or pass a vector (or most other collection types) of integers with the same thing.  <br />As an example, if you create a list with three columns (indexes 0, 1, 2) and want to move the last column (2) to the start: *SetDisplayOrder(2,0,1)*  <br />This only changes the order the columns are displayed on the screen; the column indexes you use in your code do not change afterwards. |

