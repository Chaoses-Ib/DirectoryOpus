# FlatViewChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnFlatViewChange](../scripting_events/onflatviewchange.md)**event, the method receives a **FlatViewChangeData** object when the [Flat View](/Manual/basic_concepts/flat_view.md) mode is changed in a tab.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
mode</td><td>

*string*</td><td>

Returns a *string* indicating the new Flat View mode. Will be one of *off*, *grouped*, *mixed* or *mixednofolders*.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab the Flat View mode changed in.
</td></tr></tbody>
</table>

