# Copy Options

This page controls options that affects how Directory Opus copies files. These options can all be overridden at the command level by supplying different parameters to the [Copy](/Manual/reference/command_reference/internal_commands/copy.md) command. Several conditions require Opus to ask for confirmation before copying files; the options that affect this are:

- **Ask for confirmation before overwriting existing files**: If files you are copying already existing in the destination, Opus will prompt you before overwriting them. This can be overridden by the **WHENEXISTS** argument to the **Copy** command.
- **Ask for confirmation before overwriting read-only files**: This option causes an additional confirmation to be displayed if the existing file has its read-only (**R**) attribute set.
- **Ask for confirmation before merging existing folders**: Unlike a file, where copying over an existing file deletes the original, copying over an existing folder has the effect of merging the contents of the two folders. Only files within the target folder that clash with files in the source folder will actually be deleted, and so this is generally a non-destructive operation. This option causes confirmation to be displayed before Opus merges one folder with another. This can be overridden by the **WHENEXISTS** argument to the **Copy** command.
- **When copying in Flat View mode**: Files displayed in Flat View can exist in physically different folders. If you select files from multiple folders for a copy operation, Opus gives you the choice of copying them all to the target folder, or of recreating their original folder structure in the target. You can choose *ask how to copy*, and Opus will prompt you each time, or select *copy to single level* or *recreate source folder structure*.  This option can be overridden by the **FLATVIEWCOPY** argument to the **Copy** command.
- **When copying folders to a Collection**: When you copy (add) a folder to a File Collection, you have the option of adding the folder to the collection directly (in which case it appears like any other collection member), or adding it as a sub-collection. In this second case, the folder will appear as a collection in its own right, and the folder's contents will be added to the sub-collection. This option lets you choose *ask how to copy*, *add to collection as a member* or *add to collection as a sub-collection*. This can be overridden by the **COPYTOCOLL** argument.

Additional options on this page are:

- **Sort newly created and copied files**: Normally when files are copied to or created in a file display, they are automatically sorted into their proper position (based on the current sorting parameters). If you turn this option off they will instead be added, unsorted, to the end of the list.

�
