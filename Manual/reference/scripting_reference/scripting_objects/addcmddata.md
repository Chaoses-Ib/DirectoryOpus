# AddCmdData

The **AddCmdData** object is passed to the **[OnAddCommands](../scripting_events/onaddcommands.md) **event in a [script add-in](/Manual/scripting/script_add-ins/README.md). The script can use this to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) using the **AddCommand** method.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddCommand</td><td>

*none*</td><td>

*object:***[ScriptCommand](scriptcommand.md)**</td><td>

Adds a new internal command to Opus. The returned **[ScriptCommand](scriptcommand.md)** object must be properly initialized. A script add-in can add as many internal commands as it likes to the Opus internal command set.
</td></tr></tbody>
</table>

