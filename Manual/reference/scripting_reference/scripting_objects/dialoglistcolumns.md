# DialogListColumns

The **DialogListColumns** object lets you query or modify the columns in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) Use the **[Control](control.md).columns** property to obtain a **DialogListColumns** object.

You can enumerate this object to query the current columns. Each column is represented by a **[DialogListColumn](dialoglistcolumn.md)** object.  

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>
\<string:name\></td><td>

*int*</td><td>
Adds a new column to the list view, and returns the index of the new column.
</td></tr><tr><td>
AutoSize</td><td>

*none*</td><td>

*none*</td><td>
Automatically sizes all columns in the list view to fit their content.
</td></tr><tr><td>
DeleteColumn</td><td>
\<int:index\></td><td>

*none*</td><td>
Deletes the specified column.
</td></tr><tr><td>
GetColumnAt</td><td>
\<int:index\></td><td>

*object:*  
**[DialogListColumn](dialoglistcolumn.md)**</td><td>

Returns a **[DialogListColumn](dialoglistcolumn.md)** object representing the column in the specified position.
</td></tr><tr><td>
GetDisplayOrder</td><td>

*none*</td><td>

object:**[Vector](vector.md)**</td><td>

Returns the order which the list's columns are displayed on the screen. This may differ from their natural order if you have previously changed it via **SetDisplayOrder**.  
The vector contains the index of each column in the order it appears. As an example, if you create a list with three columns (indexes 0, 1, 2) and move the last one (2) to the start, the returned vector will contain three integers: 2,0,1.
</td></tr><tr><td>
InsertColumn</td><td>
\<string:name\>  
\<int:position\></td><td>

*int*</td><td>
Inserts a new column in the list view at the specified position, and returns the index of the new column.
</td></tr><tr><td>
SetDisplayOrder</td><td>

\<int:indexA\>  
\<int:indexB\>  
\<int:indexC\>  
...  
or  
\<**[Vector](vector.md)**:indexes\></td><td>

*none*</td><td>

Changes the order in which the list's columns are displayed.  
This can be particularly useful when you want to place one or more columns before the main one, which is not possible when initially creating the columns (due to the way Windows list controls behave). The main column is special, in that it is the only one which can have a checkbox or editable label, but you may not always want it to be displayed first.  
You can either pass the column indexes directly as arguments, or pass a vector (or most other collection types) of integers with the same thing.  
As an example, if you create a list with three columns (indexes 0, 1, 2) and want to move the last column (2) to the start: *SetDisplayOrder(2,0,1)*  
This only changes the order the columns are displayed on the screen; the column indexes you use in your code do not change afterwards.
</td></tr></tbody>
</table>

