# ListerUIChangeData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnListerUIChange](../scripting_events/onlisteruichange.md)** event, the method receives a **ListerUIChangeData** object when various user interface elements are opened or closed in a Lister.

| Property Name | Return Type | Description |
| --- | --- | --- |
| change | *string* | Returns a *string* indicating which UI elements changed. This will contain one or more of the following strings: *dual*, *tree*, *metapane*, *viewer*, *utility*, *duallayout*, *metapanelayout*, *viewerlayout*, *toolbars*, *toolbarset*, *toolbarsauto*, *minmax.* |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the Lister that is changing. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |

