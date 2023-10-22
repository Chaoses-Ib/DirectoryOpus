# OnFlatViewChange

The **OnFlatViewChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification whenever the user changes the [display mode](/Manual/basic_concepts/the_lister/view_modes.md) in a tab.

| **Method Name:** | OnFlatViewChange |
| --- | --- |
| **Argument Type:** | **[FlatViewChangeData](../scripting_objects/flatviewchangedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **FlatViewChangeData.tab** property identifies the tab, and the **mode** property identifies the new Flat View mode ("off", "grouped", "mixed", "mixednofolders"). |

