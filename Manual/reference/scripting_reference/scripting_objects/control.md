# Control

The **Control** object represents a control on a [script dialog](/Manual/scripting/script_dialogs/README.md); it lets you read and modify a control's value (and contents). Use the **[Dialog](dialog.md).Control** method to obtain a **Control** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

Set or query the color used for the background (fill) of this control. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal). Currently only *static text* and *list view* controls are supported for this property.
</td></tr><tr><td>
charcase</td><td>

*string*</td><td>

For an *edit* control, gets or sets the control's case setting. Values are **upper**, **lower** and **normal**.
</td></tr><tr><td>
columns</td><td>

*object:***[DialogListColumns](dialoglistcolumns.md)**</td><td>

For a *list view* control, returns a **[DialogListColumns](dialoglistcolumns.md)** object that lets you query or modify the columns in *Details* mode.
</td></tr><tr><td>
count</td><td>

*int*</td><td>

Returns the number of items contained in the control (e.g. in a *combo box*, *list box* or *list view*, returns the number of items in the list).
</td></tr><tr><td>
cuetext</td><td>

*string*</td><td>
Get or set the cue text of a single-line edit control. This is the text shown to help the user when the edit control is empty.
</td></tr><tr><td>
cx</td><td>

*int*</td><td>
Set or query the width of the control, in pixels.
</td></tr><tr><td>
cy</td><td>

*int*</td><td>
Set or query the height of the control, in pixels.
</td></tr><tr><td>
enabled</td><td>

*bool*</td><td>

Set or query the enabled state of the control. Returns **True** if the control is enabled, **False** if it's disabled. You can set this property to change the state.
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

Set or query the color used for the text (foreground) of this control. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal). Currently only *static text* and *list view* controls are supported for this property.
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

Set or query the input focus state of the control. Returns **True** if the control currently has input focus, **False** if it doesn't. Set to **True** to give the control input focus.
</td></tr><tr><td>
label</td><td>

*string* or  
*object:***[Image](image.md)**</td><td>

Set or query the control's label or title. Not all controls have labels - this will have no effect on controls (like the *list view*) that don't.

Note that for *combo box* controls, this property is only valid for an editable combo - that is, one that you can type your own text into. You can use this property to set or query the current value of the editable text.

For a static control set to "image" mode, you can also provide an **[Image](image.md)** object that you obtained from the **[DOpus](dopus.md).LoadImage** or **[Script](script.md).LoadImage** methods.

For a *tab* control, you can set or query the labels of the individual tabs by specifying an index; e.g. `Control.label(0)` would reference the label of the first tab.
</td></tr><tr><td>
mode</td><td>

*string*</td><td>

For a *list view* control, lets you change or query the current view mode. Valid values are **icon**, **details**, **smallicon**, **list**.
</td></tr><tr><td>
readonly</td><td>

*bool*</td><td>

Set or query the *read only* state of an *edit* control.
</td></tr><tr><td>
redraw</td><td>

*bool*</td><td>

Set or query the redraw state of the control. Some controls let you turn off redrawing in order to make multiple changes without visible flicker (for example, adding a large number of items to a *list view*). Set to **False** to turn off redraw, or **True** to turn redraw back on after changing the control.
</td></tr><tr><td>
rotate</td><td>

*int*</td><td>

For a *static text* control set to "image" mode, you can set this property to rotate the displayed image. The value provided is the number of degrees from the image's initial orientation.
</td></tr><tr><td>
style</td><td>

*string*</td><td>

Set or query the font styles used to display this control's label. The string consists of zero or more characters; valid characters are **b** for bold and **i** for italics.

Currently only *static text* controls are supported for this property.
</td></tr><tr><td>
textbg</td><td>

*string*</td><td>

Set or query the color used for the text background (fill) of this control. This is in the format *\#RRGGBB* (hexadecimal) or *RRR,GGG,BBB* (decimal).

Currently only *list view* controls are supported for this property.
</td></tr><tr><td>
title</td><td>

*string* or  
*object:***[Image](image.md)**</td><td>

Alternative name for the **label** property. The term **title** is used in the dialog editor and XML resources, and can also be used here as a convenience.
</td></tr><tr><td>
value</td><td>

*string* or  
*bool* or  
*int or*  
*object:***[DialogListItem](dialoglistitem.md)** or  
*object:***[Vector](vector.md)**</td><td>

Set or query the control's value. The meaning of this property depends on the type of the control:

- **Edit control**: Returns or accepts a string representing the current contents of the edit control.
- **Check box**: For a simple on/off check box, returns or accepts a *bool* - **True** for checked and **False** for unchecked. For a tri-state check box, returns or accepts an *int* - **0** for unchecked, **1** for checked and **2** for the indeterminate state.
- **Radio button**: Returns or accepts a *bool* - **True** for checked and **False** for unchecked.
- **Tab**: Returns or accepts an *int* indicating the currently selected page in the tab control.
- **List box / combo box / list view**: Returns or accepts a **[DialogListItem](dialoglistitem.md)** representing the selected item. When setting the value it also accepts an *int* representing the 0-based index of the selected item.

Note that for a multiple-selection *list box* or *list view*, this value will return a **[Vector](vector.md)** of [DialogListItem](dialoglistitem.md) objects, representing all currently selected items.
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

Set or query the visible state of the control. Returns **True** if the control is visible and **False** if it's hidden. You can set this property to hide or show the control.
</td></tr><tr><td>
x</td><td>

*int*</td><td>
Set or query the left (x) position of the control, in pixels.
</td></tr><tr><td>
y</td><td>

*int *</td><td>
Set or query the top (y) position of the control, in pixels.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddGroup</td><td>

\<string:name\>  
\<int:id\>  
\[\<string:flags\>\]</td><td>

*int*</td><td>

Adds a new group to a *list view* control. Items you add to the list can optionally be placed in groups. Each group must have a unique ID.

The optional flags are "c" (group is collapsible) and "d" (group starts out collapsed). E.g. **AddGroup("Unimportant", 100, "cd")** would add a group called *Unimportant* that is initially collapsed.
</td></tr><tr><td>
AddItem</td><td>

\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

or

\<object:item\></td><td>

*int*</td><td>

Adds a new item to the control (*list box*, *combo box* or *list view*). The first parameter is the item's name, and the optional second parameter is a data value to associate with the item.

When adding to a grouped *list view*, the optional third parameter provides the ID of the group you want to add the item to (the second parameter must be provided in this case, and can be set to 0 if no value is required).

The item is added to the end of the list.

You can also pass a **[DialogListItem](dialoglistitem.md)** object obtained from another control.

The return value indicates the position in the list of the new item.

If you are adding to a listview control and need to add an item with multiple columns, you can do it like this (JScript):

    var i = listview.AddItem("This is col 1");
    listview.GetItemAt(i).subitems(0) = "This is col 2";
    listview.GetItemAt(i).subitems(1) = "This is col 3";
</td></tr><tr><td>
AutoSize</td><td>

\[\<bool:height\>\]</td><td>

*bool*</td><td>

Autosizes the control, if the control type supports autosize. Returns **True** if the control was autosized.

If the optional *height* parameter is set to true, the control will be autosized vertically as well as horizontally.
</td></tr><tr><td>
DeselectItem</td><td>
\<int:position\>

or

\<object:item\></td><td>

*int*</td><td>

This method is mainly for use with multiple-selection *list box* and *list view* controls. It lets you deselect individual items in the control while leaving other items selected (or unaffected).

You can specify either the index of the item to select (0 means the first item, 1 means the second and so on) or a **[DialogListItem](dialoglistitem.md)** object obtained from the **GetItemAt** or **GetItemByName** methods.

You can also specify **-1** to deselect all items in the list box.
</td></tr><tr><td>
EnableGroupView</td><td>
\<bool:enable\></td><td>
none</td><td>

Only applies to *list view* controls. By default group view is off; after adding groups with the **AddGroup** method, use **EnableGroupView** to turn group view on.
</td></tr><tr><td>
GetGroupById</td><td>
\<int:id\></td><td>

object:**[DialogListGroup](dialoglistgroup.md)**</td><td>

Returns a **[DialogListGroup](dialoglistgroup.md)**object representing the group with the specified ID that you've previous added to a *list view* control using the **AddGroup** method.
</td></tr><tr><td>
GetItemAt</td><td>
\<int:position\></td><td>

object:**[DialogListItem](dialoglistitem.md)**</td><td>

Returns a **[DialogListItem](dialoglistitem.md)** object representing the item contained in the control at the specified index (*list box*, *combo box* or *list view*). Item 0 represents the first item in the list, item 1 the second, and so on.
</td></tr><tr><td>
GetItemByLabel  
GetItemByName</td><td>
\<string:name\></td><td>

object:**[DialogListItem](dialoglistitem.md)**</td><td>

Returns a **[DialogListItem](dialoglistitem.md)** object representing the item contained in the control with the specified name (*list box, combo box or list view*). This method has two names (...*Label* and ...*Name*) for historical reasons, you can use either method name interchangeably).
</td></tr><tr><td>
InsertItemAt</td><td>

\<int:position\>  
\<string:name\>  
\[\<int:value\>\]  
\[\<int:groupid\>\]

or

\<int:position\>  
\<object:item\></td><td>

*int*</td><td>

Inserts a new item in the control (*list box, combo box or list view*). The first parameter is the position to insert the item at (0 means the beginning of the list, 1 means the second position and so on). The second parameter is the item's name, and the optional third parameter is a data value to associate with the item.

When adding to a grouped *list view*, the optional fourth parameter provides the ID of the group you want to add the item to (the third parameter must be provided in this case, and can be set to 0 if no value is required).

Instead of the *name* and *value* you can also pass a **[DialogListItem](dialoglistitem.md)** object obtained from another control.

The return value indicates the position in the list of the new item.
</td></tr><tr><td>
MoveItem</td><td>
\<int:position\>  
or  
\<object:item\>  
\<int:newposition\></td><td>

*int*</td><td>

Moves an existing item to a new location (*list box*, *combo box* or *list view*). The first parameter is the item to move (you can pass either its index or a **[DialogListItem](dialoglistitem.md)** object), and the second parameter is the new position the item should be moved to.

The return value indicates the position in the list of the moved item.
</td></tr><tr><td>
RemoveGroup</td><td>
\<int:id\></td><td>
none</td><td>

Removes the specified group from a *list view* control.
</td></tr><tr><td>
RemoveItem</td><td>
\<int:position\>  
or  
\<object:item\></td><td>
none</td><td>

Removes an item from the control (*list box, combo box or list view*). You can provide either the index of the item to remove (0 means the first item, 1 means the second and so on) or a **[DialogListItem](dialoglistitem.md)** object obtained from the **GetItemAt** or **GetItemByName** methods.

You can also specify **-1** to completely clear the contents of the control, removing all items at once.
</td></tr><tr><td>
SelectItem</td><td>
\<int:position\>  
or  
\<object:item\>  
or   
\<string:tab\></td><td>

*int*</td><td>

Selects an item in the control. For a *list box, combo box or list view*, you can specify either the index of the item to select (0 means the first item, 1 means the second and so on) or a **[DialogListItem](dialoglistitem.md)** object obtained from the **GetItemAt** or **GetItemByName** methods.

For a multiple-selection *list box* or *list view* you can also specify **-1** to select all items in the control.

For a *tab control*, you can change which page is visible by specifying the name of the page (i.e. the name of the child dialog) to show.

The return value indicates the new selected index.
</td></tr><tr><td>
SelectRange</td><td>
\<int:start\>  
\<int:end\>

or

\<object:item1\>  
\<object:item2\></td><td>

object:**[Vector](vector.md)**</td><td>

Selects text within an *edit control* (or the edit field in a *combo box* control). The two parameters represent the start and end position of the desired selection. To select the entire contents, use **0** for the start and **-1** for the end.

The return value is a **[Vector](vector.md)** with two members that provide the current start and end of the selection. To query the range without changing it, simply call the **SelectRange** method with no arguments.

In a *list box* or *list view* control, this method selects a range of items.
</td></tr><tr><td>
SetFont</td><td>
\<int:id\></td><td>
none</td><td>

Sets the font used by the control to the specified font. The *id* parameter must have come from a previous call to **[Dialog](dialog.md).CreateFont**. You can use 0 to reset the font to its default.
</td></tr><tr><td>
SetItemWidth</td><td>
\<int:width\></td><td>
none</td><td>

Sets the width in pixels of items in a list view control that's set to **list** or **smallicon** mode. Specify **-1** to automatically size the items.
</td></tr><tr><td>
SetPos</td><td>
\<int:x\>  
\<int:y\></td><td>
none</td><td>
Sets the position of this control. The x and y coordinates are specified in pixels.
</td></tr><tr><td>
SetPosAndSize</td><td>
\<int:x\>  
\<int:y\>  
\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
Sets the position and size of the control, in a single operation. All coordinates are specified in pixels.
</td></tr><tr><td>
SetSize</td><td>
\<int:cx\>  
\<int:cy\></td><td>
none</td><td>
Sets the size of this control. The cx (width) and cy (height) values are specified in pixels.
</td></tr></tbody>
</table>

