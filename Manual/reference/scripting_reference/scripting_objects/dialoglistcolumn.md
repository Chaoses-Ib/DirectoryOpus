# DialogListColumn

The **DialogListColumn** object represents a column in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) Use the **[Control](control.md).columns** property to obtain a **[DialogListColumns](dialoglistcolumns.md)** object, and then enumerate it to obtain individual **DialogListColumn** objects. 

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
name</td><td>

*string*</td><td>
Returns or sets the column's name.
</td></tr><tr><td>
resize</td><td>

*bool*</td><td>

Set this property to **True** if you want this column to automatically resize when the list view is resized horizontally. Only one column can be set to auto-resize at a time.
</td></tr><tr><td>
sort</td><td>

*int*</td><td>

Returns **1** if the list view is currently sorted forwards by this column, **-1** if it's currently sorted backwards by this column, or **0** otherwise. Settings this property will re-sort the list.
</td></tr><tr><td>
width</td><td>

*int*</td><td>

Returns or sets the column's width in pixels. Set it to **-1** to automatically size the column to fit its content. You can automatically resize all columns at once using the [DialogListColumns](dialoglistcolumns.md)**.AutoSize** method.
</td></tr></tbody>
</table>

