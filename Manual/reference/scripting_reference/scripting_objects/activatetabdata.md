# ActivateTabData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnActivateTab](../scripting_events/onactivatetab.md)**event, the method receives an **ActivateTabData** object whenever the activation state of a tab changes.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
closing</td><td>

*bool*</td><td>

Returns **True** if the activation change is due to the old tab being closed.
</td></tr><tr><td>
newtab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that has become active.
</td></tr><tr><td>
oldtab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that has gone inactive.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr></tbody>
</table>

