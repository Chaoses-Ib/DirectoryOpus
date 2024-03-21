# OnListerResize

The **OnListerResize** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a Lister window is resized.

| **Method Name:** | OnListerResize |
| --- | --- |
| **Argument Type:** | **[ListerResizeData](../scripting_objects/listerresizedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **ListerResizeData.lister** property identifies the Lister, and the **action** property is a *string* indicating the element that resize action taken. Use the **width** and **height** properties to determine the new window size. |

