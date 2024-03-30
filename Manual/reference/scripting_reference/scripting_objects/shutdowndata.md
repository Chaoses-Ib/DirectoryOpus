# ShutdownData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnShutdown](../scripting_events/onshutdown.md)** event, the method receives a **ShutdownData** object when invoked on Opus shutdown.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
endsession</td><td>

*bool*</td><td>

Returns **True** if the Windows session is ending (that is, if Opus is shutting down because the system is shutting down), or **False** if it's just Opus that is quitting.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr></tbody>
</table>

