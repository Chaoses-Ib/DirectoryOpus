# Unattended operation

The **Unattended** checkbox at the bottom of the Copy progress dialog is used to make a copy operation (including any copies in that queue) run non-interactively.

![](/Manual/images/media/13/unattended_1.png)

When a copy operation is set to unattended mode, no error or confirmation dialogs are displayed during the copy process. Instead, any errors will be silently logged and you can review these, and retry the failed operations, at the very end of the operation. This lets you start a very long copy job (or queue a whole lot of very long copy jobs), and walk away (or go to bed!) without the risk that you'll come back after several hours to find the queue stalled because of an error or confirmation prompt.

![](/Manual/images/media/13/unattended_errors.png) 

You can use the **UNATTENDED** argument of the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command to automatically start a copy operation in unattended mode, and the **WHENEXISTS** argument can be used to set the default *When file exists* behaviour. See the description of the **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command for more information about these arguments, and the [Customize](/Manual/customize/README.md) section for information on how to configure a button or hotkey.

Turning on unattended mode adds the **Errors** tab to the copy progress dialog, which collects and displays all errors resulting from the operation.

##### Handling filename collisions

The options underneath *When file exists:* let you configure how Opus is to handle a filename collision (that is, when a file in the destination already exists with the same name as one being copied). Normally the [Replace Dialog](../the_confirm_file_replace_dialog.md) would be shown, but this option lets you instruct Opus to handle the situation in several different ways:

- **Replace**: Existing files will be overwritten.
- **Keep newer**: Existing files will be overwritten if the file being copied has a more recent timestamp (is newer).
- **Rename existing**: Existing files will be renamed so that the filename no longer clashes.
- **Skip**: The file will be skipped.
- **Treat as an error**: The file will not be copied, and an error will be logged. Logging an error means you can then retry the copy at a later time, and choose how to handle the collision yourself.
- **Resume**: When copying to or from an FTP site, this will attempt to resume the file copy if possible - if the existing file is smaller than the one being copied, and the remove server supports resume. If resume is not possible, the other selected option is used.
- **Merge folders without asking**: Overrides the **Ask for confirmation before merging existing folders** option on the **[Copying Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.md)** page in Preferences.
- **Skip identical**: Any conflicting files will be automatically skipped if they are identical (same size and date).

##### Retrying failed copies

The **Retry** button at the bottom of the tab lets you retry any failed copies.

The **Export error list** option will appear if any errors occur and this lets you save the list of failed operations to a file (in either text or CSV format).
