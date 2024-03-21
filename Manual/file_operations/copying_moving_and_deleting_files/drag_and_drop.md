# Drag and drop

Drag-and-drop is a common way of moving files around in Windows. In Opus, drag-and-drop is controlled by the **[File Types](/Manual/file_types/README.md)** system.

##### Default drag-and-drop behavior

The default behavior is the same as in Explorer:

- Drag-and-drop of a file to another folder on the same drive will move it
- Drag-and-drop to a folder on a different drive will copy it
- Holding the <kbd>Shift</kbd> key when dropping forces the file to be moved
- Holding the <kbd>Ctrl</kbd> key when dropping forces it to be copied
- Holding the <kbd>Alt</kbd> key when dropping creates a shortcut to the file
- Drag-and-drop with the right button displays a menu that lets you select *Copy*, *Move* or *Create Shortcut* as the action.

Internally, these actions are defined by the items on the **Events** tab for the **All files and folders** file type. Whereas in Explorer these actions are fixed, in Opus they are configurable.

##### Configuring drag-and-drop actions

<img src="/media/13/default_draganddrop.png" class="align-right" data-query="?nolink" />This screenshot shows the [File Type editor](/Manual/file_types/filetype_editor/README.md) for the **All files and folders** file type. The events are all defined as some variant of the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command.

- Drag-and-drop: `Copy MOVEWHENSAME` moves the file on the same drive, and copies it otherwise.
- Drag-and-drop+<kbd>Alt</kbd>: `Copy MAKESHORTCUT` makes a shortcut to the file.
- Drag-and-drop+<kbd>Ctrl</kbd>: `Copy RENAMEWHENSAME` automatically renames the copied file if the name clashes with an existing one.
- Drag-and-drop+<kbd>Shift</kbd>: `Copy MOVE` always moves the file.

Although not shown here, the **Drop Menu** tab also defines the contents of the menu shown when dragging with the right mouse button. This can also be configured.

Editing these functions modifies the drag-and-drop behaviour in Opus. For example, if you wanted drag-and-drop to always copy (rather than moving on the same drive), you could edit the command definition to `Copy RENAMEWHENSAME` (the same as the *Drag-and-drop+*<kbd>Ctrl</kbd> event).

##### Overriding behaviour for specific file types

The **All files and folders** file type is a special file type that by definition matches everything - both files and folders. You can use the File Types system to define overriding events for specific file types. For example, you could configure drag-and-drop of a Zip file to extract the contents of the archive when dropped with the <kbd>Shift</kbd> key held down.

See the documentation on the **[File Types](/Manual/file_types/README.md)** system for more information.
