# ActivateTabData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnActivateTab](../scripting_events/onactivatetab.md)**event, the method receives an **ActivateTabData** object whenever the activation state of a tab changes.

| Property Name | Return Type | Description |
| --- | --- | --- |
| closing | *bool* | Returns **True** if the activation change is due to the old tab being closed. |
| newtab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab that has become active. |
| oldtab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab that has gone inactive. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |

