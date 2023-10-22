# GetSizes

The **GetSizes** internal command can be used to:

- Calculate and display the total sizes of selected folders
- Calculate the total sizes of all folders in the current file display
- Calculate the MD5 checksum for all selected files

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Calculate the total size of all selected folders. If there are no folders currently selected, all folders in the current file display will have their sizes calculated.<br /><br />*Example:* `GetSizes` |
| EVERYTHING | /O | *(no value)* | Calculates the sizes of selected folders using [Everything](/Manual/additional_functionality/everything_integration.md) if possible. If Everything is not installed, or the current folder is not indexed, the sizes will be calculated manually (by recursively scanning the folder contents).<br /><br />*Example:* `GetSizes EVERYTHING` |
|  |  | **no** | If the option is set on the [Folder Sizes](/Manual/preferences/preferences_categories/folders/folder_sizes/RAEDME.md) Preferences page to use Everything to calculate folder sizes, this command overrides it and calculates them manually.<br /><br />*Example:* `GetSizes EVERYTHING=no` |
|  |  | **only** | Calculates the sizes of selected folders using Everything if possible. If not possible, sizes will not be calculated at all (nothing happens).<br /><br />*Example:* `GetSizes EVERYTHING=only` |
| HASH | /K | *\<type\>* | Calculate a checksum for all selected files using the specified hash algorithm. If the appropriate hash column is not currently displayed in the file display it will be added automatically. Using this command overrides the **max_md5_file_size** setting on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.<br /><br />Supported hash algorithms are **md5**, **sha1**, **sha256**, **sha512**, **crc32**, **crc32_php**, **crc32_php_rev**, and **blake3**.<br /><br />*Example:* `GetSizes HASH=md5` |
| IGNOREJUNCTIONS | /O | *(no value)* | Ignores junctions and softlinks within folders when calculating their size. This overrides the **Preferences / Folders / Folder Behaviour / Ignore junctions and softlinks when calculating folder sizes** Preferences option.<br /><br />*Example:* `GetSizes IGNOREJUNCTIONS` |
|  |  | **no** | Does not ignore junctions and softlinks when calculating the sizes of folders.<br /><br />*Example:* `GetSizes IGNOREJUNCTIONS=no` |
| NODESELECT | /S | *(no value)* | Prevent the **GetSizes** command from deselected files and folders once their sizes/checksums have been calculated. This option only works if the **Postpone file deselection until end of function** option on the **[File Operations / Options](/Manual/preferences/preferences_categories/file_displays/file_display_options.md)** page in Preferences is turned on.<br /><br />*Example:* `GetSizes NODESELECT` |
| USEHASHCACHE | /S | *(no value)* | In conjunction with the **MD5** and **SHA** options, this enables the use of the checksum cache. If a file has previously had its checksum cached, and the file doesn't appear to have changed, the cached value will be used.<br /><br />*Example:* `GetSIZES MD5 USEHASHCACHE` |

