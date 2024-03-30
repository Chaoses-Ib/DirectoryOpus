# OpenListerData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnOpenLister](../scripting_events/onopenlister.md)** event, the method receives an **OpenListerData** object when invoked when a new Lister opens.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
after</td><td>

*bool*</td><td>

Initially this is set to **False**, indicating that the event has been called before any tabs have been created. If you return **True** from the **[OnOpenLister](../scripting_events/onopenlister.md)** event, it will be called again and **after** will be set to **True** to indicate all tabs have been created.
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the newly opened Lister.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr></tbody>
</table>

