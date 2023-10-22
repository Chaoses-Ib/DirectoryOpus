# OnCloseLister

The **OnCloseLister** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification whenever a Lister is closed.

| **Method Name:** | OnCloseLister |
| --- | --- |
| **Argument Type:** | **[CloseListerData](../scripting_objects/closelisterdata.md)** |
| **Return Type:** | *bool* |
| **Description:** | The **CloseListerData.lister** property identifies the Lister that is closing. The **shutdown** property is **True** if the Lister is closing because Opus (or Windows) is shutting down.  <br />If shutdown is **False**, you can prevent the Lister from closing by returning **True** from this event (or **False** to allow the close, which is the default). If Opus or Windows is shutting down then you can't prevent the Lister from closing. |

