# User Commands

This page lets you create your own [user-defined commands](/Manual/customize/creating_your_own_buttons/user-defined_commands.md).

User-defined commands are pre-defined commands that you create yourself. Effectively it's like creating a toolbar button with your own function on it, but instead of a button on a toolbar it's a command in the command list that other buttons or menus can use just like an [internal command](/Manual/reference/command_reference/RAEDME.md).

Use the toolbar to create and manage your user commands.

##### Editing a user command

![](/Manual/images/media/13/user_command.png)

Editing a user command is similar to [editing a normal toolbar button](/Manual/customize/creating_your_own_buttons/command_editor/RAEDME.md), although there are a few specific fields for user commands:

- **Name**: This is the raw name of the command - it's the name that you need to use to run the command from buttons and menus.
- **Label**: This is the default label of the command. If you drag your command from the *Commands* tab and drop it on a toolbar, the created button will have this as its label (which can of course then be edited).
- **Description**: This becomes the default tooltip of the button when you drag the command from the *Commands* tab.
- **Template**: This specifies the *argument template* for the command - see below for more details.
- **Hide from Commands menu**: The command won't be displayed in drop-down command lists. This lets you create user commands that you can still use in buttons and hotkeys (or, for example, on a Preferences page like [Folder Tree Selection Events](/Manual/preferences/preferences_categories/folder_tree/selection_events.md)), but they won't clutter up the command list.

##### Argument templates

If you want to be able to pass arguments to your user command you need to give it an argument template. This uses the [same syntax](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) as for internal Opus commands.

In the above example, we only want a single string value. The argument has been given the name `EXT` in the template field. This is not the *value* of the argument (that doesn't exist until something uses this user command), but the *name* of the argument.

The function for the user command, `Select *.&EXT&`, calls the internal `Select` command, passing it a wildcard string that is built from the supplied `EXT` parameter. The argument name is supplied in the function definition surrounded by ampersands (`&` characters) which indicates to Opus that the value of that argument is to be inserted in the command line.

You could use this example command from a toolbar button like so:

|               |                                                                 |
|---------------|-----------------------------------------------------------------|
| Command line: | `Select_Files_Of_Type txt` |
| Runs:         | `Select *.txt`             |

##### More complex templates

In the above example, `EXT` is a string argument and so the value supplied is passed through unchanged to the user command, but for boolean options the behaviour is different. For example, consider the following user command:

|           |                                                                                  |
|-----------|----------------------------------------------------------------------------------|
| Name:     | `ExampleCmd`                                |
| Template: | `EXAMPLE1/S,EXAMPLE2/O`                     |
| Function: | `C:\DummyProgram.exe &EXAMPLE1& &EXAMPLE2&` |

The `ExampleCmd` user command will run the `C:\DummyProgram.exe` program when it's invoked. Its template has two boolean options:

- `EXAMPLE1`: a straight switch argument, either on or off.
- `EXAMPLE2`: an option switch argument, which can be off, on or have a string value supplied.

By default, a switch argument will insert the value `1` when it is set, and `0` when it isn't. For example, the following use of the user command would produce the following command line for *DummyProgram*:

|               |                                                                |
|---------------|----------------------------------------------------------------|
| Command line: | `ExampleCmd EXAMPLE1`     |
| Runs:         | `C:\DummyProgram.exe 1 0` |

However, you can use the `&..&` insert to specify the actual strings that are passed through for that argument. For example:

|               |                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------|
| Function:     | `C:\DummyProgram.exe &EXAMPLE1:yes:no& &EXAMPLE2:one:two&` |
| Command line: | `ExampleCmd EXAMPLE2`                                      |
| Runs:         | `C:\DummyProgram.exe no one`                               |

For option switch (**/O**) arguments this only applies if the argument has been used as a switch, and not to provide a string value - if a string value is supplied instead, it is passed through unchanged. For example:

|               |                                                                          |
|---------------|--------------------------------------------------------------------------|
| Command line: | `ExampleCmd EXAMPLE1 EXAMPLE2=test` |
| Runs:         | `C:\DummyProgram.exe yes test`      |

Your template can also specify a list of values for an option switch which will then be shown in the drop-down list in the [command editor](/Manual/customize/creating_your_own_buttons/command_editor/RAEDME.md), making it easy to pick the value for the argument. If you use this, you can also specify a default value, which will be passed through if a value is not given for the option. Consider the following template and the two example uses:

|               |                                                                           |
|---------------|---------------------------------------------------------------------------|
| Name:         | `ExampleCmd`                         |
| Template:     | `EXAMPLE/O[<default>,one,two,three]` |
| Function:     | `C:\DummyProgram.exe &EXAMPLE&`      |
| Command line: | `ExampleCmd EXAMPLE`                 |
| Runs:         | `C:\DummyProgram.exe default`        |
| Command line: | `ExampleCmd EXAMPLE=two`             |
| Runs:         | `C:\DummyProgram.exe two`            |

##### Conditional testing

You can use the `@if:` [command modifier](/Manual/reference/command_reference/command_modifier_reference.md) to test the value of user command arguments to introduce simple conditional behaviour to your user commands (without resorting to scripting). For example:

    @if:&&EXAMPLE&&=one
    C:\Program1.exe
    @if:&&EXAMPLE&&=two
    C:\Program2.exe
    @if:else
    C:\DummyProgram.exe

You can also use the [Arg()](/Manual/reference/evaluator/arg.md) function in the [evaluator](/Manual/evaluator/RAEDME.md) to access command line arguments from evaluator code inside a user command. For example:

    @if:=(Arg("NAME")=="jon")
    echo Hi Jon!
    @if:else
    echo Who are you?
