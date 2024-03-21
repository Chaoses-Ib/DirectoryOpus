# OnSourceDestChange

The **OnSourceDestChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a tab's source/destination state changes.

| **Method Name:** | OnSourceDestChange |
| --- | --- |
| **Argument Type:** | **[SourceDestData](../scripting_objects/sourcedestdata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **SourceDestData.tab** property identifies the tab, and the **source** and **dest** properties identify the new state (if both are **False** it means the tab is "off" - this can only happen in a single file-display Lister). |

