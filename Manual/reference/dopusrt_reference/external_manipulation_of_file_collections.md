# External Manipulation of File Collections

The **[DOpusRT]()** tool can be used from outside of Opus to manipulate [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md).

This functionality is accessed using the **dopusrt.exe /col** command - following **/col** you must supply a *collection command*, and the appropriate arguments for that collection command.

As with most command-line tools, if a path or other argument contains spaces, you must "put quotes around it".

\<commandtable columns="3" id="cmdtable_1"\> \$\$ Command \$\$ Arguments \$\$ Description \$\$ **add** \$\$ *\[\<flags\>\] \<coll-name\> \<item\> \[\<item\> ...\]* \$\$ **Add one or more items to the named collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these. If a flag's value contains a space, the entire flag and value must be enclosed in quotes.  
*\<coll-name\>* is the name of the collection (if adding to a sub-collection, the full path must be provided).  
*\<item\>* is the full path and filename of the item or items to add. If the path or filename contains spaces, it must be enclosed with quotes. The filename can also contain [standard wildcards](../wildcard_reference/pattern_matching_syntax.md) to add multiple items in a folder at once.

Example:  
**dopusrt.exe /col add "Photos/Holidays" /mypictures/Hawaii/\*.jpg**  
\$\$ \$\$ \[**/dupeid***=\<id\>*\] \$\$ Lets you use "duplicate files" style collections by providing a numeric ID to assign items to groups. Items added with the same duplicate ID will be displayed together when the file display is grouped by duplicates. \$\$ \$\$ \[**/name**\] \$\$ Lets you assign your own name to a duplicate group. This must be used in conjunction with the **/dupeid** flag. For example,  
**dopusrt.exe /col add /dupeid=1 /name "My Dupes" "Group number 1"** \$\$ **clear** \$\$ \[**/full**\] *\<coll-name\>* \$\$ **Clears the contents of the named collection**.  
*\<coll-name\>* is the name of the collection (if clearing a sub-collection, the full path must be provided). By default, sub-collections are not removed when the collection is cleared, but you can specify the **/full** flag to do this.

Example:  
**dopusrt.exe /col clear "Find Results"  
dopusrt.exe /col clear /full "Marked Pictures"**  
\$\$ **create**

\$\$ *\[\<flags\>\] \<coll-name\>* \$\$ **Create a new collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these. If a flag's value contains a space, the entire flag and value must be enclosed in quotes.  
*\<coll-name\>* is the name of the collection to create. To create a sub-collection, specify the full path of the collection. The collection name must come after any of the optional flags.

Example:  
**dopusrt.exe /col create "/desc:My Photos" Photos**  
\$\$ \$\$ **/noclear** \$\$ Does not clear the collection if it already exists. \$\$ \$\$ **/icon:***\<file\>* \$\$ Specifies a custom icon for the new collection. \$\$ \$\$ **/desc:***\<desc\>* \$\$ Specifies a description for the new collection. \$\$ \$\$ /dupes \$\$ Marks the collection as a "duplicate files" collection. \$\$ \$\$ **/query** \$\$ Creates the new collection as a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md).  
\$\$ **delete** \$\$ *\<coll-name\>* \$\$ **Delete the named collection**.  
*\<coll-name\>* is the name of the collection to delete. If deleting a sub-collection, the full path must be provided.

Example:  
**dopusrt.exe /col delete "Photos/Holidays/2010"**  
\$\$ **export**

\$\$ *\[\<flags\>\] \<coll-name\> \<export-file\>* \$\$ **Export the contents of a collection to a text file**.  
*\<flags\>* are one or more optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the collection to export.  
*\<export-file\>* is the full path and file to export to - this must be quoted if it contains spaces.

If the encoding type is not specified (using the optional flags), the file will be encoded as UTF16-LE if any filenames require Unicode, and otherwise in the current ANSI code-page.

Example:  
**dopusrt.exe /col export /utf8 "Find Results" D:\Results.txt**  
\$\$ \$\$ **/append** \$\$ If the export file already exists, append to it - otherwise it will be overwritten. \$\$ \$\$ **/utf16be** \$\$ Force encoding to UTF16-BE. \$\$ \$\$ **/utf16le** \$\$ Force encoding to UTF16-LE. \$\$ \$\$ **/utf8** \$\$ Force encoding to UTF8. \$\$ \$\$ **/ansi** \$\$ Force encoding to the current ANSI code-page. \$\$ \$\$ **/cp:***\<codepage\>* \$\$ Specify the code-page.  
\$\$ **import**  
  
  
\$\$ *\[\<flags\>\] \<coll-name\> \<import-file\>* \$\$ **Import the contents of a text file to a collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the collection to import to.  
*\<import-file\>* is the file to import from.  
The import file should contain one file or folder name per line.  
  
You can import "duplicate files" style collections by prefixing each line in the import file with **\#***\<id\>*\*\*, \*\*to specify the numeric duplicate ID. Items with the same duplicate ID will be grouped together when the file display is set to group by duplicates.  
  
You can also assign names to the duplicate groups by including lines in the format **group:***\<id\>***,***\<name\>***.**  
  
If the import file has a BOM this will be used to determine the encoding type.  
  
Example:  
**dopusrt.exe /col import /ansi "My Photos" /desktop/photos.txt**  
\$\$ \$\$ **/clear** \$\$ Clear the collection before importing the new items. \$\$ \$\$ **/create** \$\$ Create the collection if it doesn't already exist. \$\$ \$\$ **/nocheck** \$\$ Don't check that the items listed in the import file exist before importing them into the collection. \$\$ \$\$ **/relative:*\<path\>*** \$\$ Specify the path which lines in the list are relative to, if the file does not contain fully qualified paths. If not specified, paths are assumed to be relative to the same folder the list is in.  
Specify **/relative:none** if doing something special where you want the lines imported as-is even if they aren't fully qualified, in which case this cannot be combined with **/nocheck**.  
If the path contains spaces, the entire argument should be quoted.  
  
Example:  
**dopusrt.exe /col import "/relative:C:\My Music" "Jazz" C:\Trane.m3u** \$\$ \$\$ **/utf16be** \$\$ Assume UTF16-BE if no BOM. \$\$ \$\$ **/utf16le** \$\$ Assume UTF16-LE if no BOM. \$\$ \$\$ **/utf8** \$\$ Assume UTF8 if no BOM. \$\$ \$\$ **/ansi** \$\$ Force conversion from the current ANSI code-page. \$\$ \$\$ **/cp:***\<codepage\>* \$\$ Force conversion from a specific code-page.  
\$\$ **remove** \$\$ *\<coll-name\> \<item\> \[\<item\> ...\]* \$\$ **Remove items from a collection**.  
*\<coll-name\>* is the name of the collection.  
*\<item\>* is the name of the item or items to remove. This can be given as either the item's full path on disk, or its name within the collection. If the path or filename contains spaces, it must be enclosed with quotes. The filename can also contain [standard wildcards](../wildcard_reference/pattern_matching_syntax.md) to remove multiple items at once.  
  
Example:  
**dopusrt.exe /col remove "Find Results" \*.txt**  
\$\$ **rename** \$\$ *\<old-coll-name\> \<new-coll-name\>* \$\$ **Rename a collection**.  
*\<old-coll-name\>* is the existing name of the collection.  
*\<new-coll-name\>* is the new name for the collection.  
  
Example:  
**dopusrt.exe /col rename "Find Results" "Saved Results 1"**  
\$\$ **runquery** \$\$ *\<coll-name\>* \$\$ **Run (refresh) a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
*\<coll-name\>* is the name of the stored query collection.  
  
Example:  
**dopusrt.exe /col runquery "Stored Queries\Backup Files"**  
\$\$ **setdesc** \$\$ *\<coll-name\> \<desc\>* \$\$ **Set the description for a collection**.  
**\<coll-name\>** is the name of the collection.  
**\<desc\>** is the new description for the collection (or nothing to clear the description).  
  
Example:  
**dopusrt.exe /col setdesc "Saved Results 1" "Music before 1990"**  
\$\$ **seticon** \$\$ *\<coll-name\> \<icon-file\>* \$\$ **Set a custom icon for a collection**.  
*\<coll-name\>* is the name of the collection.  
*\<icon-file\>* is the full path and filename of the icon file to use.  
  
The icon can come from a .ico or .icl file, or a .exe or .dll file. For files that contain more than one icon, append the desired icon index following the filename.  
  
Example:  
**dopusrt.exe /col seticon "Pics" C:\Tools\viewer.exe,2**  
\$\$ **setpaths**  
\$\$ *\[\<flags\>\] \<coll-name\> \<path\> \[\<path\> ...\]* \$\$ **Set the search path or paths for a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
*\<flags\>* are optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the stored query collection.  
*\<path\>* is the path or paths to add to the query. If a path contains spaces it must be enclosed in quotes.  
  
Example:  
**dopusrt.exe /col setpaths "Backup Files" X:\Backup**  
\$\$ \$\$ **/add** \$\$ Add the paths to the query, don't remove any existing ones.  
\$\$ **setquery**  
  
\$\$ *\[\<flags\>\] \<coll-name\> \<query\>* \$\$ **Set the query string for a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
\<flags\> are one or more optional flags, see below for a list of these.  
\<coll-name\> is the name of the stored query collection.  
\<query\> is the query string, in [Advanced Query Syntax](http://www.microsoft.com/windows/products/winfamily/desktopsearch/technicalresources/advquery.mspx).  
  
The named collection must have been created as a stored query (e.g. with the **dopusrt.exe /col create /query** command).

In conjunction with this, you can use the **/engine** argument to set the search engine used by the query. The default is Windows search; other options are **everything**, **everythingglobal** and **opus**.

Example:  
**dopusrt.exe /col setquery "Backup Files" name:\*.bak /engine=everything**  
\$\$ \$\$ **/auto** \$\$ Set the stored query to "auto refresh" mode - the query will be run/refreshed whenever it is loaded. \$\$ \$\$ **/noauto** \$\$ Set the stored query to not automatically refresh.  
\</commandtable\>
