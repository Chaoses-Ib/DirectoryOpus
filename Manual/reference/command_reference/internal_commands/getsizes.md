# GetSizes

The **GetSizes** internal command can be used to:

- Calculate and display the total sizes of selected folders
- Calculate the total sizes of all folders in the current file display
- Calculate the MD5 checksum for all selected files

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Calculate the total size of all selected folders. If there are no folders currently selected, all folders in the current file display will have their sizes calculated.

*Example:* `GetSizes`
</td></tr><tr><td>
EVERYTHING</td><td>
/O</td><td>

*(no value)*</td><td>

Calculates the sizes of selected folders using [Everything](/Manual/additional_functionality/everything_integration.md) if possible. If Everything is not installed, or the current folder is not indexed, the sizes will be calculated manually (by recursively scanning the folder contents).

*Example:* `GetSizes EVERYTHING`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

If the option is set on the [Folder Sizes](/Manual/preferences/preferences_categories/folders/folder_sizes/README.md) Preferences page to use Everything to calculate folder sizes, this command overrides it and calculates them manually.

*Example:* `GetSizes EVERYTHING=no`
</td></tr><tr><td>
</td><td>
</td><td>

**only**</td><td>

Calculates the sizes of selected folders using Everything if possible. If not possible, sizes will not be calculated at all (nothing happens).

*Example:* `GetSizes EVERYTHING=only`
</td></tr><tr><td>
HASH</td><td>
/K</td><td>

*\<type\>*</td><td>

Calculate a checksum for all selected files using the specified hash algorithm. If the appropriate hash column is not currently displayed in the file display it will be added automatically. Using this command overrides the **max_md5_file_size** setting on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

Supported hash algorithms are **md5**, **sha1**, **sha256**, **sha512**, **crc32**, **crc32_php**, **crc32_php_rev**, and **blake3**.

*Example:* `GetSizes HASH=md5`
</td></tr><tr><td>
IGNOREJUNCTIONS</td><td>
/O</td><td>

*(no value)*</td><td>

Ignores junctions and softlinks within folders when calculating their size. This overrides the **Preferences / Folders / Folder Behaviour / Ignore junctions and softlinks when calculating folder sizes** Preferences option.

*Example:* `GetSizes IGNOREJUNCTIONS`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not ignore junctions and softlinks when calculating the sizes of folders.

*Example:* `GetSizes IGNOREJUNCTIONS=no`
</td></tr><tr><td>
NODESELECT</td><td>
/S</td><td>

*(no value)*</td><td>

Prevent the **GetSizes** command from deselected files and folders once their sizes/checksums have been calculated. This option only works if the **Postpone file deselection until end of function** option on the **[File Operations / Options](/Manual/preferences/preferences_categories/file_operations/options.md)** page in Preferences is turned on.

*Example:* `GetSizes NODESELECT`
</td></tr><tr><td>
USEHASHCACHE</td><td>
/S</td><td>

*(no value)*</td><td>

In conjunction with the **MD5** and **SHA** options, this enables the use of the checksum cache. If a file has previously had its checksum cached, and the file doesn't appear to have changed, the cached value will be used.

*Example:* `GetSIZES MD5 USEHASHCACHE`
</td></tr></tbody>
</table>

