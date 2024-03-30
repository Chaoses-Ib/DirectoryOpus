# ScriptCommandData

The **ScriptCommandData** object is passed to the script-defined entry points for any [internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) added by a [script add-in](/Manual/scripting/script_add-ins/README.md). The method name for these events is defined by the script itself, but generically it's referred to as **[OnScriptCommand](../scripting_events/onscriptcommand.md)**.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>

This returns the original command line that invoked the command. If any arguments were provided on the command line they are available in parsed form from the **func.args** property.
</td></tr><tr><td>
fayt</td><td>

*string*  
or *bool*</td><td>

If this is a string, it means this is being called as a [FAYT extension](scriptfaytcommanddata.md) command. If set to **False** it's a regular command.
</td></tr><tr><td>
func</td><td>

*object:***[Func](func.md)**</td><td>

Returns a **[Func](func.md)** object relating to this function. This provides access to information about the function's environment (source and destination tabs, etc) as well as any variables and parsed command line arguments.
</td></tr></tbody>
</table>

