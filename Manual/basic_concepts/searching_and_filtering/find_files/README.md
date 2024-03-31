# Find Files

The Opus Find tool lets you search your drives for files and folders matching the criteria you specify. It has two main modes of operation:

- **[Simple](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md)** mode lets you quickly search by *name*, *date*, *size*, *type* or by *text they contain*.
- **[Advanced](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** mode uses a [filter control](/Manual/file_operations/filtered_operations/README.md) to let you specify much more complex search queries. Using the advanced mode you can search based on attributes like image dimensions, audio bitrate, document author, etc.

### Accessing the find tool

To access the Opus Find tool, select the **Find Files** command from the **Tools** menu, or press <kbd>Ctrl+F</kbd>. The Find tool appears at the bottom of the Lister in the [utility panel](../the_lister/utility_panel.md).

### Selecting the find mode

The **Advanced mode** checkbox at the top of the find panel lets you switch between *simple* and *advanced* modes. You can also press <kbd>Alt+A</kbd>.

The left half of the find panel changes depending on the selected mode. See the pages on the [simple](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md) and [advanced](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md) modes for information specific to the two modes.

### Saving and loading presets

The **Presets** dropdown at the top of the panel lets you save and load *find presets*. This lets you set up a find operation once and save it to use again later on.

The **Reset** button to the right of the dropdown gives you a quick way to reset the find panel to its default settings.

### Specifying the search location

The **Find in** control at the top-right of the find panel lets you specify the location or locations to search. You can search one or more folders (or entire drives) at once by adding entries to the location list. The dropdown on the **Find in** button gives you a history of previously searched locations.

Each entry in the list corresponds with a folder to search. To add a folder to the list, click the `+` button, or drag and drop a folder onto the list. You can edit an existing folder in the list by clicking it.

By default the search location will be *linked* to the file display, so when you navigate to a new location in the Lister, the find panel will update automatically with the new folder. You can disconnect the link by clicking the ![](/Manual/images/media/13/pathlink-linked.png) link button.

### Common search options

As well as the search location, the other options on the right half of the Find panel are common to both *simple* and *advanced* modes.

- **Search subfolders**: The function will search the contents of all sub-folders of the specified locations as well as the locations themselves.
- **Search archives**: The function will also search the contents of any archive files that are found in the specified locations.
- **Suppress UAC prompts**: If folders are encountered that you don't have permission to enter, Opus will silently skip them rather than showing a UAC elevation dialog.

### Excluding locations from the search

The **Exclude** field lets you specify folders that are excluded from the find operation.

![](/Manual/images/media/13/sync_exclude.png)

This field lets you enter one or more paths, or filenames, or wildcard patterns. Any folders that match will be excluded from the operation. In the screenshot above, any folders called **.svn** and **.github** would be excluded from the search.

The two options in the drop-down let you automatically exclude hidden folders and system folders from the operation.

### Speeding up the search using an index

The **Indexed search** control lets you take advantage of an indexed search engine like Windows Search or [Everything by voidtools](https://voidtools.com) to speed up the search. You can enter a query string in this field which will be passed to the specified search engine first. The Opus find operation will then use the results of that query as the space for its own search operation.

For example, you might want to find all JPGs on your computer of a certain size. You could use the indexed search to run a query looking for files called `*.jpg`, and then configure the advanced find mode to match images with the desired size. This would potentially be a lot quicker than solely using the Opus find tool to search for all JPGs on your system.

The search field used here is the same as used by the [Quick Search](windows_search.md) toolbar field - see that page for more information on configuring the indexed search.

### Search results are shown in a file collection

The **Show results in** controls let you specify the name of the [File Collection](../virtual_file_system/file_collections/README.md) that the results of the search will be displayed in, and which file display that collection will be loaded into. If the specified collection doesn't already exist it will be created automatically.

Normally the current file display will automatically navigate to show this collection when the search begins, but you can use the drop-down to specify that the collection should be shown in the destination (rather than the source) file display, and also opt to have it shown in a new [tab](../the_lister/tabs/README.md).

The **Clear previous results** option causes any existing contents of the file collection to be automatically cleared before the search begins. On the other hand, if the option is off then any files which you find will be added to the existing results collection, allowing you to accumulate the results of several otherwise unrelated find operations.

### Running the find

Once you've configured your find parameters, click the **Find** button at the bottom-right of the panel to start the find operation. The results collection will be loaded in the specified file display and as files are found by the Find tool they will appear in the collection.

### Refining a previous search

The **Refine** button becomes available after using the find tool once and lets you narrow down the results of a previous find by modiying the find parameters and then restarting the find operation, with the search space limited to the results of the previous search.

As an example of what **Refine** does, consider a folder that contains these files:

    Directory Listing.txt 
    Directory Opus.txt 
    Magnum Opus.txt

Searching for files with "Directory" in their names will give these two results:

    Directory Listing.txt 
    Directory Opus.txt

If you change the query to search for names containing "Opus" and click **Refine**, then you'll get just the file which matches both your original request ("Directory") and your new one ("Opus"):

    Directory Opus.txt

(Of course, you could have specified "Directory Opus" in the first place but there are times when you are not sure exactly what to look for or how many results you'll get back.)

On the other hand, if you changed the query to "Opus" and clicked the regular **Find** button instead of **Refine**, you'll get everything containing "Opus", regardless of what was done before:

    Directory Opus.txt 
    Magnum Opus.txt

More:  
[Simple Find](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md)  
[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)  
