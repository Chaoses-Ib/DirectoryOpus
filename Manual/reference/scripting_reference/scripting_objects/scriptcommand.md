# ScriptCommand

In a script's **[OnInit](../scripting_events/oninit.md)** method it can call the **[ScriptInitData](scriptinitdata.md).AddCommand** method to [add commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) to the Opus internal command set. Each call to **AddCommand** returns a **ScriptCommand** object that the script needs to initialize.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
desc</td><td>

*string*</td><td>

Use this to set a description for the command, that is displayed in the [Customize](/Manual/customize/README.md) dialog when the user selects the command from the [Commands tab](/Manual/customize/the_customize_dialog/commands.md).
</td></tr><tr><td>
fayt</td><td>

*object:***[ScriptFAYTCommand](scriptfaytcommand.md)**</td><td>

Returns a **[ScriptFAYTCommand](scriptfaytcommand.md)** object that you can use to initialise this command to [extend the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md).
</td></tr><tr><td>
hide</td><td>

*bool*</td><td>

Set to **True** to hide this command from the drop-down command list shown in the [command editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md). This lets you add commands that can still be used in buttons and hotkeys but won't clutter up the command list.
</td></tr><tr><td>
icon</td><td>

*string*</td><td>

Use this property to assign a default icon to this command. You can specify the name of an internal icon (if you want to specify an icon from a particular set, use *setname:iconname -* use this if you have bundled your script in a [script package](/Manual/scripting/script_add-ins/script_package.md) with its own icon set) or the path of an external icon or image file.
</td></tr><tr><td>
label</td><td>

*string*</td><td>

Use this to set a label for the command. This is displayed in the [Commands tab](/Manual/customize/the_customize_dialog/commands.md) of the [Customize](/Manual/customize/README.md) dialog (under the *Script Commands* category), and will form the default label of the button created if the user drags that command out to a toolbar.

The actual name of the command (used to invoke the command) is assigned through the **name** property.
</td></tr><tr><td>
method</td><td>

*string*</td><td>

This is the name of the method that Opus will call in your script when the command is invoked. This would typically be set to *OnXXXXX* where *XXXXX* is the name of the command, however any method name can be used.

When the method is invoked it is passed a single argument, a **[ScriptCommandData](scriptcommanddata.md)** object. Generically this method is referred to as **[OnScriptCommand](../scripting_events/onscriptcommand.md)**.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
This is the name of the command. This determines the name that will invoke the command when it is used in buttons and hotkeys.
</td></tr><tr><td>
noprogress</td><td>

*bool*</td><td>
Set to false if you don't want your command to display a progress indicator if more than one file is selected.
</td></tr><tr><td>
template</td><td>

*string*</td><td>

This lets you specify an optional command line template for the command. This is a string in the form *ARGNAME1/MOD,ARGNAME2/MOD,ARGNAME3/MOD*, etc, where ARGNAME is the name of the argument and /MOD are one or more [modifiers used to indicate the argument type](../../command_reference/argument_types.md). The command line template can specify as many arguments as needed.

When your command is invoked and its **[OnScriptCommand](../scripting_events/onscriptcommand.md)**event is triggered, any arguments supplied on the command line are parsed according to this template and provided via the **[ScriptCommandData](scriptcommanddata.md).[func](func.md).args** property.
</td></tr></tbody>
</table>

