# Quick Search

The search field on the Menu toolbar lets you quick run a search on the current folder. Multiple search engines are supported:

- **Windows Search**: The built-in search indexer in Windows.
- **Everything**: If you have [Everything by voidtools](https://voidtools.com) installed, you can run both local and global indexed searches using this tool.
- **Opus search**: Uses the Opus internal find tool. This is a non-indexed search.

### Indexed vs non-indexed

Both Windows Search and Everything are indexed searches - they use a pre-calculated index. The advantage of this is that results are normally returned almost immediately.

Not all locations are necessarily indexed, however, and in these cases Windows Search will be similar in speed to the Opus find tool. Note that Everything doesn't currently support searching non-indexed locations.

### Using the quick search field

![](/Manual/images/media/13/search_field.png) 

To search the current folder, click in the search field (or press <kbd>F3</kbd>) and enter your search term. By default all search engines perform a partial search so you can normally just enter one or two keywords (or parts of words) to find the files you're looking for.

### Choosing the search engine

![](/Manual/images/media/13/quicksearch_options.png)

To select a different search engine, click the button on the left of the search field to dropdown the menu.

Select the search engine you want to use from the top part of the menu. Each search engine has its own set of options, and these are shown in the bottom half of the menu.

### Windows Search

By default the Windows Search system will return files that match your keywords both in contents and in filename. If you want greater control over the search results, you can enter a more complex query string using [Advanced Query Syntax](http://msdn.microsoft.com/en-us/library/aa965711%28v=vs.85%29.aspx).

The options for Windows Search are:

- **Natural query syntax**: Allows natural query syntax (NQS) as well as advanced query syntax (AQS). NQS is a query syntax that is more relaxed than AQS, and is similar to human language.
- **Automatic wildcards**: Query expressions are treated as if each word in the query had the wildcard character \* appended to it (unless followed by punctuation other than a parenthesis).

### Everything

Two different types of Everything search are available:

- **Everything search**: A local search beneath the current folder.
- **Global Everything search**: Searches all indexed locations on your computer - the current folder isn't relevant.

The options for Everything are:

- **Case sensitive**: The case (upper/lowercase) of the supplied string must match exactly - if this is turned off, then upper and lower case letters are considered the same.
- **Whole words**: The text you enter must match a whole word, rather than being able to match part of a word.
- **Use regular expression**: Use regular expressions rather than Everything's own wildcard syntax (note: not the same as Opus standard pattern matching - only `*` and `?` characters are supported).
- **Ignore diacritics**: Ignores accent characters when matching text.

You can use Everything's [query syntax](https://www.voidtools.com/support/everything/searching/) for greater control over the search results.

### Opus search

The *Opus search* option uses the [Opus find tool](find_files/README.md) to run a search below the current folder. This is a non-indexed search and so may be significantly slower than the indexed search options (depending on how big the folder is).

The options for Opus search are:

- **Search filenames**: Searches the names of files.
- **Search content**: Searches inside files (supported file formats only).
- **Use wildcards**: Use [standard pattern matching syntax](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).
- **Use regular expression**: Use [regular expression](/Manual/reference/wildcard_reference/regular_expression_syntax.md).
- **Match any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Case sensitive**: The case (upper/lowercase) of the supplied string must match exactly - if this is turned off, then upper and lower case letters are considered the same.
- **Ignore diacritics**: Ignores accent characters when matching text.
- **Partial match**: The string you enter can match part of the filename, and does not have to match the whole filename.
- **Assume UTF-8 with no BOM**: Tells Opus to assume that plain text without a Byte Order Mark (BOM) are encoded in UTF8 rather than your computer's default 8-bit character set.

### Quick search results

![](/Manual/images/media/13/windows_search.png) 

In the above screenshot we've searched the **Documents** library for any documents with the name ***davidson*** in the author field. Matching files are displayed in a [file collection](../virtual_file_system/file_collections/README.md). This file collection is special in that it doesn't appear below the **File Collections** root folder like normal collections - instead, it appears as a child of the folder you searched in. The collection is also temporary - navigating away from the search results will cause it to be discarded.

To clear the search results and return to the folder you searched in, you can click the **Back** toolbar button, or use the close button in the search field to clear the search term.

### Saving the search results

If you want to save the results of an indexed search permanently, right-click on the background of the file display (not on a file) or on the status bar, and select the **Save as Stored Query** command from the context menu to save the search as a [stored query file collection](../virtual_file_system/file_collections/stored_queries.md).

### Quick search from the FAYT field

You can also run a quick search from the [find-as-you-type](../the_lister/find-as-you-type_field.md) field, by pressing the activation key for the search engine you want to use.
