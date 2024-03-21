# Duplicate File Finder

This tool lets you search your drives for duplicate files. This function has two distinct modes:

1.  To search for all files that appear more than once (i.e. *all* duplicate files).
2.  To search for duplicates of one or more specific files.

To access the duplicate file finder, select the **Find Duplicate Files** command from the **Tools** menu. The duplicate file finder appears at the bottom of the Lister in the [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md).

The top section of the duplicate file finder panel lets you specify where to search. You can search one or more folders (or entire drives) at once by adding entries to the **Find in** list.

![](/Manual/images/media/dupe_files_1.png) 

Each entry in the list corresponds with a folder to search. To add a folder to the list, double-click the *Add folder to search* item. You can also use the **Select Folders to Search** (![](/Manual/images/media/dupe_files_-_select.png)) button on the toolbar - this displays a folder selection dialog with checkboxes so you can select multiple folders simultaneously. You can edit a folder path in the list by double-clicking it (or select it and press **F2** if you want to enter the path using the keyboard).

To remove a folder from the list, select it and click the **Remove Folder** (![](/Manual/images/media/dupe_files_-_delete.png)) button. The **Reset Folder List** (![](/Manual/images/media/dupe_files_-_reset.png)) button clears the folder list, and the **Lock Folder** (![](/Manual/images/media/dupe_files_-_lock.png)) button locks the **Find in** location to the folder displayed in the current file display. When the folder is locked, the **Find in** list will automatically reset to the current location whenever you navigate in the file display.

The bottom section of the panel lets you specify which files you want to search for duplicates of. If this list is empty, the finder will search for *all* duplicated files (mode one). If you specify one or more files in this list, the finder will only search for duplicates of those files (mode two).

![](/Manual/images/media/dupe_files_2.png) 

Each entry in the list represents a file that the finder will search for duplicates of. To add a file to the list, double-click the *Add file to search for duplicates of* item, or click the **Browse** (![](/Manual/images/media/dupe_files_-_browse.png)) button on the toolbar. You can edit a file path in the list by double-clicking it (or select it and press **F2** if you want to enter the path by hand). Use the **Remove File** (![](/Manual/images/media/dupe_files_-_delete_file.png)) button to remove a file from the list, and the **Clear File List** (![](/Manual/images/media/dupe_files_-_reset_files.png)) button to clear it.

The right-hand side of the panel contains options that let you control how Opus searches for duplicates.

- **Show results in**: This lets you specify the name of the [File Collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) that the results of the search will be displayed in. The current file display will automatically navigate to show this collection when the search begins, and as files are found they will appear in the display. The display will be automatically grouped to keep duplicate files together. If the specified collection doesn't already exist it will be created automatically.
- The **Comparison method** drop-down lets you specify what method of comparison Opus uses to determine whether two files are duplicates:         
  - **Filename only**: The comparison is based on filename only. If two files have the same name they will be considered duplicates.
  - **Filename (no extension)**: This will search for files with the same filename stem, ignoring their file extension. For example, "grandma.mp3" and "grandma.jpg" would match.
  - **Filename and size**: The comparison is based on filename and size. If two files have the same name and are the same size they will be considered to be duplicates.
  - **Size**: The comparison is based only on file size. If two files are the same size they'll be considered to be duplicates.
  - **MD5 checksum**: This is the slowest but most accurate method of comparison. Filenames are not considered using this method; instead, for any two files Opus first compares their sizes. If the sizes are the same Opus then calculates the MD5 checksum for both files - if the checksum matches then the two files are considered to be duplicates. You can use the **MD5 accuracy** slider to reduce the accuracy of the comparison and speed up the search.
- **Clear previous results**: If this option is on the contents of the **Show results in** file collection will be automatically cleared before the search begins.
- **Delete mode**: If the reason you are searching for duplicate files is to eliminate wasted space, this mode can be handy. When this option is turned on and you perform a search, the file display showing the results is automatically put into [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md). When the search is complete, Opus will automatically select all but the first file of every duplicate file group. You can then use the **Delete** button at the bottom of the panel to delete the checked files. The **Select** button lets you re-run the delete selection process without having to re-run the search. This can be useful if you want to re-sort the list to affect which files are checked for deletion.
- **Filter**: The filter field lets you define a filter to control which files and locations are searched. You can use this in two ways:         
  - You can enter a [simple wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) to control which files will be considered by the duplicates search. For example, enter **\*.jpg** to only search for duplicate **JPG** files.
  - You can click the **Define Filter** button (![](/Manual/images/media/dupe_files_-_filter.png)) to define a filter using the advanced filter control (or use the drop-down to select a previously saved filter). You can use this to specify files to search for as well as control (using Sub-folder clauses) which sub-folders are searched. See the [Filtered Operations](/Manual/file_operations/filtered_operations/README.md) page for more information on filters.
- **Number duplicate groups**: The Duplicate Finder creates groups for each set of duplicate files found, and normally these groups are named after the criteria used for the duplicate search. If you turn this option on then each group of duplicates will be numbered (from 1 to *X*, in the order they are found).
- **Search inside archives**: The function will also search the contents of any archive files that are found in the specified locations.
- **Search inside subfolders**: The function will search the contents of all sub-folders of the specified locations as well as the locations themselves. You can use the **Filter** option below to control which sub-folders are searched.
- **MD5 accuracy**: When searching by checksum you can elect to only calculate a hash for a percentage of the file. This lets you speed up the operation for large files at the expense of accuracy. Use the slider control to adjust the percentage from 1% to 100%.

![](/Manual/images/media/md5_accuracy.png)

- **Use MD5 cache**: Use the MD5 checksums cache for large files located on NTFS partitions. If a large file's checksum is calculated it will be cached, and the cached value used in the future if the file doesn't appear to have changed.

When you have specified the locations and parameters for the duplicates search, click the **Find** button to begin.

When using the **Delete mode** option, you can override the main Preferences Recycle Bin setting when deleting any selected duplicate files.

![](/Manual/images/media/dupe_delete.png)

The **Delete** button in the bottom-right of the panel has a drop-down menu attached which lets you choose exactly how you want to delete the duplicates.
