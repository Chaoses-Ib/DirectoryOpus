# Advanced Command Editor

See the [Command Editor]() page for a description of the elements which the Simple and Advanced modes have in common. This page only covers things unique to the Advanced mode.

While the [Simple mode](simple_command_editor.md) only lets you define single-line functions, Advanced mode lets you create more complex ones. From Simple mode, click the **Advanced** button to switch to Advanced mode. The command editor will also switch to Advanced mode automatically if the button you are editing already contains a function with more than one line. In the Advanced mode the single line **Function** field is replaced by a multiple-line text box that lets you create more complicated, multiple-line functions.

![](/Manual/images/media/command_editor_advanced.png)

This screenshot shows the command editor when it is in Advanced mode (the function shown is from **Copy Files** button on the default toolbar). You can see that the single-line **Function** field has been replaced with a multiple-line field. There is a new drop-down which lets you select the type of the function (*Standard* or *MS-DOS Batch*). Also, the **Start in** and **Run** fields have disappeared - if they had been specified in Simple mode, they will be replaced by equivalent commands in the multi-line function definition. (Not to be confused with the **Run** button, which is discussed below.)

![](/Manual/images/media/start_in_x_run_0.png) 

In these screenshots you can see that the **Start in** field has been converted to a **cd** command (to set the **c**urrent **d**irectory) and the **Run** setting has been converted to a **@runmode** modifier. There are a number of command modifiers that you can use for commands in Advanced mode. Another one is shown above: in the **Copy File** function, the **@keydown** modifier is used to change the button's function based on whether the **Shift** key is held down or not. See the [Command modifiers](../command_modifiers.md) page for more information on modifiers.

##### Function types

The **Function** drop-down in Advanced mode lets you select from three types of functions:

- **Standard Function**: This is used for most commands, and is the option you will most often select. Both internal Opus functions and the launching of regular external Windows programs work in this mode.
- **[MS-DOS Batch Function](../ms-dos_batch_commands.md)**: This is used to run MS-DOS type programs (including **.bat** scripts). It's intended for programs that don't open a window of their own, but instead are designed to print text to a DOS prompt.
- **[Script Function](/Manual/scripting/script_functions.md)**: This type is used to define a button written using an ActiveX scripting language like VBScript or JScript. After selecting this, additional controls will appear to let you select the scripting language. See the page on [Scripting](/Manual/scripting/README.md) for more details on scripts.
- **WSL Script Function**: This option is available if you have WSL (Windows Subsystem for Linux) installed from the Windows Store under Windows 10. It lets you run a WSL (Bash) script from within Opus.

##### Function editing

The multi-line text field is where you enter the instructions that make up the command. The toolbar along the top of the field contains a number of drop-downs that can help you build up the command:

- **Edit**: This dropdown contains a number of text editor-like functions for the edit field; clipboard operations, search and replace, etc.
- **Commands**: Displays a list of the [internal commands](/Manual/reference/command_reference/internal_commands/README.md) (including any [user-defined commands](/Manual/customize/creating_your_own_buttons/user-defined_commands.md)). Selecting one will insert the command into the function.
- **Arguments**: This is a context-sensitive drop-down that displays the arguments (if any) for the command that begins the line the cursor is on. So for instance, if you had selected **Copy** from the **Commands** drop-down, the **Arguments** drop-down would then show you the arguments for the **Copy** command. Again, selecting arguments from the drop-down menu inserts them into the body of the function. The **Arguments** drop-down also displays a list of the [external control codes](/Manual/reference/command_reference/external_control_codes/README.md) (which you can use with both internal commands and external programs to pass things like the names of selected files through to the command).
- **Browse**: This button displays a standard file browser dialog letting you locate an external program to run. The full path to the program will be inserted into the function.
- **Modifiers**: This displays a drop-down list (with descriptions) of the various [command modifiers](../command_modifiers.md) that you can use to change the behavior of commands.

Lines beginning with `//` are ignored, allowing you to put comments in your commands. The `//` must be at the very start of the line, with no spaces or anything else before it, for the line to become a comment.

Complex commands can be split over multiple lines. When a `[[` appears at the beginning of a line it indicates that what comes next is part of the previous command. For example, the following lines are interpreted as a single command:

    Find IN C:\
    [[QUERY *.jpg]]
    [[
    FILTERDEF
    size match > 100 kb
    and size match < 200 kb
    ]]

The **Run** button at the bottom of the dialog allows you to instantly run your command or script to test it out without having to close the button editor. You can use the <kbd>F5</kbd> hotkey to do the same thing. (When working on something complex, it's still a good idea to save your work occasionally, just in case! Saving only happens when you click OK in the button editor and then OK again in the Customize dialog to exit Customize mode.)

Buttons run from the editor will be run against the source folder tab in the lister which launched the editor. If your button requires selected files, you will probably find it useful to add the **[@nodeselect](/Manual/reference/command_reference/command_modifier_reference.md)** modifier on a line near the top of the command to prevent the selection being cleared each time you test the button. Depending on the type of button, you may or may not want to leave the modifier there once you are finished. When writing a script, you can do a similar thing using the **[Command](/Manual/reference/scripting_reference/scripting_objects/command.md)** object's **deselect** property, and the default script you get when entering script mode shows you an example of how to use it.

Test-running a script will also cause an output panel to open at the bottom of the editor where any error messages or strings passed to the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).Output** method will appear. These will also appear in the Script Log if you have it turned on in the lister.
