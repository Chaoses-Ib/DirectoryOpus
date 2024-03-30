# StyleSelectedData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnStyleSelected](../scripting_events/onstyleselected.md)** event, the method receives a **StyleSelectedData** object when the user chooses a new [Lister style](/Manual/basic_concepts/the_lister/styles.md).

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that changing style.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
style</td><td>

*string*</td><td>
Returns the name of the newly selected style.
</td></tr></tbody>
</table>

