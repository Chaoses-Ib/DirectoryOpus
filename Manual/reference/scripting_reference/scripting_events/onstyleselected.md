# OnStyleSelected

The **OnStyleSelected** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification when the user selects a new [Lister style](/Manual/basic_concepts/the_lister/styles.md).

| **Method Name:** | OnStyleSelected |
| --- | --- |
| **Argument Type:** | **[StyleSelectedData](../scripting_objects/styleselecteddata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **StyleSelectedData.lister** property identifies the Lister, and the **style** property returns the name of the newly selected style. |

