# Deleting Files

This page contains options that affect how Opus deletes files. Some of the options here can be overridden at the command level by arguments supplied to the [Delete](/Manual/reference/command_reference/internal_commands/delete.md) command.

- **Ask for confirmation before commencing delete**: This causes an initial confirmation prompt to be shown at the very beginning of a delete operation. It will give you a summary of the number of files and folders selected for delete. This can be disabled by turning this option off or with the `Delete` command's `QUIET` argument.
  - **Skip confirmation when deleting to Recycle Bin**: Because the Recycle Bin itself normally displays a confirmation dialog, you can choose to disable the above confirmation when using the Recycle Bin. If you have configured the Recycle Bin to not display a prompt, you may wish to leave this option off to allow the Opus confirmation to be shown.

- **Automatically select next file after deleting**: If this option is turned on, the file in the list following the deleted files will be automatically selected. This is useful in conjunction with the [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md) when you want to inspect and optionally delete multiple images, for example.
- **Delete to Recycle Bin where possible**: With this option on, Opus will delete to the system Recycle Bin whenever it's able to. If the recycle bin is disabled (globally, or for a particular drive), or when deleting from locations like network folders that don't support the Recycle Bin, files will be deleted directly (and therefore no undo would be available in those cases). This option can be overridden with the `RECYCLE` and `NORECYCLE` arguments, and the `SHIFT` argument can also affect whether the Recycle Bin is used or not.

##### When not using the Recycle Bin

When Opus deletes a file directly, as opposed to moving it to the Recycle Bin, the following options affect the behavior:

- **Ask for confirmation for each selected file before deleting**: With this option on, you will be prompted for each selected file, with the option to delete or skip it. You will only be prompted for files selected at the top level; you will not prompted for any files within any selected folders. This option can be overridden by the `Delete` command's `QUIET` argument.
- **Ask for confirmation for each selected folder before deleting**: With this option on, you will be prompted for each selected folder, with the option to delete or skip it. You will only be prompted for folders selected at the top level; you will not be prompted for any files or folders below those folders. This option can be overridden by the `Delete` command's `QUIET` argument.
- **Delete read-only files automatically**: With this option on, read-only files will be treated like any other - their **R** attribute will be cleared automatically so they can be deleted without showing an error. This option can be overridden with the `FORCE` argument.
- **Use Secure Wipe**: If this option is enabled, Opus will perform a secure wipe of each file before deleting it. This theoretically makes it impossible (or at least much harder) to recover the file contents. You can select the number of overwrite passes to perform. This will slow down deleting greatly - you will probably not want to turn it on here, but instead use the **Secure Delete** command (the `SECURE` argument for the `Delete` command) when appropriate.
