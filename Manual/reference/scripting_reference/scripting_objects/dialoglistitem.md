# DialogListItem

The **DialogListItem** object represents an item in a *combo box* or *list box* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](control.md).GetItemAt** and **[Control](control.md).GetItemByName** methods.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

Set or query the color used for the background (fill) of this item. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal).  
Currently only items in *list view* controls are supported for this property.
</td></tr><tr><td>
checked</td><td>

*int*</td><td>

For a *list view* control with checkboxes enabled, returns or sets the check state of the item.  
Check states are **0** (unchecked), **1** (checked), **2** (indeterminate), **3** (unchecked/disabled), **4** (checked/disabled), **5** (indeterminate/disabled).
</td></tr><tr><td>
data</td><td>

*int*</td><td>
Returns or sets the optional data value associated with this item.
</td></tr><tr><td>
disabled</td><td>

*bool*</td><td>

For a *list view* control, returns or sets the disable state of this item. When a *list view* item is disabled it appears ghosted and can't be selected or right-clicked.
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

Set or query the color used for the text (foreground) of this control. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal).  
Currently only items in *list view* controls are supported for this property.
</td></tr><tr><td>
group</td><td>

*int*</td><td>

Returns or sets the *list view* group that this item is a member of.
</td></tr><tr><td>
icon</td><td>

*string*</td><td>

For a *list view* control, returns or sets the icon associated with this item. You can specify the path of a file or folder to use its icon, or a file extension (e.g. ".txt") to use a generic filetype icon. You can also set it to "dir", "file", "ftp" and "ftps" to use generic icons. You can also extract an icon from a DLL or EXE by providing the path of the file followed by a comma and then the icon index within the file.
</td></tr><tr><td>
index</td><td>

*index*</td><td>

Returns the 0-based index of this item within the control.

For a combo edit box, this will return **-1** if the user typed in a string rather than selecting one from the list. The string they entered can be retrieved from the **name** property.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns or sets the item's name.
</td></tr><tr><td>
selected</td><td>

*bool*</td><td>

Returns or sets the item's selection state. Mostly useful with multiple-selection *list box* controls.
</td></tr><tr><td>
style</td><td>

*string*</td><td>

Returns or sets the text style this item will be displayed in. You should provide a string containing one or more of the following flags: "b" (bold), "i" (italics), "u" (underline).  
Currently only items in *list view* controls are supported for this property.
</td></tr><tr><td>
subitems</td><td>

*collection:string*</td><td>

For a list view control in *Details* mode, returns a collection of strings that lets you query or change the text of the item's sub-items. There will be one string in the collection for each column in the list, excluding the first column.

For example, assuming the list has three columns in total, the string for the first column would be set using the **name** property above. The strings for the second and third columns would be set with **subitems(0)** and **subitems(1)**.
</td></tr></tbody>
</table>

