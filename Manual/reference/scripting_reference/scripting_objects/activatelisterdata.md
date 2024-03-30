# ActivateListerData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnActivateLister](../scripting_events/onactivatelister.md)**event, the method receives an **ActivateListerData** whenever the window activation state of a Lister changes.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
active</td><td>

*bool*</td><td>

Returns **True** if this Lister is activating, **False** if deactivating. Note that if the activation moves from one Lister straight to another the script will be called twice.
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that is closing.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr></tbody>
</table>

