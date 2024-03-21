# OnStartup

The **OnStartup** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when Opus starts up.

| **Method Name:** | OnStartup |
| --- | --- |
| **Argument Type:** | **[StartupData](../scripting_objects/startupdata.md)** |
| **Return Type:** | *none* |
| **Description:** | This event is only triggered when Opus starts up, therefore only script add-ins that are already installed will receive it. If a script is installed when Opus is already running it won't receive **OnStartup** until the next time Opus is started. |

