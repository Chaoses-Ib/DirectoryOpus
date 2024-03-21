# ShutdownData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnShutdown](../scripting_events/onshutdown.md)** event, the method receives a **ShutdownData** object when invoked on Opus shutdown.

| Property Name | Return Type | Description |
| --- | --- | --- |
| endsession | *bool* | Returns **True** if the Windows session is ending (that is, if Opus is shutting down because the system is shutting down), or **False** if it's just Opus that is quitting. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |

