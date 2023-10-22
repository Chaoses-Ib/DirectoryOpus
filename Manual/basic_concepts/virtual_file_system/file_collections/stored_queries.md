# Stored Queries

Stored Queries are special file collections that are used to create persistent searches with the [Windows Search](../../searching_and_filtering/windows_search.md) system. Each stored query remembers an [Advanced Query Syntax](http://msdn.microsoft.com/en-us/library/aa965711%28v=vs.85%29.aspx) search string and one or more folders to search within.

You can create a stored query from the **File Collections** root folder - right-click on the folder itself, or from within the folder right-click on the file display background, and choose the **New Stored Query** command. You can also create a stored query from an existing search - see the help on the [Windows Search](../../searching_and_filtering/windows_search.md) system for more details about this. Once you have created a stored query, right-click on it and choose the **Properties** command to display its Properties dialog - this is where you can configure the search parameters.

![](/Manual/images/media/stored_query_properties.png) 

The **Change Icon** button lets you select your own icon for the stored query collection, and the **Set Description** button lets you assign your own description string if desired. These function the same as for normal collections. Below these buttons are options that only apply to stored queries.

The **Query** field is where you enter the AQS query term that defines the search. Below that is a list of folders to search in. The query can search in a single folder (as in the screenshot above - only the **Documents** library is being searched), or it can search multiple folders at once.

If the **Refresh results automatically** option is turned on, the query will be run and the results updated every time you navigate into the collection. You would generally only turn this option on for indexed locations, where the results will be returned almost immediately. If this option is left turned off, the collection will preserve the last set of search results until you manually run the query by refreshing the folder (by pressing the **F5** key, for example).
