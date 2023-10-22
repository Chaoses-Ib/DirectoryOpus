# OnAddCommands

The **OnAddCommands** event is called to allow your [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md). Call the **[AddCmdData](../scripting_objects/addcmddata.md).AddCommand** method once for each command you wish to add.

| **Method Name:** | OnAddCommands |
| --- | --- |
| **Argument Type:** | **[AddCmdData](../scripting_objects/addcmddata.md)** |
| **Return Type:** | *none* |
| **Description:** | When Opus starts up, or when a script add-in is added, edited or enabled, its **OnAddCommands** method is called. This allows a script to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md)to the Opus command set. A script can reinitialize its list of commands at any time by calling the **[Script](../scripting_objects/script.md).InitCommands** method. |

