# Find Files

The Opus Find tool has two main modes of operation; [simple](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md) and [advanced](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/RAEDME.md). The simple-mode Find tool lets you quickly search the current folder (or any location) for files or folders by *name*, *date*, *size*, *type* or by *text they contain*. The advanced-mode Find tool uses a [Filter control](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/RAEDME.md) to let you specify much more complex search queries. Using the advanced mode you can search based on attributes like image dimensions, audio bitrate, document author, etc.

Opus also supports an alternate search system - the integrated support for [Windows Search](windows_search.md) lets you use the Windows search index to perform quick searches using a text field on the toolbar. You may find the indexed search is enough for your purposes - it will usually be quicker, although it doesn't provide as much control over the parameters of the search as the Opus Find tool.

To access the Opus Find tool, select the **Find Files** command from the **Tools** menu. The Find tool appears at the bottom of the Lister in the [Utility Panel](../the_lister/utility_panel.md).

The top section of the Find panel lets you specify the location or locations to search. You can search one or more folders (or entire drives) at once by adding entries to the **Find in** list.

![](/Manual/images/media/find_-_location.png)

Each entry in the list corresponds with a folder to search. To add a folder to the list, double-click the *Add folder to search* item. You can edit a folder path in the list by double-clicking it (or select it and press **F2** if you want to enter the path using the keyboard).

You can also use the **Select Folders to Search** (![](/Manual/images/media/dupe_files_-_select.png)) button on the toolbar - this displays a folder selection dialog with checkboxes so you can select multiple folders simultaneously. This button also has a drop-down attached to it that displays a *most-recently used* list, which lets you select from your recent search locations.

To remove a folder from the **Find in** list, select it and click the **Remove Folder** (![](/Manual/images/media/dupe_files_-_delete.png)) button. The **Reset Folder List** (![](/Manual/images/media/dupe_files_-_reset.png)) button clears the folder list, and the **Lock Folder** (![](/Manual/images/media/dupe_files_-_lock.png)) button locks the **Find in** location to the folder displayed in the current file display. When the folder is locked, the **Find in** list will automatically reset to the current location whenever you navigate in the file display.

The **Refine** checkbox becomes available after using the Find tool once and allows you to narrow down the results of a previous find. **Refine** is usually left off, in which case using the Find tool again will cause it to start from scratch and return everything below the **Find In** folders which matches your new criteria. On the other hand, if you turn on **Refine** and use the Find tool again then it will apply your new criteria on top of the previous results leaving you with only the things which match both your old and new criteria.

As an example of what **Refine** does, consider a folder that contains these files:

- Directory Listing.txt
- Directory Opus.txt
- Magnum Opus.txt Asking for files with "Directory" in their names will give these two results:

- Directory Listing.txt
- Directory Opus.txt If you then turn on **Refine** and ask for names containing "Opus" then you'll get just the file which matches both your original request ("Directory") and your new one ("Opus"):

- Directory Opus.txt (Of course, you could have specified "Directory Opus" in the first place but there are times when you are not sure exactly what to look for or how many results you'll get back.)

On the other hand, if you turn off **Refine** and ask the tool to find files with "Opus" in their names, you'll get everything containing "Opus", regardless of what was done before:

- Directory Opus.txt
- Magnum Opus.txt

To the right of the **Find in** list are a number of options that control how Opus searches for files.

- **Show results in**: This lets you specify the name of the [File Collection](../virtual_file_system/file_collections/RAEDME.md) that the results of the search will be displayed in. If the specified collection doesn't already exist it will be created automatically. Normally the current file display will automatically navigate to show this collection when the search begins, but you can use the drop-down below the **Show results in** field to specify that the collection should be shown in the destination (rather than the source) file display, and also opt to have it shown in a new [tab](../the_lister/tabs/RAEDME.md). As files are found by the Find tool they will appear in the collection.
- **Clear previous results**: If this option is on the contents of the **Show results in** file collection will be automatically cleared before the search begins. On the other hand, if the option is off then any files which you find will be added to the existing results collection, allowing you to accumulate the results of several otherwise unrelated find operations.
- **Search inside subfolders**: The function will search the contents of all sub-folders of the specified locations as well as the locations themselves.
- **Search inside archives**: The function will also search the contents of any archive files that are found in the specified locations.

The bottom part of the Find panel is where select the mode (simple or advanced), and where you define the parameters of the search.

![](/Manual/images/media/find_-_mode_tabs.png) 

The mode can be selected using the tab control. Please see the [Simple Find](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md) and [Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/RAEDME.md) pages for more information about the two modes. When you have defined your search parameters, click the **Find** button to begin the search.

More:

[Simple Find](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md)  
[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/RAEDME.md)  
