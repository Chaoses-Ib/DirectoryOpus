# FileOperationCompleteData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.md)** event, the method receives a **FileOperationCompleteData** object whenever a supported file operation begins. If you return **True** to indicate that you want to be notified about the operation, you'll receive another call when the operation is complete.

| Property Name | Return Type | Description |
| --- | --- | --- |
| action | *string* | Returns a string that indicates the type of file operation. Currently the only supported value is **"rename"**. |
| cmdline | *string* | Returns a string that provides the entire command line that launched this operation. |
| data | *variant* | When the **query** property is **False** this provides further information about the operation that completed.  <br />For "rename" this returns a **[Map](map.md)** object that provides a map of all items that were renamed and their new names. |
| dest | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the destination path of the operation. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the operation was initiated.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| query | *bool* | Returns **True** the first time the **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.md)** event is called. You should examine the action and other properties and return **True** if you decide you want notification about this operation. This will be **False** when you are called the second time, when the operation is complete. |
| source | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the source path of the operation. |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the source folder tab. |

