# TabClickData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnTabClick](../scripting_events/ontabclick.md)** event, the method receives a **TabClickData** object when a tab is clicked with a qualifier key held down.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that was clicked.
</td></tr></tbody>
</table>

