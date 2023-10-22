# OpenTabData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnOpenTab](../scripting_events/onopentab.md)** event, the method receives an **OpenTabData** object when invoked when a new tab is opened.

| Property Name | Return Type | Description |
| --- | --- | --- |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the newly opened tab. |

