# DialogListColumn

The **DialogListColumn** object represents a column in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) Use the **[Control](control.md).columns** property to obtain a **[DialogListColumns](dialoglistcolumns.md)** object, and then enumerate it to obtain individual **DialogListColumn** objects. 

| Property Name | Return Type | Description |
| --- | --- | --- |
| name | *string* | Returns or sets the column's name. |
| resize | *bool* | Set this property to **True** if you want this column to automatically resize when the list view is resized horizontally. Only one column can be set to auto-resize at a time. |
| sort | *int* | Returns **1** if the list view is currently sorted forwards by this column, **-1** if it's currently sorted backwards by this column, or **0** otherwise. Settings this property will re-sort the list. |
| width | *int* | Returns or sets the column's width in pixels. Set it to **-1** to automatically size the column to fit its content. You can automatically resize all columns at once using the [DialogListColumns](dialoglistcolumns.md)**.AutoSize** method. |

