# DoubleClickData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event, the method receives a **DoubleClickData** object when the user double-clicks a file or folder.

| Property Name | Return Type | Description |
| --- | --- | --- |
| call | *bool* | Set this property to **False** to prevent the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event being called for any further files during this operation (this is only effective if more than one file was double-clicked). Any remaining files will be opened according to their default handlers. |
| cont | *bool* | Set this property to **False** to abort double-click processing altogether on any further files during this operation (this is only effective if more than one file was double-clicked). |
| early | *bool* | Returns **True** if your **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event is being called with only a path (via the **path** property) and not a full **[Item](item.md)** object. This will occur if you set the **[ScriptInitData](scriptinitdata.md).early_dblclk** property to **True** when initialising your script.<br /><br />When early is **True**, you can set the **skipfull** to **True** to prevent the second call with a full **Item** object. |
| is_dir | *bool* | Returns **True** if the item double-clicked is a directory, **False** if it's a file. |
| item | *object:***[Item](item.md)** | Returns a **[Item](item.md)** object representing the item that was double-clicked. This property is only present if the **early** property is **False**. |
| mouse | *string* | Returns a string that indicates the mouse button that launched the double-click. The string can be one of the following: *left*, *middle*, *none*. |
| multiple | *bool* | This is set to **True** if multiple files were double-clicked. |
| path | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object providing the full pathname of the item that was double-clicked. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| skipfull | *bool* | When the early property is **True**, set **skipfull** to **True** to prevent your **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event from being called a second time. |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab that the item was double-clicked in. |

