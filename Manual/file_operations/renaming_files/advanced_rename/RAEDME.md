# Advanced Rename

The Advanced Rename dialog lets you perform complicated batch renaming operations. You can use wildcards or regular expressions, find and replace, create macros, modify capitalization, number or renumber files, rename using file metadata and even write complicated rename scripts using this dialog.

To access the Advanced Rename function, select the files you wish to rename and click the **Rename** button on the toolbar.

![](/Manual/images/media/advanced_rename.png) 

The Advanced Rename dialog has five distinct sections:

1.  The left panel is the **[presets list](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.md)**, where you can load and manage your rename presets.

1.  The top section controls the **[rename mode](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/RAEDME.md)** (described below) and lets you edit the **old name** and **new name** strings. These are used, among other things, to provide wildcard patterns or find and replace strings.

1.  The **[actions](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/RAEDME.md)** section controls the transformations that will be applied to each filename. The script **edit** button is used to expand the dialog to reveal the rename script editor.

1.  The **[options](/Manual/file_operations/renaming_files/advanced_rename/rename_options.md)** section contains several checkboxes that control the rename operation.

1.  Finally, the **preview** section displays a preview of the transformed filenames. Each file listed in the preview list (except for those from sub-folders) has a checkbox that you can use to remove the file from the rename operation.

When the **Use preview list to build macros** option is turned on, the preview list also doubles as the [macro builder](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md), a powerful mass-editing feature for making the same changes to every filename at once. When that option is turned off, you can edit the new filenames individually. Editing individual names is great for making small changes which the macro (or other batch operations) may not have got exactly right. Once the name for a file has been edited directly it will be displayed in red and the name is locked in until the rename operation occurs (or until you clear the custom name).

The Clipboard button ( ![](/Manual/images/media/clipmenu_001.png) ) contains commands that let you copy the full list of original filenames to the clipboard, so that you can paste them over another set of files, or edit them in an external text editor or spreadsheet. With filenames in the clipboard (one per line), use the **Paste new names from clipboard** command to paste them into the *Rename* dialog. The menu also contains **Prefix**, **Append** and **Reset** commands. **Prefix** and **Append** let you add the clipboard content to the start or end of the existing names instead of replacing the names. If one line is in the clipboard, it will be added to every name. If multiple lines are in the clipboard, one will be added to each name, and blank lines can be used to skip names. (If the number of files is larger than the number of lines, the clipboard content will loop around.) Finally, the **Reset** option clears any new names set via the same menu or via manually typing over individual names.

The macro builder cannot be used at the same time as the Clipboard **Paste**, **Prefix** and **Append** commands; it will be turned off if you use them. If you need to apply macros to names from the clipboard, paste the new names, then click Apply, then use the macro builder. (Note that the macro builder can also use the clipboard, copy and paste in its own way. See the [macro builder](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md) page for details.)

Once you've configured your Rename parameters, you can click **OK** to close the dialog and perform the rename. Alternatively, the **Apply** button allows changes to be applied to the selected files while leaving the Rename dialog open. Once you use the **Apply** button the **Undo** button next to it becomes available, allowing you to undo the rename you just applied.

More:

[Rename Presets](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.md)  
[Rename Modes](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/RAEDME.md)  
[Rename Actions](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/RAEDME.md)  
[Rename Options](/Manual/file_operations/renaming_files/advanced_rename/rename_options.md)  
[Renaming with Metadata](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md)  
[Rename Scripts](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.md)  
