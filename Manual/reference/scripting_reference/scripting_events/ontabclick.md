# OnTabClick

The **OnTabClick** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when a tab is clicked with a qualifier key held down. You can use this to override the default behavior (e.g. control-clicking tabs normally links them).

| **Method Name:** | OnTabClick |
| --- | --- |
| **Argument Type:** | **[TabClickData](../scripting_objects/tabclickdata.md)** |
| **Return Type:** | *bool* |
| **Description:** | The **TabClickData.tab** property identifies the tab that was clicked. You can return **True** from this event to prevent the default action, or **False** (which is the default) to allow it to proceed. |

