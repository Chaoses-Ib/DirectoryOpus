# DialogListItem

The **DialogListItem** object represents an item in a *combo box* or *list box* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](control.md).GetItemAt** and **[Control](control.md).GetItemByName** methods.

| Property Name | Return Type | Description |
| --- | --- | --- |
| bg | *string* | Set or query the color used for the background (fill) of this item. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal).  <br />Currently only items in *list view* controls are supported for this property. |
| checked | *int* | For a *list view* control with checkboxes enabled, returns or sets the check state of the item.  <br />Check states are **0** (unchecked), **1** (checked), **2** (indeterminate), **3** (unchecked/disabled), **4** (checked/disabled), **5** (indeterminate/disabled). |
| data | *int* | Returns or sets the optional data value associated with this item. |
| disabled | *bool* | For a *list view* control, returns or sets the disable state of this item. When a *list view* item is disabled it appears ghosted and can't be selected or right-clicked. |
| fg | *string* | Set or query the color used for the text (foreground) of this control. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal).  <br />Currently only items in *list view* controls are supported for this property. |
| group | *int* | Returns or sets the *list view* group that this item is a member of. |
| icon | *string* | For a *list view* control, returns or sets the icon associated with this item. You can specify the path of a file or folder to use its icon, or a file extension (e.g. ".txt") to use a generic filetype icon. You can also set it to "dir", "file", "ftp" and "ftps" to use generic icons. You can also extract an icon from a DLL or EXE by providing the path of the file followed by a comma and then the icon index within the file. |
| index | *index* | Returns the 0-based index of this item within the control.<br /><br />For a combo edit box, this will return **-1** if the user typed in a string rather than selecting one from the list. The string they entered can be retrieved from the **name** property. |
| name | *string* | Returns or sets the item's name. |
| selected | *bool* | Returns or sets the item's selection state. Mostly useful with multiple-selection *list box* controls. |
| style | *string* | Returns or sets the text style this item will be displayed in. You should provide a string containing one or more of the following flags: "b" (bold), "i" (italics), "u" (underline).  <br />Currently only items in *list view* controls are supported for this property. |
| subitems | *collection:string* | For a list view control in *Details* mode, returns a collection of strings that lets you query or change the text of the item's sub-items. There will be one string in the collection for each column in the list, excluding the first column.<br /><br />For example, assuming the list has three columns in total, the string for the first column would be set using the **name** property above. The strings for the second and third columns would be set with **subitems(0)** and **subitems(1)**. |

