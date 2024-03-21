# OnShutdown

The **OnShutdown** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when Opus is shutting down.

| **Method Name:** | OnShutdown |
| --- | --- |
| **Argument Type:** | **[ShutdownData](../scripting_objects/shutdowndata.md)** |
| **Return Type:** | *bool* |
| **Description:** | Opus calls this event when it is shutting down. The **ShutdownData.endsession** property will be **True** if Opus is quitting because Windows is shutting down. If **endsession** is **False**, you can return **True** from this event to prevent Opus from quitting - the return value is ignored if Windows is shutting down too. |

