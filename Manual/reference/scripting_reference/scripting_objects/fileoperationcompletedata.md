# FileOperationCompleteData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.md)** event, the method receives a **FileOperationCompleteData** object whenever a supported file operation begins. If you return **True** to indicate that you want to be notified about the operation, you'll receive another call when the operation is complete.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

Returns a string that indicates the type of file operation. Currently the only supported value is **"rename"**.
</td></tr><tr><td>
cmdline</td><td>

*string*</td><td>
Returns a string that provides the entire command line that launched this operation.
</td></tr><tr><td>
data</td><td>

*variant*</td><td>

When the **query** property is **False** this provides further information about the operation that completed.  
For "rename" this returns a **[Map](map.md)** object that provides a map of all items that were renamed and their new names.
</td></tr><tr><td>
dest</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the destination path of the operation.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the operation was initiated.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
query</td><td>

*bool*</td><td>

Returns **True** the first time the **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.md)** event is called. You should examine the action and other properties and return **True** if you decide you want notification about this operation. This will be **False** when you are called the second time, when the operation is complete.
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the source path of the operation.
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the source folder tab.
</td></tr></tbody>
</table>

