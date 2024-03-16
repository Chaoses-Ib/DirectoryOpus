# Copy and Paste

Copy-and-paste (or cut-and-paste) is possibly the simplest method of moving files around.

1.  Select the files you want to copy or move, choose the *Copy* (<kbd>Ctrl+C</kbd>) or *Cut* (<kbd>Ctrl+X</kbd>) command from the **Edit** menu
2.  Navigate to the target folder, and select *Paste* (<kbd>Ctrl+V</kbd>).

Moving files using the clipboard is implemented in almost all file managers the same way, although Opus does extend this functionality in a few ways, which it's worth being aware of.

##### Copy queues

Although these functions use the internal **[Clipboard](/Manual/reference/command_reference/internal_commands/clipboard.md)** command to initiate them, when you paste files into a Lister, the actual file copy or move is implemented "behind-the-scenes" using the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command.

This means that features like the [copy queue](copy_queues/RAEDME.md) are available for clipboard operations just like they are when [copying via the toolbar buttons](copying_using_the_toolbar_buttons/RAEDME.md).

You can control the queuing using the various arguments for the **[Clipboard](/Manual/reference/command_reference/internal_commands/clipboard.md)** command.

##### Pasting text and graphics data

If the clipboard contains text or graphics data, you can paste that in a Lister as if it were a real file. Opus will create a new file and write the clipboard data to it automatically.

- Text data will be written to a file called *Clipboard Text.txt*
- Graphical data will be written to a file called *Clipboard Image.jpg*

You can modify the format that graphics data is saved in (Bitmap, GIF, PNG or JPG) using the **clipboard_image_paste** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences. You can also use the **clipboard_image_paste_dpi** option to have the pasted image scaled automatically to compensate for the system DPI.

The name of the new file can be controlled using the various arguments for the **[Clipboard](/Manual/reference/command_reference/internal_commands/clipboard.md)** command.

##### Incremental clipboard

The **ADD** argument for the internal **[Clipboard](/Manual/reference/command_reference/internal_commands/clipboard.md)** command lets you add selected files to any that are already on the clipboard. For example, you could copy a few files from one folder, a few from another folder, and a few from a third folder, and then paste them all into the destination in one go.

To make use of this functionality, you would need to create a new toolbar button or hotkey that runs the `Clipboard COPY ADD` command (or assign this to a hotkey - for example, <kbd>Ctrl+C</kbd> runs `Clipboard COPY` by default, so you could assign this to <kbd>Ctrl+Shift+C</kbd>).

See the section on [Customize](/Manual/customize/RAEDME.md) for information about creating your own buttons and hotkeys.
