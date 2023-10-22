# Command modifiers

Opus supports various command modifiers that can be used in toolbar buttons and hotkeys to modify the behaviour of the function. A command modifier is not a command itself - for the most part you can think of them as options that control how the function is executed.

Each modifier is given on a separate line - therefore, to use command modifiers in a function, you must edit the function in the [advanced command editor](command_editor/advanced_command_editor.md) (as the simple editor does not support multiple-line functions). Some modifiers (like **@async**) affect an individual command in the function, and are given on the same line as the command - others affect the whole function, and are supplied on a line by themselves.

![](/Manual/images/media/command_modifiers_001.png) 

This screenshot is an example of a simple function that makes use of two command modifiers:

- The **@filesonly** modifier causes the function to only use selected files - any currently selected folders will be ignored. The **{f}**[external control code](/Manual/reference/command_reference/external_control_codes/RAEDME.md) means each filename will be passed in turn to Notepad.
- The **@async** modifier causes the command following it, **notepad.exe** in this instance, to run asynchronously. If multiple files are selected, an instance of notepad.exe will be executed for each file, without waiting for the previous instance to return.

See the [Command modifier reference](/Manual/reference/command_reference/command_modifier_reference.md) page for a full list of the available command modifiers.
