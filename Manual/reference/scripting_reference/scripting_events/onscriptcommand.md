# OnScriptCommand

The **OnScriptCommand** event is the entry point for an [internal command](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) added by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md). The actual name of the event is defined by the script itself, when the command is added via the **[ScriptInitData](../scripting_objects/scriptinitdata.md).AddCommand** method - **OnScriptCommand** is merely a placeholder name.

| **Method Name:** | OnScriptCommand |
| --- | --- |
| **Argument Type:** | **[ScriptCommandData](../scripting_objects/scriptcommanddata.md)** |
| **Return Type:** | *bool* |
| **Description:** | When a script add-in adds a new internal command using **ScriptInitData.AddCommand**, it specifies the name of its entry point with the **ScriptCommand.method** property. When the internal command is run, Opus will call that method within your script.  <br />The **ScriptCommandData.func** property provides information about the command environment (including any parsed arguments), and the **cmdline** property provides the raw command line that invoked your command.  <br />If this event returns **True** the function will be aborted - you might do this if an error occurs and the user chooses to abort the operation. |

