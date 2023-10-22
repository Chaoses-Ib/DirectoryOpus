# OpenListerData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnOpenLister](../scripting_events/onopenlister.md)** event, the method receives an **OpenListerData** object when invoked when a new Lister opens.

| Property Name | Return Type | Description |
| --- | --- | --- |
| after | *bool* | Initially this is set to **False**, indicating that the event has been called before any tabs have been created. If you return **True** from the **[OnOpenLister](../scripting_events/onopenlister.md)** event, it will be called again and **after** will be set to **True** to indicate all tabs have been created. |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the newly opened Lister. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |

