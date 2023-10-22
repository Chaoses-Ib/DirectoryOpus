# Drag and drop

Drag-and-drop is a common way of moving files around in Windows. In Opus, drag-and-drop is controlled by the **[File Types](/Manual/file_types/RAEDME.md)** system. The default behaviour is the same as in Explorer:

- Drag-and-drop of a file to another folder on the same drive will move it
- Drag-and-drop to a folder on a different drive will copy it
- Holding the **Shift** key when dropping forces the file to be moved
- Holding the **Ctrl** key when dropping forces it to be copied
- Holding the **Alt** key when dropping creates a shortcut to the file
- Drag-and-drop with the right button displays a menu that lets you select *Copy*, *Move* or *Create Shortcut* as the action.

Internally, these actions are defined by the items on the **Events** tab for the **All files and folders** file type. Whereas in Explorer these actions are fixed, in Opus they are configurable.

\<WRAP c1borderless\> \|![](/Manual/images/media/default_draganddrop.png)\| \|This screenshot shows the [File Type editor](/Manual/file_types/filetype_editor/RAEDME.md) for the **All files and folders** file type. As you can see, the events are all defined as some variant of the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command.  
\<WRAP\>\<wrap topspace\>\</wrap\>

- *Drag-and-drop*: The **MOVEWHENSAME** argument specifies that the file is moved on the same drive, and copied otherwise.
- *Drag-and-drop + Alt*: The **MAKESHORTCUT** argument causes the Copy command to make a shortcut to the file.
- *Drag-and-drop + Ctrl*: The **RENAMEWHENSAME** argument will automatically rename the copied file if the name clashes with an existing one.
- *Drag-and-drop + Shift*: The **MOVE** argument causes the file to be always moved. \</WRAP\>Although not shown here, the **Drop Menu** tab also defines the contents of the menu shown when dragging with the right mouse button. This can also be configured.

Editing these functions modifies the drag-and-drop behaviour in Opus. For example, if you wanted drag-and-drop to always copy (rather than moving on the same drive), you could edit the command definition to **Copy RENAMEWHENSAME** (the same as the *Drag-and-drop + Ctrl* event).

The **All files and folders** file type is a special file type that by definition matches everything - both files and folders. You can use the File Types system to define overriding events for specific file types. For example, you could configure drag-and-drop of a Zip file to extract the contents of the archive when dropped with the **Shift** key held down.

See the documentation on the **[File Types](/Manual/file_types/RAEDME.md)** system for more information.  
\|

\</WRAP\>\<wrap clear/\>
