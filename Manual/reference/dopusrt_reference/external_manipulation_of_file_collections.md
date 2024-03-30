# External Manipulation of File Collections

The **[DOpusRT]()** tool can be used from outside of Opus to manipulate [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md).

This functionality is accessed using the **dopusrt.exe /col** command - following **/col** you must supply a *collection command*, and the appropriate arguments for that collection command.

As with most command-line tools, if a path or other argument contains spaces, you must "put quotes around it".

<table>
<thead><tr><th>
Command</th><th>
Arguments</th><th>
Description
</th></tr></thead><tbody><tr><td>

**add**</td><td>

*\[\<flags\>\] \<coll-name\> \<item\> \[\<item\> ...\]*</td><td>

**Add one or more items to the named collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these. If a flag's value contains a space, the entire flag and value must be enclosed in quotes.  
*\<coll-name\>* is the name of the collection (if adding to a sub-collection, the full path must be provided).  
*\<item\>* is the full path and filename of the item or items to add. If the path or filename contains spaces, it must be enclosed with quotes. The filename can also contain [standard wildcards](../wildcard_reference/pattern_matching_syntax.md) to add multiple items in a folder at once.

Example:  
**dopusrt.exe /col add "Photos/Holidays" /mypictures/Hawaii/\*.jpg**
</td></tr><tr><td>
</td><td>

\[**/dupeid***=\<id\>*\]</td><td>
Lets you use "duplicate files" style collections by providing a numeric ID to assign items to groups. Items added with the same duplicate ID will be displayed together when the file display is grouped by duplicates.
</td></tr><tr><td>
</td><td>

\[**/name**\]</td><td>

Lets you assign your own name to a duplicate group. This must be used in conjunction with the **/dupeid** flag. For example,  
**dopusrt.exe /col add /dupeid=1 /name "My Dupes" "Group number 1"**
</td></tr><tr><td>

**clear**</td><td>

\[**/full**\] *\<coll-name\>*</td><td>

**Clears the contents of the named collection**.  
*\<coll-name\>* is the name of the collection (if clearing a sub-collection, the full path must be provided). By default, sub-collections are not removed when the collection is cleared, but you can specify the **/full** flag to do this.

Example:  
**dopusrt.exe /col clear "Find Results"  
dopusrt.exe /col clear /full "Marked Pictures"**
</td></tr><tr><td>

**create**</td><td>

*\[\<flags\>\] \<coll-name\>*</td><td>

**Create a new collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these. If a flag's value contains a space, the entire flag and value must be enclosed in quotes.  
*\<coll-name\>* is the name of the collection to create. To create a sub-collection, specify the full path of the collection. The collection name must come after any of the optional flags.

Example:  
**dopusrt.exe /col create "/desc:My Photos" Photos**
</td></tr><tr><td>
</td><td>

**/noclear**</td><td>
Does not clear the collection if it already exists.
</td></tr><tr><td>
</td><td>

**/icon:***\<file\>*</td><td>
Specifies a custom icon for the new collection.
</td></tr><tr><td>
</td><td>

**/desc:***\<desc\>*</td><td>
Specifies a description for the new collection.
</td></tr><tr><td>
</td><td>
/dupes</td><td>
Marks the collection as a "duplicate files" collection.
</td></tr><tr><td>
</td><td>

**/query**</td><td>

Creates the new collection as a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md).
</td></tr><tr><td>

**delete**</td><td>

*\<coll-name\>*</td><td>

**Delete the named collection**.  
*\<coll-name\>* is the name of the collection to delete. If deleting a sub-collection, the full path must be provided.

Example:  
**dopusrt.exe /col delete "Photos/Holidays/2010"**
</td></tr><tr><td>

**export**</td><td>

*\[\<flags\>\] \<coll-name\> \<export-file\>*</td><td>

**Export the contents of a collection to a text file**.  
*\<flags\>* are one or more optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the collection to export.  
*\<export-file\>* is the full path and file to export to - this must be quoted if it contains spaces.

If the encoding type is not specified (using the optional flags), the file will be encoded as UTF16-LE if any filenames require Unicode, and otherwise in the current ANSI code-page.

Example:  
**dopusrt.exe /col export /utf8 "Find Results" D:\Results.txt**
</td></tr><tr><td>
</td><td>

**/append**</td><td>

If the export file already exists, append to it - otherwise it will be overwritten.
</td></tr><tr><td>
</td><td>

**/utf16be**</td><td>
Force encoding to UTF16-BE.
</td></tr><tr><td>
</td><td>

**/utf16le**</td><td>
Force encoding to UTF16-LE.
</td></tr><tr><td>
</td><td>

**/utf8**</td><td>
Force encoding to UTF8.
</td></tr><tr><td>
</td><td>

**/ansi**</td><td>
Force encoding to the current ANSI code-page.
</td></tr><tr><td>
</td><td>

**/cp:***\<codepage\>*</td><td>
Specify the code-page.
</td></tr><tr><td>

**import**</td><td>

*\[\<flags\>\] \<coll-name\> \<import-file\>*</td><td>

**Import the contents of a text file to a collection**.  
*\<flags\>* are one or more optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the collection to import to.  
*\<import-file\>* is the file to import from.  
The import file should contain one file or folder name per line.  
  
You can import "duplicate files" style collections by prefixing each line in the import file with **\#***\<id\>*\*\*, \*\*to specify the numeric duplicate ID. Items with the same duplicate ID will be grouped together when the file display is set to group by duplicates.  
  
You can also assign names to the duplicate groups by including lines in the format **group:***\<id\>***,***\<name\>***.**  
  
If the import file has a BOM this will be used to determine the encoding type.  
  
Example:  
**dopusrt.exe /col import /ansi "My Photos" /desktop/photos.txt**
</td></tr><tr><td>
</td><td>

**/clear**</td><td>
Clear the collection before importing the new items.
</td></tr><tr><td>
</td><td>

**/create**</td><td>
Create the collection if it doesn't already exist.
</td></tr><tr><td>
</td><td>

**/nocheck**</td><td>
Don't check that the items listed in the import file exist before importing them into the collection.
</td></tr><tr><td>
</td><td>

**/relative:*\<path\>***</td><td>

Specify the path which lines in the list are relative to, if the file does not contain fully qualified paths. If not specified, paths are assumed to be relative to the same folder the list is in.  
Specify **/relative:none** if doing something special where you want the lines imported as-is even if they aren't fully qualified, in which case this cannot be combined with **/nocheck**.  
If the path contains spaces, the entire argument should be quoted.  
  
Example:  
**dopusrt.exe /col import "/relative:C:\My Music" "Jazz" C:\Trane.m3u**
</td></tr><tr><td>
</td><td>

**/utf16be**</td><td>
Assume UTF16-BE if no BOM.
</td></tr><tr><td>
</td><td>

**/utf16le**</td><td>
Assume UTF16-LE if no BOM.
</td></tr><tr><td>
</td><td>

**/utf8**</td><td>
Assume UTF8 if no BOM.
</td></tr><tr><td>
</td><td>

**/ansi**</td><td>
Force conversion from the current ANSI code-page.
</td></tr><tr><td>
</td><td>

**/cp:***\<codepage\>*</td><td>
Force conversion from a specific code-page.
</td></tr><tr><td>

**remove**</td><td>

*\<coll-name\> \<item\> \[\<item\> ...\]*</td><td>

**Remove items from a collection**.  
*\<coll-name\>* is the name of the collection.  
*\<item\>* is the name of the item or items to remove. This can be given as either the item's full path on disk, or its name within the collection. If the path or filename contains spaces, it must be enclosed with quotes. The filename can also contain [standard wildcards](../wildcard_reference/pattern_matching_syntax.md) to remove multiple items at once.  
  
Example:  
**dopusrt.exe /col remove "Find Results" \*.txt**
</td></tr><tr><td>

**rename**</td><td>

*\<old-coll-name\> \<new-coll-name\>*</td><td>

**Rename a collection**.  
*\<old-coll-name\>* is the existing name of the collection.  
*\<new-coll-name\>* is the new name for the collection.  
  
Example:  
**dopusrt.exe /col rename "Find Results" "Saved Results 1"**
</td></tr><tr><td>

**runquery**</td><td>

*\<coll-name\>*</td><td>

**Run (refresh) a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
*\<coll-name\>* is the name of the stored query collection.  
  
Example:  
**dopusrt.exe /col runquery "Stored Queries\Backup Files"**
</td></tr><tr><td>

**setdesc**</td><td>

*\<coll-name\> \<desc\>*</td><td>

**Set the description for a collection**.  
**\<coll-name\>** is the name of the collection.  
**\<desc\>** is the new description for the collection (or nothing to clear the description).  
  
Example:  
**dopusrt.exe /col setdesc "Saved Results 1" "Music before 1990"**
</td></tr><tr><td>

**seticon**</td><td>

*\<coll-name\> \<icon-file\>*</td><td>

**Set a custom icon for a collection**.  
*\<coll-name\>* is the name of the collection.  
*\<icon-file\>* is the full path and filename of the icon file to use.  
  
The icon can come from a .ico or .icl file, or a .exe or .dll file. For files that contain more than one icon, append the desired icon index following the filename.  
  
Example:  
**dopusrt.exe /col seticon "Pics" C:\Tools\viewer.exe,2**
</td></tr><tr><td>

**setpaths**</td><td>

*\[\<flags\>\] \<coll-name\> \<path\> \[\<path\> ...\]*</td><td>

**Set the search path or paths for a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
*\<flags\>* are optional flags, see below for a list of these.  
*\<coll-name\>* is the name of the stored query collection.  
*\<path\>* is the path or paths to add to the query. If a path contains spaces it must be enclosed in quotes.  
  
Example:  
**dopusrt.exe /col setpaths "Backup Files" X:\Backup**
</td></tr><tr><td>
</td><td>

**/add**</td><td>
Add the paths to the query, don't remove any existing ones.
</td></tr><tr><td>

**setquery**</td><td>

*\[\<flags\>\] \<coll-name\> \<query\>*</td><td>

**Set the query string for a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)**.  
\<flags\> are one or more optional flags, see below for a list of these.  
\<coll-name\> is the name of the stored query collection.  
\<query\> is the query string, in [Advanced Query Syntax](https://learn.microsoft.com/en-us/windows/win32/lwef/-search-2x-wds-aqsreference).  
  
The named collection must have been created as a stored query (e.g. with the **dopusrt.exe /col create /query** command).

In conjunction with this, you can use the **/engine** argument to set the search engine used by the query. The default is Windows search; other options are **everything**, **everythingglobal** and **opus**.

Example:  
**dopusrt.exe /col setquery "Backup Files" name:\*.bak /engine=everything**
</td></tr><tr><td>
</td><td>

**/auto**</td><td>

Set the stored query to "auto refresh" mode - the query will be run/refreshed whenever it is loaded.
</td></tr><tr><td>
</td><td>

**/noauto**</td><td>
Set the stored query to not automatically refresh.
</td></tr></tbody>
</table>

