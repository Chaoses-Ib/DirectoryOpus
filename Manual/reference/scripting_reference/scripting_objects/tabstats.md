# TabStats

The **TabStats** object provides various information and statistics about the current folder displayed in a tab. Note that the **[Tab](tab.md)** object provides two versions of this object. **Tab.selstats** takes [Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) into account, and in this mode the values of the "checked" and the "selected" properties will be the same. If the object was retrieved via **Tab.stats** and the file display is in Checkbox Mode, the two sets of properties will be different.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
bigimage_h</td><td>

*int*</td><td>
Returns the width in pixels of the largest image in the folder.
</td></tr><tr><td>
bigimage_w</td><td>

*int*</td><td>
Returns the height in pixels of the largest image in the folder.
</td></tr><tr><td>
bytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in the folder as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
checkbox_mode</td><td>

*bool*</td><td>

Returns **True** if the tab is currently in [Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md).
</td></tr><tr><td>
checkedbytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in checked items as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
checkeddirbytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in checked folders as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
checkeddirs</td><td>

*int*</td><td>
Returns the total number of checked folders.
</td></tr><tr><td>
checkedfilebytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in checked files as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
checkedfiles</td><td>

*int*</td><td>
Returns the total number of checked files.
</td></tr><tr><td>
checkeditems</td><td>

*int*</td><td>
Returns the total number of checked items.
</td></tr><tr><td>
checkedmusiclength</td><td>

*int*</td><td>
Returns the total length in seconds of all checked music files.
</td></tr><tr><td>
dirbytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in all folders as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
dirs</td><td>

*int*</td><td>
Returns the total number of folders.
</td></tr><tr><td>
filebytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in all files as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
filedate_max</td><td>

*date*</td><td>
Returns the latest (most recent) file date in the folder.
</td></tr><tr><td>
filedate_min</td><td>

*date*</td><td>
Returns the earliest (oldest) file date in the folder.
</td></tr><tr><td>
files</td><td>

*int*</td><td>
Returns the total number of files.
</td></tr><tr><td>
items</td><td>

*int*</td><td>
Returns the total number of items.
</td></tr><tr><td>
largestfile</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the size of the largest file in the folder as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
musiclength</td><td>

*int*</td><td>
Returns the total length in seconds of all music files.
</td></tr><tr><td>
selbytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in all selected items as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
seldirbytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in all selected folders as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
seldirs</td><td>

*int*</td><td>
Returns the number of selected folders.
</td></tr><tr><td>
selfilebytes</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns the total number of bytes in all selected files as a **[FileSize](filesize.md)** object.
</td></tr><tr><td>
selfiles</td><td>

*int*</td><td>
Returns the number of selected files.
</td></tr><tr><td>
selitems</td><td>

*int*</td><td>
Returns the number of selected items.
</td></tr><tr><td>
selmusiclength</td><td>

*int*</td><td>
Returns the total length in seconds of all selected music files.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

The first time a script accesses a particular **TabStats** object, a snapshot is taken of the tab state. If the script then makes changes to that tab (e.g. it selects files, creates a new folder, etc), these changes will not be reflected by the object. To re-synchronize the object with the tab, call the **TabStats.Update** method.
</td></tr></tbody>
</table>

