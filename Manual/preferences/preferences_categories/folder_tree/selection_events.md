# Selection Events

These options let you override the command that runs when a folder in the Folder Tree is selected using the mouse. You can configure commands for both the left and middle mouse buttons (the right mouse button is always used for the context menu), and you can have separate commands for when the **Alt**, **Control** and **Shift** keys are held down.

  
The command for each event must be a command that would make sense on a button or hotkey. You can use [Opus internal commands](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) or external programs (passing arguments to them using the [standard control codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)). If you want to run more than a simple single-line command, you can create a more complicated [User](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md) command and then specify the name of the user command for the event.

  
The default settings for these events are:

- **Left mouse button**:  
  \* **Normal**: **Go**. Reads the selected folder into the file display currently associated with that tree.

      * **Alt**: **Go NEWTAB**. Reads the selected folder into a new tab.

      * **Ctrl**: **Go OPENINDUAL**. Reads the selected folder into the dual display - the file display **not** currently associated with the tree. If the tree isn't currently in dual display mode it will be put into that state automatically.

      * **Shift**: Nothing defined.

- **Middle mouse button**:  
  \* **Normal**: **Go NEWTAB**. Reads the selected folder into a new tab. 

      * **Alt**: Nothing defined.

      * **Ctrl**: **Go NEWTAB OPENINDUAL**. Reads the selected folder into a new tab in the other file display.

      * **Shift**: Nothing defined. 

So from the above we can see that by default, left-clicking a folder will read the folder as normal, **Alt**-clicking a folder will read it in a new tab, and **Ctrl**-clicking will read it into the dual display. Middle-clicking a folder will read it in a new tab (the same as **Alt**-left-click) and **Ctrl**-middle-click will open it in a new tab in the other display.

Say you wanted it so that **Shift**-clicking a folder would open it in a new Lister automatically. You could do this by setting the **Left mouse button** / **Shift** event to the command **Go NEW**.

You may also want to change it so that left-clicking a folder that's already open in a tab will switch to that tab rather than reading it into the current tab. The command for this would be **Go TABFINDEXISTING**.
