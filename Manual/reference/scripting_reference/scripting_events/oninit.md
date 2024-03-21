# OnInit

The **OnInit** event is called once for each [script add-in](/Manual/scripting/script_add-ins/README.md) to initialize it. The event will be called on program startup, and also if a script is added or edited while Opus is already running. Implementing the **OnInit** event is optional, but highly recommended as it allows you to provide a name, description and other information to be shown to the user in Preferences. It also provides a way for a script to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) and [columns](/Manual/scripting/example_scripts/adding_a_new_column.md) (although the **[OnAddCommands](onaddcommands.md)** and **[OnAddColumns](onaddcolumns.md)** methods provide a better way to do this).

| **Method Name:** | OnInit |
| --- | --- |
| **Argument Type:** | **[ScriptInitData](../scripting_objects/scriptinitdata.md)** |
| **Return Type:** | *bool* |
| **Description:** | When Opus starts up, or when a script add-in is added or edited, its **OnInit** method is called. This gives the script a chance to tell Opus something about itself, by setting the various properties of the **ScriptInitData** object. The **AddCommand** method can also be used from this event to [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md)to the Opus command set, and AddColumn method can be used to add [columns](/Manual/scripting/example_scripts/adding_a_new_column.md).  <br />If you return **True** from this method, the script will be disabled until the next time **OnInit** is called (which normally would be the next time Opus is run). For instance, you might want to do this if the version of Windows isn't appropriate for your script. |

