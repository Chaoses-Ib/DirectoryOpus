# Item

The **Item** object represents a file or folder displayed in a tab. You can obtain a collection of **Item** objects from the various methods of the **[Tab](tab.md)** object. A collection of **Item** objects is also used with the **[Command](command.md)** object to specify the files or folders a command should operate on. Using the **[FSUtil](fsutil.md).ReadDir** method to enumerate the contents of a folder also returns an **Item** object. You can create an **Item** from a file path using the **[FSUtil](fsutil.md).GetItem** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the full pathname of the item (i.e. path plus filename).
</td></tr><tr><td>
access</td><td>

*date*</td><td>
Returns the "last accessed" date, in local time.
</td></tr><tr><td>
access_utc</td><td>

*date*</td><td>
Returns the "last accessed" date, in UTC.
</td></tr><tr><td>
attr</td><td>

*int*</td><td>

Returns the item attributes. This value is a series of flags that are logically OR'd together. The attributes supported by Opus are:

|        |                                 |
|--------|---------------------------------|
| 1      | read only                       |
| 2      | hidden                          |
| 4      | system                          |
| 32     | archive                         |
| 1024   | reparse point (junctions, etc.) |
| 2048   | compressed                      |
| 4096   | offline storage                 |
| 8192   | not content-indexed             |
| 16384  | encrypted                       |
| 524288 | pinned                          |

Using the **fileattr** property, which returns a **[FileAttr](fileattr.md)** object, may be easier than dealing with the raw attribute flags.
</td></tr><tr><td>
attr_text</td><td>

*string*</td><td>
Returns the item attributes as a string, as displayed in the file display.
</td></tr><tr><td>
checked</td><td>

*bool*</td><td>

Returns **True** if the item was checked (in [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md)), or **False** otherwise.
</td></tr><tr><td>
create</td><td>

*date*</td><td>
Returns the "creation" date, in local time.
</td></tr><tr><td>
create_utc</td><td>

*date*</td><td>
Returns the "creation" date, in UTC.
</td></tr><tr><td>
current</td><td>

*bool*</td><td>

For **Item** objects obtained from a **[Viewer](viewer.md)**, this property is **True** if the item represents the currently displayed image and **False** otherwise.

For **Item** objects obtained from a file display, the property indicates whether or not the item is the one with focus. The **focus** property is the more proper way to check this, but both work in case you forget which is which.
</td></tr><tr><td>
display_name</td><td>

*string*</td><td>

Returns the display name of the item. Only a few items have a display name that is different to their actual name - some examples are certain system folders (like *C:\Users* which might have a translated display name in non-English locales).
</td></tr><tr><td>
ext</td><td>

*string*</td><td>
Returns the filename extension.
</td></tr><tr><td>
ext_m</td><td>

*string*</td><td>

Returns the filename extension, taking multi-part extensions into account. For example, a file called "file.part1.rar" might return ".rar" for **ext** but ".part1.rar" for **ext_m**.
</td></tr><tr><td>
failed</td><td>

*bool*</td><td>

Returns **True** if the item failed when used by a command. This is only meaningful in conjunction with the **[Command](command.md).files** collection - once the command has returned, this property will indicate success or failure on a per-file basis.
</td></tr><tr><td>
fileattr</td><td>

*object:***[FileAttr](fileattr.md)**</td><td>

Returns a **[FileAttr](fileattr.md)** object that represents the item's attributes.
</td></tr><tr><td>
filegroup</td><td>

*object:***[FileGroup](filegroup.md)**</td><td>

If the file display this item came from is grouped by a particular column, this property returns a **[FileGroup](filegroup.md)** object representing the group the item is in. If the item has no group this will return an empty string.

This property is about grouping the file display by one of its columns. If you're looking for *file type groups*, see the **groups** and **groupsobject** properties, just below.
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

For **Item** objects obtained from a file display, this property is **True** if the object represents the item with focus, and **False** otherwise. Only one item can have focus at a time. The item with focus is typically shown with an outline around it, and is usually the last item which was clicked on, or which was moved to with the keyboard. The item with focus is often also one of the selected items, but not always; selection and focus are two separate things.

For **Item** objects obtained from a **[Viewer](viewer.md)**, the property indicates if the file is the one currently shown in the viewer. The **current** property is the more proper way to test this, but **focus** also works.
</td></tr><tr><td>
got_size</td><td>

*bool*</td><td>

Returns **True** for folder items if their size has been calculated by, for example, the **[GetSizes](../../command_reference/internal_commands/getsizes.md)** command. If **False**, the **size** property will be unreliable for folders.
</td></tr><tr><td>
groups</td><td>

**[Vector](vector.md)**:**[FiletypeGroup](filetypegroup.md)**</td><td>

Returns a **[Vector](vector.md)** of **[FiletypeGroup](filetypegroup.md)** objects representing any and all file type groups that this file is a member of.

If you only want to check membership of a particular file type group, see the **InGroup** method in the section below.

If you're looking for information on how the file display is grouping this file based on one of the displayed columns, see the **filegroup** property, just above.
</td></tr><tr><td>
groupsobject</td><td>

*object:***[FiletypeGroups](filetypegroups.md)**</td><td>

Similar to the groups property, except a **[FiletypeGroups](filetypegroups.md)** object is returned instead of a **[Vector](vector.md)**.
</td></tr><tr><td>
highlighted</td><td>

*object:***[HighlightedColumns](highlightedcolumns.md)**</td><td>

Returns a **[HighlightedColumns](highlightedcolumns.md)** object that lets you enumerate any [selected cells](/Manual/basic_concepts/selecting_files/selecting_cells.md) belonging to this item.

This only applies if the item was retrieved from a **[Tab](tab.md)**. Normally you would use this in a script run from the **Copy Highlighted Cells** context menu.
</td></tr><tr><td>
id</td><td>

*int*</td><td>
This is a unique ID for the item; it is used internally by Opus.
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

Returns **True** if the item represents a folder, and **False** for a file.
</td></tr><tr><td>
is_junction</td><td>

*bool*</td><td>

Returns **True** if the item is a junction to another folder.
</td></tr><tr><td>
is_reparse</td><td>

*bool*</td><td>

Returns **True** if the item is a reparse point.
</td></tr><tr><td>
is_symlink</td><td>

*bool*</td><td>

Returns **True** if the item is a symbolic link.
</td></tr><tr><td>
metadata</td><td>

*object:***[Metadata](metadata.md)**</td><td>

Returns a **[Metadata](metadata.md)** object that provides access to the item's metadata.
</td></tr><tr><td>
modify</td><td>

*date*</td><td>
Returns the "last modified" date, in local time.
</td></tr><tr><td>
modify_utc</td><td>

*date*</td><td>
Returns the "last modified" date, in UTC.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of the item.
</td></tr><tr><td>
name_stem</td><td>

*string*</td><td>

Returns the filename "stem" of the item. This is the name of the item with the filename extension removed. It will be the same as the **name** for folders.
</td></tr><tr><td>
name_stem_m</td><td>

*string*</td><td>

Returns the filename "stem" of the item, taking multi-part extensions into account. For example, a file called "file.part1.rar" might return "file.part1" for **name_stem** but "file" for **name_stem_m**.
</td></tr><tr><td>
nested</td><td>

*bool*</td><td>

Returns **True** if the item was in an expanded sub-folder, **False** if it was in the root of the folder.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns the path of the item's parent folder. This does not include the name of the item itself, which can be obtained via the **name** property.
</td></tr><tr><td>
realpath</td><td>

*object:***[Path](path.md)**</td><td>

Returns the "real" path of the item. For items located in [virtual folders](/Manual/preferences/preferences_categories/folders/virtual_folders/README.md)like [Libraries](/Manual/basic_concepts/virtual_file_system/libraries.md) or [Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), this lets you access the item's underlying path in the real file system. The **realpath** property includes the full path to the item, including its own name.
</td></tr><tr><td>
selected</td><td>

*bool*</td><td>

Returns **True** if the item was selected, or **False** otherwise.
</td></tr><tr><td>
shortpath</td><td>

*object:***[Path](path.md)**</td><td>
Returns the short path of the item, if it has one. Note that short paths are disabled by default in Windows 10.
</td></tr><tr><td>
size</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the size of the item as a **[FileSize](filesize.md)** object.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
InGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

Tests the file for membership of the specified file type group.

Each file type group has two names: An internal name which is always the same in all languages, and a display name which may be translated differently for each language. The display name is what you see in the File Types editor. Groups that come pre-defined when you install Opus have internal names like *"Archives"* and *"Music"* (which are also their English display names). User-defined groups have internal names which are unique, automatically generated GUID strings like *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*.

The *group* argument should be the name of the group you wish to test against, e.g. *"Music"*.

By default, both the internal name and the display name are checked, and a match on either will return true. Prefix the *group* argument with *"name:"* to restrict the search to internal names, or with *"disp:"* to restrict the search to display names.

To get a list of all file type groups which the file matches, use the **groups** property instead (see the section above).
</td></tr><tr><td>
Labels</td><td>

\<string:category\>  
\<string:flags\></td><td>

**[Vector](vector.md)**:*string*</td><td>

This method returns a **[Vector](vector.md)** of strings representing any [labels](/Manual/file_operations/labels.md) that have been assigned to the item.

Both arguments are optional. The first is a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) that lets you filter the returned labels based on their category. For example, pass *"Status"* to only retrieve a list of status icons assigned to a file.

The second optional argument contains flags keywords that control how the labels are returned. The only defined flag is *"explicit"* - if specified, wildcard and label filters will not be considered - only explicitly assigned labels will be returned. Note that if you want to provide the second argument but don't want to filter by category you should pass *"\*"* for the first argument to match all categories.

If explicit labels aren't requested, any global wildcard/filter labels will be returned, along with any per-folder labels configured for the item's folder. Per-folder *content type* and *folder type* labels, however, are not currently returned by this function.
</td></tr><tr><td>
MatchFilter</td><td>

\<object:filter\>  
or \<string:filter\></td><td>

*bool*</td><td>

Returns **True** if the item matches the specified filter. The *filter* argument must be a **[Filter](filter.md)** object created by the **[DOpusFactory](dopusfactory.md).NewFilter** method.

You can also pass a [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) in string form, to parse the filter and compare the item in one operation, although if you're comparing multiple items it would be much more efficient to create the **Filter** first.
</td></tr><tr><td>
Open</td><td>

\<string:mode\>  
\<object:window\></td><td>

*object:***[File](file.md)**</td><td>

Opens this file and returns a **[File](file.md)** object that lets you access its contents as binary data.

By default the file will be opened in *read mode* - specify *"w"* for the optional *mode* parameter to open the file in *write mode.* Note that you cannot both read and write with the same **File** object.

When opening in write mode, you can also specify optional flags that control how the file is opened:

|     |                                                                                                                            |
|-----|----------------------------------------------------------------------------------------------------------------------------|
| wc  | create a new file, only if it doesn't already exist.                                                                       |
| wa  | create a new file, always. If the file already exists it will be overwritten. (This is the default.)                       |
| we  | open existing file. The file will not be created if it doesn't already exist.                                              |
| wo  | open existing file. If the file doesn't exist it will be created.                                                          |
| wt  | truncate existing file. If the file exists it will be truncated. The file will not be created if it doesn't already exist. |
| d   | delete-on-close.                                                                                                           |

When using write mode, you may add *f* (force) to any of the above mode strings to tell Opus to clear the read-only file attribute if it blocks modifying an existing file; otherwise, attempting to open a read-only file for writing will fail. For example, *"wof"* is like *"wo"* mode but also clears the read-only attribute.

If you only want to make changes to the file's attributes without modifying its data you can also specify *"m"* to open it in *modify mode*.

The optional *window* parameter lets you associate the **File** object with a **[Tab](tab.md)** or a **[Lister](lister.md)**, which will be used if Opus needs to display any dialogs (e.g. a UAC elevation dialog). You may also specify the string "NoElevate" to prevent UAC elevation entirely, or "ElevateNoAsk" to prevent UAC prompts while still gaining elevation if something else has already performed it.

A **File** object is always returned, even if the file could not be opened. Check **File.error** on the returned object immediately after creating it to see if opening the file succeeded. Even if the file was not be opened, some of the object's methods may still work. For example, if a file doesn't exist then you can't open it or set its attributes, but permissions on an existing file may allow you to set its attributes while blocking you from modifying it or vice versa.
</td></tr><tr><td>
ShellProp</td><td>

\<string:property\>  
\<string:type\></td><td>

*variant*</td><td>

Returns the value of the specified shell property for the item. The property argument can be the property's PKEY or its name.

If you provide a name then the optional second argument lets you control how the properties are looked up by name. If the value of *type* is "R" then the first property whose raw name matches the supplied name will be used. If the value is "D" then the first property whose display name matches the supplied name will be used. If *type* is omitted then both raw and display names can match.

Note that if a shell property is returned by the system as a SAFEARRAY type, it will be converted automatically to a **[Vector](vector.md)** object.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

Updates the **Item** object from the file on disk. You might use this if you had run a command to change an item's timestamp or attributes, and wanted to retrieve the new information.
</td></tr></tbody>
</table>

