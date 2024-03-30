# OnAddCommands

The **OnAddCommands** event is called to allow your [script add-in](/Manual/scripting/script_add-ins/README.md) to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md). Call the **[AddCmdData](../scripting_objects/addcmddata.md).AddCommand** method once for each command you wish to add.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnAddCommands
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[AddCmdData](../scripting_objects/addcmddata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

When Opus starts up, or when a script add-in is added, edited or enabled, its **OnAddCommands** method is called. This allows a script to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md)to the Opus command set. A script can reinitialize its list of commands at any time by calling the **[Script](../scripting_objects/script.md).InitCommands** method.
</td></tr></tbody>
</table>

