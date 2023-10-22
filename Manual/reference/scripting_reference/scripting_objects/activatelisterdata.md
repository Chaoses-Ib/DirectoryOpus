# ActivateListerData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnActivateLister](../scripting_events/onactivatelister.md)**event, the method receives an **ActivateListerData** whenever the window activation state of a Lister changes.

| Property Name | Return Type | Description |
| --- | --- | --- |
| active | *bool* | Returns **True** if this Lister is activating, **False** if deactivating. Note that if the activation moves from one Lister straight to another the script will be called twice. |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the Lister that is closing. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |

