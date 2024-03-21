# OnListerUIChange

The **OnListerUIChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when the state of certain user interface elements in the Lister changes.

| **Method Name:** | OnListerUIChange |
| --- | --- |
| **Argument Type:** | **[ListerUIChangeData](../scripting_objects/listeruichangedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **ListerUIChangeData.lister** property identifies the Lister, and the **change** property is a *string* indicating the element that changed. You can discover the actual state of the element using the **[Command](../scripting_objects/command.md).IsSet** method. |

