# SourceDestData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnSourceDestChange](../scripting_events/onsourcedestchange.md)** event, the method receives a **SourceDestData** object to indicate which tab's state changed.

| Property Name | Return Type | Description |
| --- | --- | --- |
| dest | *bool* | Returns **True** if the tab is now the destination. |
| source | *bool* | Returns **True** if the tab is now the source. If both **source** and **dest** return False it indicates that the tab is now "off". |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab. |

