# Windows Search

The search field on the Menu toolbar lets you access the [Windows Search](http://windows.microsoft.com/en-GB/windows7/products/features/windows-search) system from within Opus. This provides an indexed search - the advantage of which is that results are normally returned almost immediately. Not all locations are necessarily indexed, however, and in these cases the search speed will be similar to that provided by the Opus **[Find Files](find_files/RAEDME.md)** function.

![](/Manual/images/media/search_field.png) 

To search the current folder, click in the search field (or press **F3**) and enter your search term. You can also use the [find-as-you-type](../the_lister/find-as-you-type_field.md) field in search mode - by default this is activated by pressing the **=** key (equals sign). You can normally just enter one or two keywords to find the files you're looking for - the Windows Search system will return files that match your keywords both in contents and in filename. If you want greater control over the search results, you can enter a more complex query string using [Advanced Query Syntax](http://msdn.microsoft.com/en-us/library/aa965711%28v=vs.85%29.aspx).

![](/Manual/images/media/windows_search.png) 

In the above screenshot we have searched the **Documents** library for any documents with the name ***davidson*** in the author field. Matching files are displayed in a [file collection](../virtual_file_system/file_collections/RAEDME.md). This file collection is special in that it doesn't appear below the **File Collections** root folder like normal collections - instead, it appears as a child of the folder you searched in. The collection is also temporary - navigating away from the search results will cause it to be discarded.

To clear the search results and return to the folder you searched in, you can click the **Back** toolbar button, or use the ![](/Manual/images/media/filter_bar_-_close.png) button in the search field to clear the search term.

If you want to save the results of an indexed search permanently, right-click on the background of the file display (not on a file) or on the status bar, and select the **Save as Stored Query** command from the context menu to save the search as a [stored query file collection](../virtual_file_system/file_collections/stored_queries.md).

Windows Search is included in Vista and above - for Windows XP you must [download](http://www.gpsoft.com.au/DScripts/redirect.asp?page=windowssearch) it from Microsoft and install it to use this feature in Opus.
