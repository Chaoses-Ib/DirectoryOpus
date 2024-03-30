# DoubleClickData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event, the method receives a **DoubleClickData** object when the user double-clicks a file or folder.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
call</td><td>

*bool*</td><td>

Set this property to **False** to prevent the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event being called for any further files during this operation (this is only effective if more than one file was double-clicked). Any remaining files will be opened according to their default handlers.
</td></tr><tr><td>
cont</td><td>

*bool*</td><td>

Set this property to **False** to abort double-click processing altogether on any further files during this operation (this is only effective if more than one file was double-clicked).
</td></tr><tr><td>
early</td><td>

*bool*</td><td>

Returns **True** if your **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event is being called with only a path (via the **path** property) and not a full **[Item](item.md)** object. This will occur if you set the **[ScriptInitData](scriptinitdata.md).early_dblclk** property to **True** when initialising your script.

When early is **True**, you can set the **skipfull** to **True** to prevent the second call with a full **Item** object.
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

Returns **True** if the item double-clicked is a directory, **False** if it's a file.
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.md)**</td><td>

Returns a **[Item](item.md)** object representing the item that was double-clicked. This property is only present if the **early** property is **False**.
</td></tr><tr><td>
mouse</td><td>

*string*</td><td>

Returns a string that indicates the mouse button that launched the double-click. The string can be one of the following: *left*, *middle*, *none*.
</td></tr><tr><td>
multiple</td><td>

*bool*</td><td>

This is set to **True** if multiple files were double-clicked.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object providing the full pathname of the item that was double-clicked.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
skipfull</td><td>

*bool*</td><td>

When the early property is **True**, set **skipfull** to **True** to prevent your **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event from being called a second time.
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that the item was double-clicked in.
</td></tr></tbody>
</table>

