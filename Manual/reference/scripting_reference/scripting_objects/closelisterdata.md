# CloseListerData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnCloseLister](../scripting_events/oncloselister.md)** event, the method receives a **CloseListerData** object before a Lister is closed.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that is closing.
</td></tr><tr><td>
prevent_save</td><td>

*bool*</td><td>

Set this to **True** to prevent the closing Lister from being saved as the new default Lister.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
shutdown</td><td>

*bool*</td><td>

Returns **True** if the Lister is closing because Opus is shutting down.
</td></tr></tbody>
</table>

