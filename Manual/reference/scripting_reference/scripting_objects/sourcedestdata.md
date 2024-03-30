# SourceDestData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnSourceDestChange](../scripting_events/onsourcedestchange.md)** event, the method receives a **SourceDestData** object to indicate which tab's state changed.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dest</td><td>

*bool*</td><td>

Returns **True** if the tab is now the destination.
</td></tr><tr><td>
source</td><td>

*bool*</td><td>

Returns **True** if the tab is now the source. If both **source** and **dest** return False it indicates that the tab is now "off".
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab.
</td></tr></tbody>
</table>

