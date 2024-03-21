# OnDisplayModeChange

The **OnDisplayModeChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever the user changes the [display mode](/Manual/basic_concepts/the_lister/view_modes.md) in a tab.

| **Method Name:** | OnDisplayModeChange |
| --- | --- |
| **Argument Type:** | **[DisplayModeChangeData](../scripting_objects/displaymodechangedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **DisplayModeChangeData.tab** property identifies the tab, and the **mode** property identifies the new display mode. |

