# StyleSelectedData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnStyleSelected](../scripting_events/onstyleselected.md)** event, the method receives a **StyleSelectedData** object when the user chooses a new [Lister style](/Manual/basic_concepts/the_lister/styles.md).

| Property Name | Return Type | Description |
| --- | --- | --- |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the Lister that changing style. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| style | *string* | Returns the name of the newly selected style. |

