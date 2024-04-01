# Delete

The **Delete** internal command can be used to:

- Recycle files and folders (delete them to the recycle bin)
- Delete files and folders permanently (bypassing the recycle bin)
- [Securely erase](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.md) files so they can't ever be recovered
- Empty the recycle bin
- Remove items from a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md)

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ALL</td><td>
/S</td><td>

*(no value)*</td><td>

Delete all files and folders without prompting. This can be used to override the **Ask for confirmation for each file before deleting** and **Ask for confirmation for each folder before deleting** options on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

*Example:* `Delete ALL`
</td></tr><tr><td>
EMPTYRECYCLE</td><td>
/O</td><td>

*(no value)*</td><td>

Empty the system recycle bin. You can combine with the **FORCE** argument to suppress the confirmation prompt, and the **QUIET** argument to suppress the progress dialog.

*Example:* `Delete EMPTYRECYCLE FORCE QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

*\<drive letter\>*</td><td>

Empty the recycle bin for a specific drive.

*Example:* `Delete EMPTYRECYCLE=C:`
</td></tr><tr><td>
ERASEEMPTYSPACE</td><td>
/O</td><td>

*(no value)*</td><td>

Erase empty space on the current drive. Empty space will be overwritten with random data to ensure deleted files cannot be recovered. This can take a long time, and generally only makes sense with HDDs, not SSDs. (To secure-erase a single file (that hasn't been deleted yet) instead, see the **SECURE** argument instead.)

*Example:* `Delete ERASEEMPTYSPACE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<drive letter\>*</td><td>

Erase empty space on the specified drive. Must be the first parameter.

*Example:* `Delete ERASEEMPTYSPACE=D:`
</td></tr><tr><td>
</td><td>
</td><td>

*passes:\<n\>*</td><td>

Specifies the number of erase passes, from 1 to 32. If omitted, the previous number of passes will be remembered, and a single pass will be used if no previous number exists.

*Example:* `Delete ERASEEMPTYSPACE=passes:1`

If both a drive letter and pass count are given, the drive letter must be the first parameter.

*Example:* `Delete ERASEEMPTYSPACE=D:,passes:2`
</td></tr><tr><td>
FAILNOTEMPTY</td><td>
/S</td><td>

*(no value)*</td><td>

Fail when attempting to delete a non-empty folder, or any file. Must be combined with the **NORECYCLE** argument.

*Example:* `Delete FAILNOTEMPTY NORECYCLE`

Use **SKIPNOTEMPTY** instead if you want the command to continue considering other items after encountering a file or non-empty folder.
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

Specifies the name of the file or files to delete. If you don't provide this argument the command will delete all selected items in the source Lister. This is the default argument for the **Delete** command - you don't need to specify the **FILE** keyword.

If you only specify the filename instead of the full path of the file or files, Opus will look in the current source folder. You can also specify a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Remember that if the filename contains spaces you need to enclose it in quotes.

*Example:* `Delete *.tmp`
</td></tr><tr><td>
FILTER</td><td>
/O</td><td>

*(no value)*</td><td>

Delete with filtering enabled (without having to activate the [delete filter](/Manual/file_operations/filtered_operations/README.md) in the Lister first). Opus will prompt you to define the filter.

*Example:* `Delete FILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter\>*</td><td>

Delete using the specified filter. This must have previously been created from the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences.

You can also directly specify a [simple wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). When specifying a simple wildcard pattern as the filter, it only affects which files are deleted; all selected folders and sub-folders are deleted unless they contain a file which doesn't match the filter and thus isn't deleted.

*Example:* `Delete FILTER "temp files"`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

Delete with filtering enabled if the <kbd>Shift</kbd> key is held down. Opus will prompt you to define the filter.

*Example:* `Delete FILTER=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

Delete with filtering enabled if the <kbd>Alt</kbd> key is held down.

*Example:* `Delete FILTER=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

Delete with filtering enabled if the <kbd>Ctrl</kbd> key is held down.

*Example:* `Delete FILTER=ctrl`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to only delete matching files from selected folders. This is similar to the **FILTER** argument, however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `Delete FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FORCE</td><td>
/S</td><td>

*(no value)*</td><td>

Force the deletion of any files that are marked as read-only (have the **R** attribute set). This overrides the **Delete read-only files automatically (without asking)** option on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

*Example:* `Delete FORCE`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(no value)*</td><td>

The default behaviour for the **Delete** command is to operate on either the source file display, or the Folder Tree, depending on which one has the input focus. This lets you use the same command to delete folders in the tree as well as items in the file display. Specify this argument to force the command to always operate on the source file display and ignore the folder tree.

*Example:* `Delete NOFROMFOCUS`
</td></tr><tr><td>
NORECYCLE</td><td>
/S</td><td>

*(no value)*</td><td>

Prevent the use of the recycle bin - files will be permanently deleted. This overrides the **Delete to Recycle Bin where possible** option on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

*Example:* `Delete NORECYCLE`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(no value)*</td><td>

Prevent the display of any confirmation dialogs or error messages.

*Example:* `Delete FORCE QUIET`
</td></tr><tr><td>
RECYCLE</td><td>
/S</td><td>

*(no value)*</td><td>

Delete files by moving them to the recycle bin (if possible - not all drives support the recycle bin). Deletes to the recycle bin are not permanent - the files can be recovered until the bin is emptied. This overrides the **Delete to Recycle Bin where possible** option on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

*Example:* `Delete RECYCLE`
</td></tr><tr><td>
REMOVECOLLECTION</td><td>
/O</td><td>

*(no value)*</td><td>

Remove selected files and folders from the file collection. If used outside of a file collection this command will do nothing.

*Example:* `Delete REMOVECOLLECTION`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

When used on files and folders in a file collection, the items will be removed from the collection. When used outside of a file collection, the items will be deleted as normal.

*Example:* `Delete REMOVECOLLECTION=auto`
</td></tr><tr><td>
SECURE</td><td>
/O</td><td>

*(no value)*</td><td>

Perform a secure delete using the number of passes specified on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

*Example:* `Delete SECURE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<passes\>*</td><td>

Perform a secure delete using the specified number of passes (from 1 to 32 depending on your level of paranoia :)

*Example:* `Delete SECURE=5`
</td></tr><tr><td>
SHIFT</td><td>
/S</td><td>

*(no value)*</td><td>

Modifies the behaviour of the **Delete** command if the <kbd>Shift</kbd> key is held down.

- If the **Delete to Recycle Bin** option is selected on the **[File Operations / Delete Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences, holding the <kbd>Shift</kbd> key down will disable the use of the recycle bin.
- If the **Delete to Recycle Bin** option is not selected, the command acts as if the **ALL** and **FORCE** arguments are specified. In either case, if the <kbd>Shift</kbd> key is not held down, the **SHIFT** argument has no effect on the normal operation of the command. This argument is used to emulate the behaviour of Explorer.

*Example:* `Delete SHIFT`
</td></tr><tr><td>
SKIPNOTEMPTY</td><td>
/S</td><td>

*(no value)*</td><td>

Skip over non-empty folders, and all files, without deleting them, while still considering subsequent items for deletion. Must be combined with **NORECYCLE**.

*Example:* `Delete NORECYCLE SKIPNOTEMPTY`

Use **FAILNOTEMPTY** instead if you want the command to stop completely as soon as it encounters any file or non-empty folder.
</td></tr></tbody>
</table>

