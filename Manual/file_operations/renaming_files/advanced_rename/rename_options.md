# Rename Options

The **Options** section of the Rename dialog contains options which don't affect the new filenames, but instead affect how the rename operation itself behaves.

![](/Manual/images/media/13/rename_options.png)

- **Apply actions even if pattern doesn't match**: If a selected file doesn't match the specified wildcard pattern, normally the rename command will skip it. If this option is on then options like **Capitalization** will be applied to all items whether they match the wildcard or not.
- **Automatically number files when names clash**: Appends an incrementing number to the new filename if the new name is already in use. If turned off and a new filename clashes with an existing one, an error dialog will be shown.
- **Hide unaffected items in preview**: Items whose names aren't going to be modified are hidden in the preview list. If turned off, they're shown in a different color.
- **Use preview list to build macros**: Enables the [macro recorder](rename_actions/rename_macros.md). When turned on, you can click on any "new name" in the preview list and edit the filename directly to record a macro that's then applied to all selected files. If this option is turned off, you can edit filenames individually in the preview list.
- **Rename files in selected sub-folders**: The rename operation will operate recursively on files in selected folders rather than renaming the folders themselves.
  - **Rename folders as well as their contents**: Both sub-folders and their contents will be processed by the rename operation.
  - **Show preview of sub-folder contents**: Shows a preview of the rename operation on the contents of any selected folders in the preview list. Note that you can't edit or turn off individual sub-folder files like you can with files at the top-level.
- **Rename matching filenames as one**: Multiple files with the same base filename (excluding file extension) will be treated as if they were the one file for the purpose of renumbering, wildcard or other batch renames. For example, if you had files called *01012.JPG* and *01012.WAV*, they would be given the same number as part of a renumber rename instead of being numbered sequentially.
