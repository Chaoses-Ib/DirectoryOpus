# Synchronize

The **Synchronize** tool lets you synchronize the contents of two folders. The folders involved can be any location that Opus can access - local drives, archives, network shares or even on an FTP site. You can specify the criteria used to determine whether a file should be copied or not, and you can choose whether synchronization is one-way or two-way. To access the Synchronize tool, select the **Synchronize** command from the **Tools** menu.

![](/Manual/images/media/sync_-_panel.png)

The **Synchronize** tool is displayed in the **[Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md)** at the bottom of the Lister. The fields at the top of the panel control the folders that are being synchronized. When the panel opens the **Source** and **Destination** folders will default to the locations in the current source and destination file displays. You can use the **Browse** (![](/Manual/images/media/browse.png)) buttons for each field to select a different location, or type the path in manually.

The **Lock** (![](/Manual/images/media/dupe_files_-_lock.png)) buttons for each field let you lock the folder to the current location in the Lister. When the field is locked it will update automatically whenever you navigate to a new location - this lets you use the Lister for navigation without having to update the **Source** and **Destination** fields manually.

The **Swap** (![](/Manual/images/media/sync_-_swap.png)) button swaps the values of the **Source** and **Destination** fields around.

The **Options** section of the panel defines the type of comparison and other options affecting the synchronize operation.

- **Mode**: This lets you choose whether the synchronize operation is one-way or two-way.                          
  - **One-way copy**: Files will be copied from the **Source** to the **Destination** folder only. In this mode you can choose the comparison method used to determine whether a file needs to be updated or not.
  - **Two-way copy**: Files will be copied in both directions. Where the same file exists in both locations, the newer one will be copied over the top of the older one.

- **Compare**: In one-way copy mode, this drop-down lets you choose the comparison method used to determine whether an existing file needs to be updated.                  
  - **Byte comparison**: The file in the destination folder is compared byte-for-byte against the source file and replaced if it differs. Even though the actual comparison is only done if the two files have the same size, this mode can still be very slow compared to the other options.
  - **Date (different)**: The file in the destination folder will be replaced if its last modified timestamp is different to that of the source file.
  - **Date (different) or size**: The file will be replaced if either its last modified timestamp or its size are different to that of the source file.
  - **Date (newer)**: The file will be replaced if the last modified timestamp of the source file is newer than that of the existing one.
  - **Date (newer) or size**: The file will be replaced if the timestamp of the source is newer or the size is different.
  - **Size**: The file will be replaced if its size is different to the size of the source file.  
    In two-way copy mode you can't choose the comparison method as the only mode that makes sense is **Date (newer)**.              
- **Sync left-to-right**: When turned on, the synchronize panel gets its Source path from the left (or top) file display and its Destination path from the right (or bottom) file display, even if the actual source/destination status of the two file displays is reversed. Turn this on to prevent accidentally performing a synch in the wrong direction. When this is off, clicking within the right (or bottom) file display may cause the synchronization to be performed in the opposite direction to what you expect unless you remember to click again on the left (or top) file display first. Of course, the difference matters most when doing a one-way copy.
- **Delete files from destination that don't exist in the source**: In one-way copy mode you can turn this option on to delete files from the destination directory if they don't exist in the source folder. This option is not available in two-way copy mode since in that mode files that exist in one folder but not the other will be copied.
- **Delete before copy**: When the **Delete files from destination** option is enabled, this option makes Opus perform the delete operation before the copy operation, instead of after. You may want to use this option if you are worried that the destination drive won't have enough space.
- **Synchronize sub-folder contents**: Turn this option on if you want to synchronize the contents of sub-folders in the source and destination folder. If you leave this off then only files in the specified folders themselves will be synchronized.
- **Ignore seconds when comparing by timestamp**: When **Mode** is set to two-way copy, or one of the **Date** comparison methods is selected in one-way copy mode, this option causes Opus to ignore the seconds field of timestamps when comparing the dates of two files. For example, the dates **21-Feb-2010 10:35:12** and **21-Feb-2010 10:35:38** would be considered the same with this option turned on. This can be useful when synchronizing between locations that don't store timestamps to the same resolution (e.g. some FTP servers don't store seconds at all, so without this option your files would almost always look like they were out-of-date even if they weren't).
- **Filter**: This option lets you specify a filter to control which files are synchronized. You can either enter a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) directly, select a [pre-configured filter](/Manual/preferences/preferences_categories/file_operations/filters.md) from the drop-down, or click the **Define** button to [define a new filter](../filtered_operations/RAEDME.md).
- **Hide unaffected files**: If this option is on then any files that don't need to be synchronized (in either direction) will be hidden when the comparison is performed. This can be handy when you have a very large directory tree that might only have a few files that need to be synchronized - it makes it much easier to see what's going to happen. You can also hide unaffected files manually (or show them again) by right-clicking the background of the file display and choosing the **Hide unaffected items** or **Reveal hidden items** context menu commands.
- **Only compare existing files**: Normally the synchronize function will copy files that don't exist as well as those that already exist but are different (based on the comparison method chosen). If this option is turned on then only files that already exist but are different will be copied - files that don't already exist on both sides will be ignored.
- **DST Compensation**: This option enables daylight savings compensation. Some file systems (FAT/FAT32, and some FTP servers) store timestamps as local time rather than as an absolute UTC time. What this means in practical terms is that when your system clock changes forward or back one hour for the beginning or ending of daylight savings (summer time), all your files can suddenly look like their timestamps have changed. If you turn this option on then Opus will ignore timestamp changes of exactly one hour.
- **Automatically shrink panel**: If this option is on then when the comparison begins, the synchronize panel will be automatically shrunk down to a narrow bar at the bottom of the Lister. This results in the maximum amount of available space in the Lister for viewing the results of the comparison. To restore the panel after it has been shrunk, click the ![](/Manual/images/media/panel_-_grow.png) button on the right-hand side of the panel (or click on the header and drag it back up to the desired size).

Synchronization is a two-stage process - *comparison* followed by *synchronization*. The comparison stage is when Opus compares the source and destination folders and works out what needs to be copied and/or deleted. After setting your desired options, click the **Compare** button in the top-right corner of the panel to begin the comparison. The procedure Opus follows when you do this is:

1.  If the Lister is not currently in dual-display mode, a second file display will be opened.
2.  The source and destination folders will be read into the source and destination file displays (if they're not already showing them).
3.  Both file displays will be put into [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) (actually a special variant of checkbox mode that's only used for Synchronize and the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md)).
4.  If the **Synchronize sub-folder contents** option is on, both file displays will be put into [Flat View (Grouped)](/Manual/basic_concepts/flat_view.md) mode, and Opus will read the contents of all sub-folders.
5.  The source and destination folders will be compared based on the options chosen. This step can take some time depending on the size of the folders involved.
6.  The files and folders selected for synchronization will be indicated as such with a series of glyphs in their checkboxes to indicate what action will be taken.
7.  If the **Hide unaffected files** option is on, any files not selected for synchronization will be removed from the display.
8.  The results of the comparison will be summarised in a dialog box.

![](/Manual/images/media/sync_-_compare1.png) ![](/Manual/images/media/sync_-_compare2.png)

These images show two examples of the comparison results summary dialog. The one on the left was a comparison run on two folders in two-way copy mode - you can see that several files have been selected to be copied in each direction. The image on the right was the result of a one-way copy mode comparison on the same two folders. The same two files were selected to be copied from source to destination, but instead of three files being copied the other way, they are going to be deleted instead. This is because the copy is one-way only and the **Delete files from destination that don't exist in the source** option was enabled.

At this point, you can click the **Synchronize** button to begin the synchronization. If however you want to check the file list first to see exactly what's going to happen, or you want to make changes to the files selected for synchronization or to the comparison options, you can click the **Close** button to return to the Lister. You'll then see the following kind of display in the file list.

![](/Manual/images/media/sync_-_file_list.png) 

This screenshot corresponds to a one-way copy comparison from **B:\Home Shots** to **C:\Test\Pictures**. As you can see, the files that have been selected for comparison have been marked with a series of glyphs that indicate the recommended action: ![](/Manual/images/media/sync_-_copy_right.png) (copy to the folder on the right), ![](/Manual/images/media/sync_-_copy_left.png) (copy to the folder on the left) and ![](/Manual/images/media/sync_-_delete.png) (delete). For folders, the glyphs in grey (![](/Manual/images/media/sync_-_copy_left_grey.png) ![](/Manual/images/media/sync_-_copy_right_grey.png) and ![](/Manual/images/media/sync_-_delete_grey.png)) indicate that some but not all of the items within the folder have that state.

From the above screenshot you can see that in the destination, **IMG2488.jpg** and **IMG2494.jpg** did not exist, so these have been selected in the source to be copied. In the source, **IMG2487.jpg**, **IMG2493.jpg** and **IMG2489.jpg** did not exist, and so because the **Delete files from destination that don't exist in the source** option was enabled, these have been selected to be deleted. If we had used a two-way copy, they would have been selected to be copied to the source instead.

You can make changes to the synchronize action for a file or folder by simply clicking on its checkbox - Opus will cycle through the various actions available every time you click. If you are dealing with a large number of files, you may wish to remove from the display those that you have marked to not be synchronized. To do this, right-click the background of the file display and choose the **Hide unaffected items** command from the context menu. Any files that are not marked as either copy or delete will be removed from the display. You can redisplay the hidden files with the **Reveal hidden items** command.

The results summary dialog will also inform you of any errors encountered during the comparison stage. An error can arise if a file on one side of the comparison has the same name as a folder on the other side.

![](/Manual/images/media/sync_-_compare_errors.png) 

You can see that in this instance, the file **IMG2488.jpg** in the source folder clashed with a folder of the same name in the destination folder. If conflicts arise, the files and folders concerned will be skipped by the synchronization process - but if you want to investigate further and rectify the issue, you can click the **Conflicts** button at this point. This will return you to the Lister and highlight the conflicting items for you.

![](/Manual/images/media/sync_-_conflicts.png) 

Once you've verified (and possibly modified) the synchronize actions, you can begin the synchronization by clicking the **Synchronize** button in the top-right corner of the panel. If you change any of the options at this point the **Synchronize** button will be disabled and you will need to re-run the comparison by clicking **Compare** again before you can proceed with the synchronization. Once the synchronization stage begins, it proceeds as more or less an automated operation. The progress dialog will step through the various parts of the synchronization (copy from source to destination, copy from destination to source, delete from destination) as the operation progresses.

As an alternative to the **Synchronize** tool, Opus provides another, simpler method for updating the contents of one folder from another. See the [Copying Updated Files]() page for more information.
