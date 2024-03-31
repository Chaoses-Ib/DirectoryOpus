# Selection Events

This page lets you override the command that runs when a folder in the folder tree is selected using the mouse. You can configure commands for both the left and middle mouse buttons (the right mouse button is always used for the context menu), and you can have separate commands for when the <kbd>Alt</kbd>, <kbd>Ctrl</kbd> and <kbd>Shift</kbd> keys are held down.

The command for each event must be a command that would make sense on a button or hotkey. You can use [Opus internal commands](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) or external programs (passing arguments to them using the [standard control codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)). If you want to run more than a simple single-line command, you can create a more complicated [user-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md) and then specify the name of the user command for the event.

The default settings for these events are:

### Left mouse button

- **Default**: `Go`. Reads the selected folder into the file display currently associated with that tree.
- <kbd>Alt</kbd>: `Go NEWTAB`. Reads the selected folder into a new tab.
- <kbd>Ctrl</kbd>: `Go OPENINDUAL`. Reads the selected folder into the dual display - the file display **not** currently associated with the tree. If the tree isn't currently in dual display mode it will be put into that state automatically.

### Middle mouse button

- **Default**: `Go NEWTAB`. Reads the selected folder into a new tab. 
- <kbd>Ctrl</kbd>: `Go NEWTAB OPENINDUAL`. Reads the selected folder into a new tab in the other file display.
