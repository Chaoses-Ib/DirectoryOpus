# SetAttr

The **SetAttr** internal command can be used to:

- Modify the attributes of files or folders
- Compress (by setting the **C** attribute) or encrypt files (by setting the **E** attribute), and set the default compression/encryption status for folders
- Modify the last modified and creation timestamps of files or folders
- Modify file metadata, either through a [user-interface](/Manual/file_operations/editing_metadata/README.md) or [programmatically](../../metadata_keywords/keywords_for_setattr_meta.md)
- Assign your own description to files and folders, and edit the internal [comment](/Manual/file_operations/creating_archives/zip_files/zip_comment.md) for a Zip archive
- Modify attributes of files on remote FTP sites

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

Displays the **[Change Attributes & Times](/Manual/file_operations/changing_attributes.md)** dialog, which lets you modify the attributes and timestamps of selected files and folders.

*Example:* `SetAttr`
</td></tr><tr><td>
ATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

Sets the specified attributes for selected files and folders, and clears all others. The *\<attributes\>* value must consist of one or more of the following letters:

|       |                                                                        |
|-------|------------------------------------------------------------------------|
| **R** | Read-only (files can not be deleted or overwritten)                    |
| **A** | Archive (file needs to be archived, used by backup tools)              |
| **H** | Hidden (files can be marked as hidden to hide them from the display)   |
| **S** | System (file is a system file - usually set in conjunction with **H**) |
| **N** | Normal (normal attributes, none of the other attributes set)           |
| **I** | Non-content Indexed (contents will not be indexed by the system)       |
| **C** | Compressed (on NTFS-formatted drives only)                             |
| **E** | Encrypted (on NTFS-formatted drives only)                              |

Note that modifying the **C** or **E** attributes may take longer than normal, as the file data has to be (un)compressed or (un)encrypted. Setting these attributes for folders sets the default compression/encryption state for new files created in those folders. A file can be compressed, or encrypted, but not both at once.

*Example:* `SetAttr ATTR rca`
</td></tr><tr><td>
CHMOD</td><td>
/K</td><td>

*\<attribute mask\>*</td><td>

Sets the specified attributes for files on a remote FTP site. The *\<attribute mask\>* is specified using [octal notation](http://en.wikipedia.org/wiki/File_system_permissions#Octal_notation).

*Example:* `SetAttr CHMOD 666`
</td></tr><tr><td>
CLEARATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

Clears the specified attributes for selected files and folders. The specified attributes will be turned off, but other attributes will be untouched. See the description of the **ATTR** argument for a list of attribute values.

*Example:* `SetAttr CLEARATTR c`
</td></tr><tr><td>
CREATED</td><td>
/K</td><td>

*\<date/time\>*</td><td>

Sets the creation timestamp for selected files and folders. The value for this argument can be given as either a date only, a time only, or a date and time.

The accepted formats for the date string are **YYYYMMDD** or **YYYY-MM-DD**, and the time string must be in the format **HH:MM:SS**.

If you specify a time as well as a date the time must come after the date, separated by a space, and you must enclose the entire value in quotes (because of the embedded space). If only a time is provided, the file's current date will be preserved (and vice versa).

*Example:* `SetAttr CREATED "1973-09-22 3:35"`
</td></tr><tr><td>
</td><td>
</td><td>

**now**</td><td>

Sets the creation timestamp to the current date and time.

*Example:* `SetAttr CREATED=now`
</td></tr><tr><td>
</td><td>
</td><td>

**modified**</td><td>

Copies the last modified timestamp of the file.

*Example:* `SetAttr CREATED=modified`
</td></tr><tr><td>
</td><td>
</td><td>

**taken**</td><td>

For image files, copies the *Date Taken* timestamp. If the file doesn't have an EXIF tag the creation timestamp won't be changed.

*Example:* `SetAttr CREATED=taken`
</td></tr><tr><td>
</td><td>
</td><td>

**digitized**</td><td>

For image files, copies the *Date Digitized* timestamp. If the file doesn't have an EXIF tag the creation timestamp won't be changed.

*Example:* `SetAttr CREATED=digitized`
</td></tr><tr><td>
</td><td>
</td><td>

**parent**</td><td>

Copies the creation timestamp from the parent folder.

*Example:* `SetAttr CREATED=parent`
</td></tr><tr><td>
</td><td>
</td><td>

**doccreated**</td><td>

For document files, copies the *Document Created* timestamp. If the file doesn't have this timestamp in its metadata the creation timestamp won't be changed.

*Example:* `SetAttr CREATED=doccreated`
</td></tr><tr><td>
</td><td>
</td><td>

**docedited**</td><td>

For document files, copies the //Document Last Edited //timestamp. If the file doesn't have this timestamp in its metadata the creation timestamp won't be changed.

*Example:* `SetAttr CREATED=docedited`
</td></tr><tr><td>
</td><td>
</td><td>

**docsaved**</td><td>

For document files, copies the *Document Last Saved* timestamp. If the file doesn't have this timestamp in its metadata the creation timestamp won't be changed.

*Example:* `SetAttr CREATED=docsaved`
</td></tr><tr><td>
DEHYDRATE</td><td>
/S</td><td>

*(no value)*</td><td>

For cloud files on Windows 10 and above, this command "dehydrates" the file (removes local data and replaces it with a placeholder). This is equivalent to the "Free up space" context menu command that OneDrive adds.

*Example:* `SetAttr DEHYDRATE`
</td></tr><tr><td>
DESCRIPTION</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **[Set Description](/Manual/file_operations/file_descriptions.md)** dialog, which lets you assign your own description string to selected files and folders.

*Example:* `SetAttr DESCRIPTION`
</td></tr><tr><td>
</td><td>
</td><td>

*\<description\>*</td><td>

Sets the description for selected files and folders to the specified string.

*Example:* `SetAttr DESCRIPTION "Project Files for Keith"`

Note that an empty string will be treated the same as not passing a string at all, causing the **[Set Description](/Manual/file_operations/file_descriptions.md)** dialog to open. If you want an empty string to clear the description, use the **SETDESCRIPTION** argument instead.
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<filename\>, ...*</td><td>

Specifies the name of the file or files to modify. If you don't provide this argument the command operates on all selected items in the source Lister. This is the default argument for the **SetAttr** command - you don't need to specify the **FILE** keyword.

If you only specify the filename instead of the full path of the file or files, Opus will look in the current source folder. You can also specify a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Remember that if the filename contains spaces you need to enclose it in quotes.

*Example:* `SetAttr *.xls DESCRIPTION "Annual Results for 2011" SETATTR r`
</td></tr><tr><td>
FILTER</td><td>
/K</td><td>

*\<filter\>*</td><td>

Applies the specified filter to the contents of selected folders. This must have previously been created from the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences. You can also directly specify a [simple wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md)

*Example:* `SetAttr FILTER "temp files" ATTR n`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to filter the contents of selected folders. This is similar to the **FILTER** argument, however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `SetAttr ATTR n FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
META</td><td>
/O/M</td><td>

*(no value)*</td><td>

Displays the **[Set Metadata](/Manual/file_operations/editing_metadata/README.md)** dialog, which lets you modify the metadata for selected files and folders.

*Example:* `SetAttr META`
</td></tr><tr><td>
</td><td>
</td><td>

*keyword:\<value\>, ...*</td><td>

Sets the specified metadata fields to the supplied values. Changes are made (where applicable) to all selected files.

Each *keyword:\<value\>* pair must be enclosed in quotes if the value contains any spaces. This argument can accept multiple *keyword:\<value\>* pairs to make changes to more than one metadata field at once.

See the section on [programmatic setting of metadata](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.md) for more information.

*Example:* `SetAttr META "artist:Pink Floyd" "album:Dark Side of the Moon"`
</td></tr><tr><td>
MODIFIED</td><td>
/K</td><td>

*\<date/time\>*</td><td>

Sets the last modified timestamp for selected files and folders. The value for this argument can be given as either a date only, a time only, or a date and time.

The accepted formats for the date string are **YYYYMMDD** or **YYYY-MM-DD**, and the time string must be in the format **HH:MM:SS**.

If you specify a time as well as a date the time must come after the date, separated by a space, and you must enclose the entire value in quotes (because of the embedded space). If only a time is provided, the file's current date will be preserved (and vice versa).

*Example:* `SetAttr MODIFIED 20080110`
</td></tr><tr><td>
</td><td>
</td><td>

**now**</td><td>

Sets the last modified timestamp to the current date and time.

*Example:* `SetAttr MODIFIED=now`
</td></tr><tr><td>
</td><td>
</td><td>

**created**</td><td>

Copies the creation timestamp of the file.

*Example:* `SetAttr MODIFIED=created`
</td></tr><tr><td>
</td><td>
</td><td>

**taken**</td><td>

For image files, copies the *Date Taken* timestamp. If the file doesn't have an EXIF tag the last modified timestamp won't be changed.

*Example:* `SetAttr MODIFIED=taken`
</td></tr><tr><td>
</td><td>
</td><td>

**digitized**</td><td>

For image files, copies the *Date Digitized* timestamp. If the file doesn't have an EXIF tag the last modified timestamp won't be changed.

*Example:* `SetAttr MODIFIED=digitized`
</td></tr><tr><td>
</td><td>
</td><td>

**parent**</td><td>

Copies the last modified timestamp from the parent folder.

*Example:* `SetAttr MODIFIED=parent`
</td></tr><tr><td>
</td><td>
</td><td>

**doccreated**</td><td>

For document files, copies the *Document Created* timestamp. If the file doesn't have this timestamp in its metadata the last modified timestamp won't be changed.

*Example:* `SetAttr MODIFIED=doccreated`
</td></tr><tr><td>
</td><td>
</td><td>

**docedited**</td><td>

For document files, copies the //Document Last Edited //timestamp. If the file doesn't have this timestamp in its metadata the last modified timestamp won't be changed.

*Example:* `SetAttr MODIFIED=docedited`
</td></tr><tr><td>
</td><td>
</td><td>

**docsaved**</td><td>

For document files, copies the *Document Last Saved* timestamp. If the file doesn't have this timestamp in its metadata the last modified timestamp won't be changed.

*Example:* `SetAttr MODIFIED=docsaved`
</td></tr><tr><td>
PIN</td><td>
/O</td><td>

*(no value)*</td><td>

For cloud files on Windows 10 and above, this command toggles the "pinned" status of the file on and off. This is equivalent to the "Always keep on this device" context menu command that OneDrive adds. When a file is "pinned", it's always kept on the device. When it's "unpinned" it may or may not be kept locally.

*Example:* `SetAttr PIN`
</td></tr><tr><td>
</td><td>
</td><td>

**yes**</td><td>

Sets the pinned state on selected cloud files.

*Example:* `SetAttr PIN=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Clears the pinned state on selected cloud files.

*Example:* `SetAttr PIN=no`
</td></tr><tr><td>
RECURSE</td><td>
/O</td><td>

*(no value)*</td><td>

Changes made by this command will be recursively applied to files within selected folders. This does not affect the **META** argument - only attributes, timestamps and descriptions can be applied recursively.

*Example:* `SetAttr CLEARATTR hs RECURSE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Prevents the command from working recursively if the recurse option has been turned on by default.

*Example:* `SetAttr SETDESCRIPTION="2023 Trip To Japan" RECURSE=no`
</td></tr><tr><td>
SETATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

Sets the specified attributes for selected files and folders. The specified attributes will be turned on, but other attributes will be untouched. See the description of the **ATTR** argument for a list of attribute values.

*Example:* `SetAttr SETATTR r`
</td></tr><tr><td>
SETDESCRIPTION</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the description for selected files and folders.

*Example:* `SetAttr SETDESCRIPTION`

The difference between the **DESCRIPTION** and **SETDESCRIPTION** arguments is what they do when not given a value. **SETDESCRIPTION** clears the description while **DESCRIPTION** opens a dialog for you to type in a description.
</td></tr><tr><td>
</td><td>
</td><td>

*\<description\>*</td><td>

Sets the description for selected files and folders to the specified string.

*Example:* `SetAttr SETDESCRIPTION "Approved for release"`
</td></tr><tr><td>
TOGGLEATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

Toggles (inverts) the state of the specified attributes. If each attribute specified is currently set it will be cleared, and vice versa. Attributes that aren't specified will be unaffected. See the description of the **ATTR** argument for a list of attribute values.

*Example:* `SetAttr TOGGLEATTR h`
</td></tr><tr><td>
ZIPCOMMENT</td><td>
/S</td><td>

*(no value)*</td><td>

Lets you edit the internal [Zip comment](/Manual/file_operations/creating_archives/zip_files/zip_comment.md) when viewing the contents of a Zip archive. The comment is stored inside the Zip file and can be displayed by other Zip tools.

*Example:* `SetAttr ZIPCOMMENT`
</td></tr></tbody>
</table>

