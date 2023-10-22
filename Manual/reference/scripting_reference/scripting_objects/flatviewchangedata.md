# FlatViewChangeData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnFlatViewChange](../scripting_events/onflatviewchange.md)**event, the method receives a **FlatViewChangeData** object when the [Flat View](/Manual/basic_concepts/flat_view.md) mode is changed in a tab.

| Property Name | Return Type | Description |
| --- | --- | --- |
| mode | *string* | Returns a *string* indicating the new Flat View mode. Will be one of *off*, *grouped*, *mixed* or *mixednofolders*. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab the Flat View mode changed in. |

