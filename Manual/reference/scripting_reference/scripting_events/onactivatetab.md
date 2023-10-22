# OnActivateTab

The **OnActivateTab** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive a notification every time a tab becomes active (i.e. comes to the front of another tab in the same file display).

| **Method Name:** | OnActivateTab |
| --- | --- |
| **Argument Type:** | **[ActivateTabData](../scripting_objects/activatetabdata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **ActivateTabData.old** property identifies the tab that was previously active, and the **new** property identifies the new active tab. |

