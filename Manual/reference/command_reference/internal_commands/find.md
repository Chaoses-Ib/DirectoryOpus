# Find

The **Find** internal command can be used to:

- Display the [Find Panel](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) where you can perform file searches
- Automate the Find Files function to perform simple searches without displaying a user interface
- Automate the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md) function

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Display the Find Panel. It will open in whichever mode you last used it.

*Example:* `Find`
</td></tr><tr><td>
ADVANCED</td><td>
/S</td><td>

*(no value)*</td><td>

Display the Find Panel in [Advanced](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md) mode.

*Example:* `Find ADVANCED`
</td></tr><tr><td>
ANYWORD</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to enable the *Any Word* option for name searching.  
For example, if this was turned on and you used "cat dog" as the **NAME** argument, Opus would match filenames containing "cat" or "dog" (or both, in any order). This saves you having to construct complicated OR wildcard patterns.

*Example:* `Find NAME="cat dog" ANYWORD RECURSE IN "c:\\`
</td></tr><tr><td>
ARCHIVES</td><td>
/S</td><td>

*(no value)*</td><td>

Search inside archive files (when the Find Files function is being automated).

*Example:* `Find *.doc IN C:\Data ARCHIVES`
</td></tr><tr><td>
BOTHWAYS</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you turn on the **Copy files in both directions** option.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
CASE</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **NAME** argument should be treated as case-sensitive, similar to the related checkbox in the UI.

*Example:* `Find *.DOC IN C:\ RECURSE CASE`
</td></tr><tr><td>
CLEAR</td><td>
/O</td><td>

*(no value)*</td><td>

Clear previous results (when the Find Files function is being automated). The output file collection will be cleared before the new Find begins.

*Example:* `Find *.doc IN C:\Data CLEAR`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not clear previous results.

*Example:* `Find *.doc in C:\Data CLEAR=no`
</td></tr><tr><td>
COLLNAME</td><td>
/K</td><td>

*\<collection name\>*</td><td>

Specify the name of the file collection that results are added to. If not supplied the default collections (*Find Results* and *Duplicate Files*) are used.

*Example:* `Find *.doc in C:\Data COLLNAME Output`
</td></tr><tr><td>
COLUMN</td><td>
/K</td><td>

*\<column name\>*</td><td>

When automating the duplicate finder tool with the `DUPES` argument, specifies that duplicates should be matched using the value of a specific column.

*Example:* `Find IN C:\Data DUPES COLUMN=createddate`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

Match duplicates by name as well as the value of the specified column

*Example:* `Find IN C:\Data DUPES COLUMN=createddate,name`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

Match duplicates by size as well as the value of the specified column

*Example:* `Find IN C:\Data DUPES COLUMN=createddate,name,size`
</td></tr><tr><td>
COMPARE</td><td>
/K</td><td>

**size**</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to compare files by size. By default it will look for different sizes; you can also specify **size,smaller** or **size,larger**.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to compare files by date. By default it will look for different dates; you can also specify **newer**. This can also be combined with **size**.
</td></tr><tr><td>
</td><td>
</td><td>

**compare**</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to compare files by comparing the file data (hash).
</td></tr><tr><td>
COMPUTERS</td><td>
/S</td><td>

*(no value)*</td><td>

Launch the Windows *Search for Computers* function (depending on your version of Windows, this may have no effect).

*Example:* `Find COMPUTERS`
</td></tr><tr><td>
CONTAINING</td><td>
/K</td><td>

*\<search text\>*</td><td>

Specify text to search for (when the Find Files function is being automated).

*Example:* `Find *.txt CONTAINING printf IN C:\SourceCode`
</td></tr><tr><td>
CONTANYWORD</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **CONTAINING** argument should be handled in "any word" mode, similar to the related checkbox in the UI.

*Example:* `Find *.txt CONTAINING "apple pear peach plum" CONTANYWORD IN C:\Inventory`
</td></tr><tr><td>
CONTCASE</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **CONTAINING** argument should be treated as case-sensitive, similar to the related checkbox in the UI.

*Example:* `Find *.txt CONTAINING Apple CONTCASE IN C:\Inventory`
</td></tr><tr><td>
CONTIGNOREDIACRITICS</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **CONTAINING** argument should ignore diacritics (accent marks), similar to the related checkbox in the UI.

*Example:* `Find *.txt CONTAINING "aeiou" CONTIGNOREDIACRITICS IN C:\Documents`
</td></tr><tr><td>
CONTNOPARTIAL</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to prevent partial word matching for the **CONTAINING** argument (contents must then match the pattern you specify exactly).

*Example:* `Find "moo\*cow" IN "c:\ RECURSE CONTNOPARTIAL`
</td></tr><tr><td>
CONTWILD</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **CONTAINING** argument should be treated as a wildcard, similar to the related checkbox in the UI.

*Example:* `Find *.txt CONTAINING (foo|bar) CONTWILD IN C:\Things`
</td></tr><tr><td>
CONTREGEXP</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating the Find Files function to specify that the **CONTAINING** argument should use [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md), similar to the related checkbox in the UI.

*Example:* `Find *.txt CONTAINING "Mr(s?) Bond" CONTREGEXP IN C:\ RECURSE`
</td></tr><tr><td>
CONTUTF8</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Find Files function, plain text files will be assumed to be UTF-8 if no BOM is detected (similar to the related checkbox in the UI).

*Example:* `Find *.txt CONTAINING printf IN C:\SourceCode CONTUTF8`
</td></tr><tr><td>
DELETE</td><td>
/O</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you turn on the **Delete destination files that aren't in the source** option.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

Also turns on the **Delete before copy** option.
</td></tr><tr><td>
DSTCOMPENSATION</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to ignore one hour time differences (daylight savings time) when comparing timestamps.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
DUPES</td><td>
/S</td><td>

*(no value)*</td><td>

Automates the Duplicate File Finder.

*Example:* `Find IN C:\Data DUPES`
</td></tr><tr><td>
EXCLUDEHIDDEN</td><td>
/O</td><td>

*(no value)*</td><td>

Excludes hidden folders (those with the **H** attribute set) from the search.

*Example:* `Find *.txt IN D:\ EXCLUDEHIDDEN`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not exclude hidden folders. Use this to override a saved preset.

*Example:* `Find PRESET=DocFiles EXCLUDEHIDDEN=no IN \\storage\data`
</td></tr><tr><td>
EXCLUDESYSTEM</td><td>
/O</td><td>

*(no value)*</td><td>

Excludes system folders (those with the **H** and **S** attributes set) from the search.

*Example:* `Find *.exe IN C:\ EXCLUDESYSTEM`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not exclude system folders. Use this to override a saved preset.

*Example:* `Find *.exe IN C:\ EXCLUDESYSTEM=no`
</td></tr><tr><td>
FILTER</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates that the value of the **NAME** argument is the name of a [pre-defined filter](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md). This lets you automate more complex searches than just those based on filename and containing text.

*Example:* `Find NAME image_files IN C:\Pictures FILTER`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md). Similar to the **FILTER** argument, you can automate more complex searches than just those based on filename and containing text - however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `Find FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FROM</td><td>
/K</td><td>

*\<path\>*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you specify the folder that is the source of the synchronize operation.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Find tool, performs the search below the current folder.

*Example:* `Find NAME *.txt HERE`
</td></tr><tr><td>
HIDEUNAFFECTED</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to hide unaffected files once the comparison process has run.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
IGNOREDIACRITICS</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to specify that the **NAME** argument should ignore diacritics (accent marks), similar to the related checkbox in the UI.

*Example:* `Find (\[aeiou\]+)\\txt IGNOREDIACRITICS REGEXP IN C:\Documents`
</td></tr><tr><td>
IGNORELINKS</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md), this lets you turn on the **Ignore hard links** option.

*Example:* `Find IN C:\Data DUPES IGNORELINKS`
</td></tr><tr><td>
IGNORESECONDS</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to ignore seconds when comparing timestamps.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
IN</td><td>
/K/M</td><td>

*\<search location\> ...*</td><td>

Specify the folder or folders to search in when automating a search. Remember that if the paths contain a space you must enclose the value in quotes.

*Example:* `Find *.txt IN "C:\Folder 1" "C:\Folder 2"`
</td></tr><tr><td>
LOADPREV</td><td>
/K</td><td>

**no**</td><td>

Disable the loading of previous find settings when the Find panel opens. By default, the Find panel will remember its previous settings when it opens unless it has been invoked via an automated search (i.e with both **IN** and **NAME** arguments specified). Use this argument to prevent the command ever remembering its previous settings.

*Example:* `Find LOADPREV=no`
</td></tr><tr><td>
</td><td>
</td><td>

**yes**</td><td>

Force the Find panel to load its previous settings even when opened by an automated search. This does not restore multiple search paths, however - **LOADPREV=all** must be specified for that.

*Example:* `Find *.txt IN "C:\Folder 1" LOADPREV=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Forces the Find panel to remember its previous settings, and also restores all paths that were previously listed in the search list.

*Example:* `Find LOADPREV=all`
</td></tr><tr><td>
MD5</td><td>
/O</td><td>

*(no value)*</td><td>

Search for duplicates using the MD5 checksum (used with the **DUPES** argument). The default behaviour is to search based on filename and size.

*Example:* `Find IN C:\Data DUPES MD5`
</td></tr><tr><td>
</td><td>
</td><td>

*\<percentage\>*</td><td>

Only calculate checksums based on a percentage of the file's contents. This can dramatically speed up duplicate checking for large files, at the expense of some accuracy.

*Example:* `Find IN C:\Data DUPES MD5=75`
</td></tr><tr><td>
</td><td>
</td><td>

**cache**</td><td>

Use the checksum cache for large files. If a file's checksum has previously been cached and the file does not appear to have changed, the cached value will be used instead of recalculating its checksum.

*Example:* `Find IN C:\Downloads DUPES MD5=cache,50`
</td></tr><tr><td>
MINSIZE</td><td>
/K/N</td><td>

*\<size\>*</td><td>

When automating the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md), this lets you set the value of the **Minimum size** field. The value is given in kilobytes.

*Example:* `Find IN C:\Data DUPES MD5 MINSIZE=500`
</td></tr><tr><td>
NAME</td><td>
</td><td>

*\<filename\>*</td><td>

This is the default argument for the **Find** command, which means you do not need to use the **NAME** keyword before it (unless you are searching for a word which is recognized as another argument keyword).

Specify the filename or wildcard pattern to search for. To automate the Find Files function you must specify both the **NAME** argument, and the location to search using the **IN** argument.

The **NOWILD**, **ANYWORD** and **NOPARTIAL** arguments can be used to control whether or not wildcards, "any word" or partial matching are used when searching names, similar to the checkboxes in the UI.

You can start the wildcard pattern with **regex:** to use [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md) instead of wildcards. (Do not specify the **NOWILD** argument in this case.)

You can also search using a pre-defined filter by providing the filter name for the **NAME** argument and also specifying the **FILTER** switch.

*Example:* `Find *.(doc|txt|bmp) IN C:\ RECURSE ARCHIVES`  
*Example:* `Find regex:foo.+bar\\txt IN C:\ RECURSE`  
*Example:* `Find NAME="Text File (1).txt" NOWILD IN C:\ RECURSE`

When used with the **DUPES** argument, this lets you provide a filename filter for the duplicates search. When used like this, you can specify a regular expression pattern by prefixing the wildcard with the **regex:** prefix.

*Example:* `Find *.pdf IN C:\Documents RECURSE CLEAR MD5 DUPES`
</td></tr><tr><td>
NAMEONLY</td><td>
/O</td><td>

*(no value)*</td><td>

Search for duplicates based on filename only (used with the **DUPES** argument). The default behaviour is to search based on filename and size.

*Example:* `Find IN C:\Data DUPES NAMEONLY`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

Search for duplicates based on filename only, ignoring their file extensions.

*Example:* `Find IN C:\Data DUPES NAMEONLY=noext`
</td></tr><tr><td>
NOAUTORUN</td><td>
/S</td><td>

*(no value)*</td><td>

Lets you prevent an automated search from taking place - instead, the Find, Duplicates or Synchronize panel will open with the controls initialised but allow you to make further changes before starting the search. For example, when both the **NAME** and **IN** arguments are provided, the Find Files operation normally begins automatically. To prevent this, specify the **NOAUTORUN** argument as well.

*Example:* `Find *.doc IN /mydocuments RECURSE NOAUTORUN`
</td></tr><tr><td>
NOPARTIAL</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to prevent partial name matching (names must then match the pattern you specify exactly).

*Example:* `Find *.bak IN "c:\ RECURSE NOPARTIAL`
</td></tr><tr><td>
NOWILD</td><td>
/S</td><td>

*(no value)*</td><td>

Use when automating Find Files to prevent wildcard name matching. Like the similar checkbox in the UI.

*Example:* `Find "File (1).txt" IN "c:\ RECURSE NOWILD`
</td></tr><tr><td>
NUMBERGROUPS</td><td>
/S</td><td>

*(no value)*</td><td>

The **Duplicate Finder** creates groups for each set of duplicate files found, and normally these groups are named after the criteria used for the duplicate search. If you turn this option on then each group of duplicates will be numbered (from 1 to *X*, in the order they are found).

*Example:* `Find IN C:\Data DUPES MD5 NUMBERGROUPS`
</td></tr><tr><td>
OF</td><td>
/K/M</td><td>

*\<file to match\> ...*</td><td>

Specifies one or more files to search for duplicates of. If you don't use this argument, all duplicate files in the specified locations will be found. Remember that if the file path you are providing contains spaces, you must enclose the value in quotes.

*Example:* `Find DUPES OF C:\Report.txt IN C:\Backups MD5`
</td></tr><tr><td>
OFFLINE</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md), this lets you turn off the **Ignore offline files** option (the default for this option is on).

*Example:* `Find IN E:\TapeBackup DUPES OFFLINE`
</td></tr><tr><td>
ONLYEXISTING</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you select to only synchronize existing files.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<preset name\>*</td><td>

Loads the specified Find, Synchronize or Duplicates preset. Other arguments you provide will override the preset settings - for example, you can use the **IN** argument to override the search path. Specify the **NOAUTORUN** argument to prevent the operation from starting automatically.

*Example:* `Find PRESET=ImageFiles IN=D:\Downloads`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

Generates a list of saved presets (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting an item from the list will open the appropriate panel and run the specified preset.

*Example:* `Find PRESET=!list DUPES`
</td></tr><tr><td>
</td><td>
</td><td>

**faves**</td><td>

Modifies the generated list of presets to only display those you have marked as favorites.

*Example:* `Find PRESET=!list,faves`
</td></tr><tr><td>
</td><td>
</td><td>

**nofaves**</td><td>

Modifies the generated list of presets to exclude those you have marked as favorites.

*Example:* `Find SYNC PRESET=!list,nofaves`
</td></tr><tr><td>
</td><td>
</td><td>

**nogroups**</td><td>

Displays the generated list of presets as a flat list rather than separating them up into any groups you may have created.

*Example:* `Find PRESET=!list,nofaves,nogroups`
</td></tr><tr><td>
QUERY</td><td>
/K/R</td><td>

*\<query string\>*</td><td>

Performs a search in the specified location using the [Windows Search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) system.

If used on its own, without other arguments, it is like typing a query string into the search field at the top-right of the lister to search below the current folder. You can also run a Windows Search query on a specified folder or into a custom results collection.

Everything which follows the **QUERY** argument will be passed to Windows Search as the query string, so it *must* be the last argument to the command.

*Example:* `Find QUERY filename:*.doc author:"Leo Davidson"`  
*Example:* `Find IN "C:\Documents" COLLNAME "Leo's Docs" QUERY filename:*.doc author:"Leo Davidson"`
</td></tr><tr><td>
RECURSE</td><td>
/O</td><td>

*(no value)*</td><td>

When automating the Find Files, Duplicate File Finder or Synchronize Files functions, the search will extend into sub-folders below the specified locations.

*Example:* `Find IN C:\Data DUPES RECURSE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Prevent the search from extending into sub-folders.

*Example:* `Find IN C:\Data DUPES RECURSE=no`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(no value)*</td><td>

When automating the Find Files function, enables [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md) for the value of the **NAME** field.

*Example:* `Find "foo.+bar\\txt" IN C:\ RECURSE REGEXP`
</td></tr><tr><td>
RUNINPANEL</td><td>
/S</td><td>

*(no value)*</td><td>

Normal automation of the **Find** command causes it to run in the background, without a visible user interface. The **RUNINPANEL** argument lets you open the Duplicate Finder or Synchronize panel, initialise it with other arguments (including loading a preset), and then automatically start the operation in the user interface, exactly the same as clicking the "go" button manually.

Contrast this with **NOAUTORUN** which will open the panel but not start the operation.

*Example:* `Find IN C:\Data DUPES RUNINPANEL`
</td></tr><tr><td>
SAVEQUERY</td><td>
/S</td><td>

*(no value)*</td><td>

When you are currently viewing the results of a [Windows Search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) query, this command will save the search as a [stored query collection](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md).

*Example:* `Find SAVEQUERY`
</td></tr><tr><td>
SHOWRESULTS</td><td>
/K</td><td>

**source**</td><td>

Display the results of the automated search in the current source file display or Lister.

*Example:* `Find *.txt IN C:\ RECURSE SHOWRESULTS=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Display the results in the destination file display.

*Example:* `Find *.jpg IN C:\Data SHOWRESULTS=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**tab**</td><td>

Display the results in a new tab. You can combine this with the **source** or **dest** arguments.

*Example:* `Find IN C:\Data DUPES RECURSE SHOWRESULTS dest,tab`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*(no value)*</td><td>

Display the Find Panel in [simple mode](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.md).

*Example:* `Find SIMPLE`
</td></tr><tr><td>
SIZEONLY</td><td>
/S</td><td>

*(no value)*</td><td>

Search for duplicates based on file size only (used with the **DUPES** argument). The default behaviour is to search based on filename and size.

*Example:* `Find IN C:\Data DUPES SIZEONLY`
</td></tr><tr><td>
SYNC</td><td>
/O</td><td>

*(no value)*</td><td>

In conjunction with other arguments, this lets you automate the [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool. The other relevant arguments are **FROM**, **TO**, **BOTHWAYS**, **DELETE**, **COMPARE**, **IGNORESECONDS**, **DSTCOMPENSATION**, **HIDEUNAFFECTED**, **ONLYEXISTING**.

This process requires the use of multiple commands. `Find SYNC` performs the initial step in the synchronize process - the comparison. You then need to use `Copy SYNC` to perform any copying required. Finally, `Set CLEARSYNC` can be used to exit synchronize mode once finished.

//<Example://>

    Find SYNC FROM "D:\Work" TO "D:\Backups" RECURSE COMPARE=newer HIDEUNAFFECTED
    Copy SYNC
    Set CLEARSYNC
</td></tr><tr><td>
</td><td>
</td><td>

**ltr**</td><td>
Performs the synchronize from left-to-right rather than source-to-destination.
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<path\>*</td><td>

When automating the Synchronize tool with the **SYNC** argument, this lets you specify the folder that is the destination of the synchronize operation.

//<Example://> See the **SYNC** argument for an example.
</td></tr><tr><td>
UAC</td><td>
/O</td><td>

*(no value)*</td><td>

Enables UAC prompts if elevation may be required to search inside folders.

\`\`Find *.txt UAC IN D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Suppresses UAC prompts, skipping folders you don't have access to. (This is the default, so it doesn't normally need specifying. Can be useful if you want to override a preset which enables UAC prompts.)

\`\`Find PRESET=DocFiles UAC=no IN D:\\\`
</td></tr></tbody>
</table>

