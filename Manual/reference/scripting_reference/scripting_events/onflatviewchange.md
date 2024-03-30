# OnFlatViewChange

The **OnFlatViewChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever the user changes the [display mode](/Manual/basic_concepts/the_lister/view_modes.md) in a tab.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnFlatViewChange
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[FlatViewChangeData](../scripting_objects/flatviewchangedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **FlatViewChangeData.tab** property identifies the tab, and the **mode** property identifies the new Flat View mode ("off", "grouped", "mixed", "mixednofolders").
</td></tr></tbody>
</table>

