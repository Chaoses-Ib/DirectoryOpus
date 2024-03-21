# ConfigChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnScriptConfigChange](../scripting_events/onscriptconfigchange.md)**event, the method receives a **ConfigChangeData** object whenever the user modifies the script's configuration via the Preferences editor.

| Property Name | Return Type | Description |
| --- | --- | --- |
| changed | **[Vector](vector.md)**:*string* | Returns a **[Vector](vector.md)** containing the names of the configuration items that were modified. |

