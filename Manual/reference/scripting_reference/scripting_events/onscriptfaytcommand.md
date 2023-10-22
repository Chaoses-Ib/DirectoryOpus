# OnScriptFAYTCommand

The **OnScriptFAYTCommand** event is the entry point for a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) that [extends the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md). The actual name of the event is defined by the script itself, when the command is added via the **[ScriptInitData](../scripting_objects/scriptinitdata.md).AddCommand** method - **OnScriptFAYTCommand** is merely a placeholder name.

| **Method Name:** | OnScriptFAYTCommand |
| --- | --- |
| **Argument Type:** | **[ScriptFAYTCommandData](../scripting_objects/scriptfaytcommanddata.md)** |
| **Return Type:** | *none* |
| **Description:** | When a script extends the FAYT field by adding a new internal command using **ScriptInitData.AddCommand**, it specifies the name of its entry point with the **ScriptCommand.method** property. When the FAYT extension is triggered, Opus will call that method within your script.<br /><br />The **[scriptfaytcommanddata](../scripting_objects/scriptfaytcommanddata.md)** object provides information about what the user has typed to trigger your extension. |

