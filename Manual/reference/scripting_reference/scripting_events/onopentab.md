# OnOpenTab

The **On** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification when a new tab opens.

| **Method Name:** | OnOpenTab |
| --- | --- |
| **Argument Type:** | **[OpenTabData](../scripting_objects/opentabdata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **OpenTabData.tab** property identifies the newly opened tab. Note that this method is not called when a new Lister is opened, irrespective of how many tabs it contains - instead, you can identify all the tabs in the newly opened Lister by implementing the **OnOpenLister** event. |

