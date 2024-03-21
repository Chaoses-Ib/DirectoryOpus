# OnScriptConfigChange

The **OnScriptConfigChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever the user modifies the script's configuration via the Preferences editor.

| **Method Name:** | OnScriptConfigChange |
| --- | --- |
| **Argument Type:** | **[ConfigChangeData](../scripting_objects/configchangedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **ConfigChangeData.changed** property identifies the configuration items that were modified. |

