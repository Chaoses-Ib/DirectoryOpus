# AddCmdData

The **AddCmdData** object is passed to the **[OnAddCommands](../scripting_events/onaddcommands.md) **event in a [script add-in](/Manual/scripting/script_add-ins/README.md). The script can use this to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) using the **AddCommand** method.

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AddCommand | *none* | *object:***[ScriptCommand](scriptcommand.md)** | Adds a new internal command to Opus. The returned **[ScriptCommand](scriptcommand.md)** object must be properly initialized. A script add-in can add as many internal commands as it likes to the Opus internal command set. |

