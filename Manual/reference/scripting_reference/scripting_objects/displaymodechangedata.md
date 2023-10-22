# DisplayModeChangeData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnDisplayModeChange](../scripting_events/ondisplaymodechange.md)** event, the method receives a **DisplayModeChangeData** object when the [display mode](/Manual/basic_concepts/the_lister/view_modes.md) is changed in a tab.

| Property Name | Return Type | Description |
| --- | --- | --- |
| mode | *string* | Returns a *string* indicating the new display mode. Will be one of *largeicons*, *smallicons*, *list*, *details*, *power*, *thumbnails* or *tiles*. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab the display mode changed in. |

