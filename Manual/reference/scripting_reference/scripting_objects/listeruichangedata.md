# ListerUIChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnListerUIChange](../scripting_events/onlisteruichange.md)** event, the method receives a **ListerUIChangeData** object when various user interface elements are opened or closed in a Lister.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
change</td><td>

*string*</td><td>

Returns a *string* indicating which UI elements changed. This will contain one or more of the following strings: *dual*, *tree*, *metapane*, *viewer*, *utility*, *duallayout*, *metapanelayout*, *viewerlayout*, *toolbars*, *toolbarset*, *toolbarsauto*, *minmax.*
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that is changing.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr></tbody>
</table>

