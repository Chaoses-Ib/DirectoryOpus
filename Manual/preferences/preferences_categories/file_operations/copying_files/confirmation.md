# Confirmation

This page controls options that affects how Directory Opus asks for confirmation if needed when copying files. These options can all be overridden at the command level by supplying different parameters to the [Copy](/Manual/reference/command_reference/internal_commands/copy.md) command.

- **Ask for confirmation before overwriting existing files**: If files you are copying already existing in the destination, Opus will prompt you before overwriting them. This can be overridden by the `WHENEXISTS` argument to the `Copy` command.
- **Ask for confirmation before overwriting read-only files**: This option causes an additional confirmation to be displayed if the existing file has its read-only (**R**) attribute set.
- **Ask for confirmation before merging existing folders**: Unlike a file, where copying over an existing file deletes the original, copying over an existing folder has the effect of merging the contents of the two folders. Only files within the target folder that clash with files in the source folder will actually be deleted, and so this is generally a non-destructive operation. This option causes confirmation to be displayed before Opus merges one folder with another. This can be overridden by the `WHENEXISTS` argument to the `Copy` command.
- **Automatically rename when copying virtual files**: This affects copying from a "virtual" source, which is one where the files don't really exist on disk yet; typically when you drag & drop from a web browser to Opus. If a file with the same name already exists, and the option is on, the new file's name will be modified to make it unique without prompting. If the option is off instead, you'll be prompted for what to do. (For operations involving real files, you can change what happens by editing the File Type drag and drop events. This option exists because copies from virtual sources have to be treated specially and don't use the file type events.)

  
==When copying nested items==

In Flat View or with expanded sub-folders, it's possible to select files from one or multiple sub-folders at the same time. This option controls how those files are copied.

- **When copying nested items**: The options here are:
  - **Ask how to copy**: Opus will ask you what to do, every time.
  - **Copy to single level**: The files will all be copied to the destination folder.
  - **Recreate source folder structure**: The files will be copied to sub-folders in the destination, recreating their original locations relative to the source folder.
- **Copy to single level if all items are in the same folder**: This option affects what happens when all the selected items are in a single sub-folder underneath the source folder. With the option turned on, they would all be copied to the destination folder as normal. With the option off, the "nested items" option above comes into play to determine how to proceed.

This can be overridden by the `FLATVIEWCOPY` argument to the `Copy` command.

  
==When copying folders to a collection==

When copying folders into a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) you have the option of adding the folder to the collection directly (in which case it appears like any other collection member), or adding it as a sub-collection. In this second case, the folder will appear as a collection in its own right, and the folder's contents will be added to the sub-collection.

- **Ask how to copy**: Opus will ask you what to do, every time.
- **Add to collection as a member**: The folder will be added as an ordinary member of the collection.
- **Add to collection as a sub-collection**: The folder will be added as a sub-collection, with its contents as members.

This can be overridden by the `COPYTOCOLL` argument to the `Copy` command.

  
==Show rename presets in Confirm File Replace dialog==

You can select one or more of your saved [rename presets](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.md) to be available in the [file replace dialog](/Manual/file_operations/copying_moving_and_deleting_files/the_confirm_file_replace_dialog.md). The presets you turn on here can be found in the dropdown menu attached to the **Replace** button.

![](/Manual/images/media/13/replace_rename.png)

The dropdown shows separate options for both the *New* and *Old* files - selecting a preset from that menu will run it on either the existing file (old) or copy (new), allowing you to automatically rename the file to resolve a clash.
