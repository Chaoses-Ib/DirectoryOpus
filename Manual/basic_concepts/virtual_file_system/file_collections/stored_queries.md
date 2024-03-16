# Stored Queries

Stored Queries are special file collections that are used to create persistent searches with the [quick search](../../searching_and_filtering/windows_search.md) system. Each stored query remembers a search string and one or more folders to search within. Rather than a static collection of search results, when you navigate to the stored query, the quick search can be automatically run and up-to-date results shown instead.

##### Creating a stored query

You can create a stored query from the **File Collections** root folder - right-click on the folder itself, or from within the folder right-click on the file display background, and choose the **New Stored Query** command.

You can also create a stored query from an existing search - see the help on the [quick search](../../searching_and_filtering/windows_search.md) system for more details about this.

##### Stored query properties

Once you have created a stored query, right-click on it and choose the **Properties** command to display its Properties dialog, and change to the **Query** tab - this is where you can configure the search parameters.

- **Query**: This is where you enter the search string.
- **Search Engine**: Choose the search engine to run the query in. The options button to the right shows a menu specific to the selected engine.
- **Folders**: Select the folders to run the query in. If a global search engine is chosen, this will be disabled.
- **Refresh results automatically**: The query will be run and the results updated every time you navigate into the collection. You would generally only turn this option on for indexed locations, where the results will be returned almost immediately. If this option is off, the collection will preserve the last set of search results until you manually run the query by refreshing the folder (by clicking the refresh button or pressing the <kbd>F5</kbd> key, for example).
