# CloseListerData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnCloseLister](../scripting_events/oncloselister.md)** event, the method receives a **CloseListerData** object before a Lister is closed.

| Property Name | Return Type | Description |
| --- | --- | --- |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the Lister that is closing. |
| prevent_save | *bool* | Set this to **True** to prevent the closing Lister from being saved as the new default Lister. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| shutdown | *bool* | Returns **True** if the Lister is closing because Opus is shutting down. |

