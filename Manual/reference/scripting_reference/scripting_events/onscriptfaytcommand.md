# OnScriptFAYTCommand

The **OnScriptFAYTCommand** event is the entry point for a [script add-in](/Manual/scripting/script_add-ins/README.md) that [extends the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md). The actual name of the event is defined by the script itself, when the command is added via the **[ScriptInitData](../scripting_objects/scriptinitdata.md).AddCommand** method - **OnScriptFAYTCommand** is merely a placeholder name.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnScriptFAYTCommand
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ScriptFAYTCommandData](../scripting_objects/scriptfaytcommanddata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

When a script extends the FAYT field by adding a new internal command using **ScriptInitData.AddCommand**, it specifies the name of its entry point with the **ScriptCommand.method** property. When the FAYT extension is triggered, Opus will call that method within your script.

The **[scriptfaytcommanddata](../scripting_objects/scriptfaytcommanddata.md)** object provides information about what the user has typed to trigger your extension.
</td></tr></tbody>
</table>

