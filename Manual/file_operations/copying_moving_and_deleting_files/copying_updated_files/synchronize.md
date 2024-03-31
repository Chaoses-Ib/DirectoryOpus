# Synchronize

The **Synchronize** tool lets you synchronize the contents of two folders. The folders involved can be any location that Opus can access - local drives, archives, network shares or even on an FTP site. You can specify the criteria used to determine whether a file should be copied or not, and you can choose whether synchronization is one-way or two-way. To access the Synchronize tool, select the **Synchronize** command from the **Tools** menu.

![](/Manual/images/media/13/sync_-_panel.png)

The **Synchronize** tool is displayed in the **[Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md)** at the bottom of the Lister.

Synchronize is a two-step process:

- First a **comparison** stage is run, which identifies files that need to be copied and/or deleted
- Secondly the actual **synchronize** takes place, once you've verified that the results of the comparison stage are correct

### Comparison mode

The left half of the panel contains options that control the comparison stage.

- **Copy files in both directions**: Files will be copied in both directions (a *two-way copy*). The comparison in this mode is simply based on file modification date - where the same file exists in both locations, the newer one will be copied over the top of the older one.
- **Copy files from left to right**: Files will be copied from the left to the right (or from **source** to **destination** - a *one-way copy*) only. In this mode you can choose the comparison method used to determine whether a file needs to be updated or not.

### One-way copy mode options

In one-way copy mode, the comparison methods you can choose are:

- **Byte comparison**: The file in the destination folder is compared byte-for-byte against the source file and replaced if it differs. Even though the actual comparison is only done if the two files have the same size, this mode can still be very slow compared to the other options.
- **Date (different)**: The file in the destination folder will be replaced if its last modified timestamp is different to that of the source file.
- **Date (different) or size**: The file will be replaced if either its last modified timestamp or its size are different to that of the source file.
- **Date (newer)**: The file will be replaced if the last modified timestamp of the source file is newer than that of the existing one.
- **Date (newer) or size**: The file will be replaced if the timestamp of the source is newer or the size is different.
- **Size (different)**: The file will be replaced if its size is different to the size of the source file.
- **Size (larger)**: The file will be replaced if its size is different to the size of the source file.
- **Size (smaller)**: The file will be replaced if its size is different to the size of the source file.

Other options available in one-way copy mode:

- **Delete files from destination that aren't in the source**: Deletes files from the destination directory if they don't exist in the source folder. This option is not available in two-way copy mode since in that mode files that exist in one folder but not the other will be copied.
- **Delete before copy**: When the above option is enabled, this option makes Opus perform the delete operation before the copy operation, instead of after. You may want to use this option if you are worried that the destination drive won't have enough space.

### General comparison options

Other options which control the comparison stage in both one-way and two-way mode:

- **Filter**: This option lets you specify a filter to control which files are synchronized. You can either enter a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) directly, select a [pre-configured filter](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md) from the drop-down, or click the **Define** button to [define a new filter](../../filtered_operations/README.md).
- **Hide unaffected files**: If this option is on then any files that don't need to be synchronized (in either direction) will be hidden when the comparison is performed. This can be handy when you have a very large directory tree that might only have a few files that need to be synchronized - it makes it much easier to see what's going to happen. You can also hide unaffected files manually (or show them again) by right-clicking the background of the file display and choosing the **Hide unaffected items** or **Reveal hidden items** context menu commands.
- **Ignore one hour time differences**: This option enables daylight savings compensation. Some file systems (FAT/FAT32, and some FTP servers) store timestamps as local time rather than as an absolute UTC time. What this means in practical terms is that when your system clock changes forward or back one hour for the beginning or ending of daylight savings (summer time), all your files can suddenly look like their timestamps have changed. If you turn this option on then Opus will ignore timestamp changes of exactly one hour.
- **Ignore seconds**: Ignores seconds when comparing the dates of two files. For example, the dates **21-Feb-2010 10:35:12** and **21-Feb-2010 10:35:38** would be considered the same with this option turned on. This can be useful when synchronizing between locations that don't store timestamps to the same resolution (e.g. some FTP servers don't store seconds at all, so without this option your files would almost always look like they were out-of-date even if they weren't).
- **Only compare existing files**: Normally the synchronize function will copy files that don't exist as well as those that already exist but are different (based on the comparison method chosen). If this option is turned on then only files that already exist but are different will be copied - files that don't already exist on both sides will be ignored.

### Synchronize location

The fields on the right of the panel determine which folders are synchronized. Depending on the **Synchronize left-to-right** option, these fields are either called **Source** and **Destination**, or **Left** and **Right**.

When the panel opens the location fields will default to the locations in the current source and destination file displays.

Each field has a "link" button which lets you link it to the current location in the Lister. When the field is linked it will update automatically whenever you navigate to a new location - this lets you use the Lister for navigation without having to update the location fields manually.

You can use the **Browse** buttons for each field to select a different location, or type the path in manually.

The **Swap** button to the right of the location fields swaps the values of the fields around.

The options below the location fields are:

- **Synchronize left-to-right**: When turned on, the synchronize panel gets its source path from the left (or top) file display and its destination path from the right (or bottom) file display, even if the actual source/destination status of the two file displays is reversed. Turn this on to prevent accidentally performing a sync in the wrong direction. When this is off, clicking within the right (or bottom) file display may cause the synchronization to be performed in the opposite direction to what you expect unless you remember to click again on the left (or top) file display first. Of course, the difference matters most when doing a one-way copy.
- **Synchronize sub-folder contents**: Turn this option on if you want to synchronize the contents of sub-folders in the source and destination folder. If you leave this off then only files in the specified folders themselves will be synchronized.
- **Synchronize everything (including hidden files)**: Ignores any filters in effect in the source and destination and synchronizes all files, including any that are normally hidden.

### Excluding locations

The **Exclude** field lets you specify folders that are excluded from the synchronize operation.

![](/Manual/images/media/13/sync_exclude.png)

This field lets you enter one or more paths, or filenames, or wildcard patterns. Any folders that match will be excluded from the operation. In the screenshot above, any folders called **.svn** and **.github** would be excluded from the synchronize.

The two options in the drop-down let you automatically exclude hidden folders and system folders from the operation.

### Performing the comparison

Synchronization is a two-stage process - *comparison* followed by *synchronization*. The comparison stage is when Opus compares the source and destination folders and works out what needs to be copied and/or deleted.

After setting your desired options, click the **Compare** button in the bottom-right corner of the panel to begin the comparison. The procedure Opus follows when you do this is:

1.  If the Lister is not currently in dual-display mode, a second file display will be opened.
2.  The source and destination folders will be read into the source and destination file displays (if they're not already showing them).
3.  Both file displays will be put into [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) (actually a special variant of checkbox mode that's only used for Synchronize and the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md)).
4.  If the **Synchronize sub-folder contents** option is on, both file displays will be put into [Flat View (Grouped)](/Manual/basic_concepts/flat_view.md) mode, and Opus will read the contents of all sub-folders.
5.  The source and destination folders will be compared based on the options chosen. This step can take some time depending on the size of the folders involved.
6.  The files and folders selected for synchronization will be indicated as such with a series of glyphs in their checkboxes to indicate what action will be taken.
7.  If the **Hide unaffected files** option is on, any files not selected for synchronization will be removed from the display.
8.  The results of the comparison will be summarised in a dialog box.

### Comparison results

![](/Manual/images/media/13/sync_-_compare1.png) 

At this point, you can click the **Synchronize** button to begin the synchronization. If however you want to check the file list first to see exactly what's going to happen, or you want to make changes to the files selected for synchronization or to the comparison options, you can click the **Close** button to return to the Lister. You'll then see the following kind of display in the file list.

### Reviewing and changing synchronize actions

  
![](/Manual/images/media/13/sync_-_file_list.png) 

This screenshot corresponds to a one-way copy comparison. The files that have been selected for synchronization are marked with a series of glyphs that indicate the recommended action (copy, delete or no action). You can make changes to the synchronize action for a file or folder by simply clicking on its checkbox - Opus will cycle through the various actions available every time you click.

If you are dealing with a large number of files, you may wish to remove from the display those that you have marked to not be synchronized. To do this, right-click the background of the file display and choose the **Hide unaffected items** command from the context menu. Any files that are not marked as either copy or delete will be removed from the display. You can redisplay the hidden files with the **Reveal hidden items** command.

### Comparison errors

The results summary dialog will also inform you of any errors encountered during the comparison stage. An error can arise if a file on one side of the comparison has the same name as a folder on the other side.

If conflicts arise, the files and folders concerned will be skipped by the synchronization process - but if you want to investigate further and rectify the issue, you can click the **Conflicts** which appears in the summary dialog. This will return you to the Lister and highlight the conflicting items for you.

### Performing the synchronize

Once you've verified (and possibly modified) the synchronize actions, you can begin the synchronization by clicking the **Synchronize** button in the bottom-right corner of the panel.

If you change any of the options at this point the **Synchronize** button will be disabled and you will need to re-run the comparison by clicking **Compare** again before you can proceed with the synchronization. Once the synchronization stage begins, it proceeds as more or less an automated operation. The progress dialog will step through the various parts of the synchronization (copy from source to destination, copy from destination to source, delete from destination) as the operation progresses.
