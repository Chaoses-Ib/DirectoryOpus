# TabStats

The **TabStats** object provides various information and statistics about the current folder displayed in a tab. Note that the **[Tab](tab.md)** object provides two versions of this object. **Tab.selstats** takes [Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) into account, and in this mode the values of the "checked" and the "selected" properties will be the same. If the object was retrieved via **Tab.stats** and the file display is in Checkbox Mode, the two sets of properties will be different.

| Property Name | Return Type | Description |
| --- | --- | --- |
| bigimage_h | *int* | Returns the width in pixels of the largest image in the folder. |
| bigimage_w | *int* | Returns the height in pixels of the largest image in the folder. |
| bytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in the folder as a **[FileSize](filesize.md)** object. |
| checkbox_mode | *bool* | Returns **True** if the tab is currently in [Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md). |
| checkedbytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in checked items as a **[FileSize](filesize.md)** object. |
| checkeddirbytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in checked folders as a **[FileSize](filesize.md)** object. |
| checkeddirs | *int* | Returns the total number of checked folders. |
| checkedfilebytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in checked files as a **[FileSize](filesize.md)** object. |
| checkedfiles | *int* | Returns the total number of checked files. |
| checkeditems | *int* | Returns the total number of checked items. |
| checkedmusiclength | *int* | Returns the total length in seconds of all checked music files. |
| dirbytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in all folders as a **[FileSize](filesize.md)** object. |
| dirs | *int* | Returns the total number of folders. |
| filebytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in all files as a **[FileSize](filesize.md)** object. |
| filedate_max | *date* | Returns the latest (most recent) file date in the folder. |
| filedate_min | *date* | Returns the earliest (oldest) file date in the folder. |
| files | *int* | Returns the total number of files. |
| items | *int* | Returns the total number of items. |
| largestfile | *object:***[FileSize](filesize.md)** | Returns the size of the largest file in the folder as a **[FileSize](filesize.md)** object. |
| musiclength | *int* | Returns the total length in seconds of all music files. |
| selbytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in all selected items as a **[FileSize](filesize.md)** object. |
| seldirbytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in all selected folders as a **[FileSize](filesize.md)** object. |
| seldirs | *int* | Returns the number of selected folders. |
| selfilebytes | *object:***[FileSize](filesize.md)** | Returns the total number of bytes in all selected files as a **[FileSize](filesize.md)** object. |
| selfiles | *int* | Returns the number of selected files. |
| selitems | *int* | Returns the number of selected items. |
| selmusiclength | *int* | Returns the total length in seconds of all selected music files. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Update | *none* | *none* | The first time a script accesses a particular **TabStats** object, a snapshot is taken of the tab state. If the script then makes changes to that tab (e.g. it selects files, creates a new folder, etc), these changes will not be reflected by the object. To re-synchronize the object with the tab, call the **TabStats.Update** method. |

