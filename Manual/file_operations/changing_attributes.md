# Changing Attributes

The **Change Attributes & Times** dialog lets you modify both the attributes of a file and its timestamps. To access this function, select the files and folders you wish to modify and choose the **Attributes** command from the **Properties** drop-down menu.

*Attributes* are the set of "flags" that all files and folders have, that control certain properties of the file entry as part of the filesystem. File attributes are displayed in the **Attr** column in the file display (in details and power mode).

![](/Manual/images/media/attr_in_list.png)

The attributes that you can change through this dialog are:

- **Archive**: Indicated by an **A** in the **Attr** column, this attribute is usually used to indicate that a file needs to be archived. The **A** attribute is normally set automatically when a file is saved or edited, and backup tools can use this to tell that a file needs to be backed up (and they would then clear it automatically after doing so).  
  \* **Compressed**: Indicated by a **C** in the **Attr** column, this attribute indicates that the file is compressed. Only NTFS supports file compression - FAT/FAT32 formatted disks don't offer this feature.

If a folder is set as compressed then all new files created in that folder will be compressed by default. This option is exclusive with **Encrypted** (you can't both compress and encrypt the same file).  
\* **Encrypted**: Indicated by an **E** in the **Attr** column, this attribute indicates that the file is encrypted. Only NTFS supports file encryption - FAT/FAT32 formatted disks don't offer this feature.

When a file is encrypted, only the users who have been associated with the file will be able to decrypt it - for example, if your laptop is stolen, the thief might have access to the files on the hard drive, but without your login password would not be able to decrypt the data.

If a folder is set as encrypted then all new files created in that folder will be encrypted by default. This option is exclusive with **Compressed** (you can't both encrypt and compress the same file).  
\* **Hidden**: This is indicated by an **H** in the **Attr** column. When a file is set to hidden its icon will be shown as ghosted (as in the image above), but the file itself is not necessarily hidden from the display. You can configure whether Opus shows hidden files and folders through the **Global hide filters** options in the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md)** Preferences page. The display of hidden files can also be controlled on a per-folder basis using the **[Folder Formats](/Manual/basic_concepts/folder_options/folder_formats.md)** system.  
\* **Non-Indexed**: This is indicated by an **I** in the **Attr** column. The file's content will not be indexed by the system (for searching), only its name and other metadata.

- **Read-only**: This is indicated by an **R** in the **Attr** column. When a file is set to read-only, it normally can't be overwritten or deleted. For example, if you set a **.txt** file to read-only and then try to edit it in Notepad, Notepad would not be able to save over the existing file. Read-only files can still be deleted to the recycle bin as normal.  
  \* **System**: Indicated by an **S** in the **Attr** column, the system attribute is generally used in conjunction with the **H** attribute to mark files and folders that "belong" to the operating system. By default, files marked **H+S** will be hidden from the display, although you can enable the display of these items by turning off the **Hide protected operating system files** option on the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md)**Preferences page.  
  \* **Offline**: Indicated by an **O** in the **Attr** column, this indicates that the file is "offline" - that is, it resides on a network or other computer and will only be copied to your computer when you try to access it. This is most commonly used by Microsoft OneDrive.  
  \* **Pinned**: Indicated by a **P** in the **Attr** column, this indicates that the file is "pinned" - that is, marked to remain permanently on this machine rather than being moved to offline storage. This is most commonly used by Microsoft OneDrive.

*Timestamps* are the various time and date values stored for each file and folder. The timestamps you can modify through this dialog are:

- **Creation time**: The timestamp that represents when the file was first created.  
  \* **Last modified time**: The timestamp that represents the last time the file was modified.

The **Change Attributes & Times** dialog lets you modify either the attributes, or the timestamps, or both. The **Attributes** section of the dialog lets you modify attributes in two ways:

- **Change attributes to**: Select this option if you want to specify the absolute attributes the files are to have.

![](/Manual/images/media/attr_-_change.png)

Click the attributes in the list to toggle their checkmarks on or off. The file's existing attributes will be replaced with the new set of attributes you select.

- **Set and Clear attributes**: Select either or both of these options if you want to set and/or clear specific attributes while leaving others unchanged.

![](/Manual/images/media/attr_-_set_x_clear.png)

In the above screenshot, the **A** attribute would be set and the **R** and **S** attributes would be cleared, but the other attributes of the files (**C**, **E** and **H**) would not be changed either way.

The **Times** section of the dialog lets you choose which timestamps you wish to modify.

- **Set creation time**: Turn on this option to modify the files' creation timestamp.  
  \* **Set last modified time**: Turn on this option to modify the files' last modified timestamp.

For both creation and modified time you can enter a date, a time, or both. Use the checkboxes in the date and time fields to turn them on or off - turning a field off will cause that element in each file's timestamp to be preserved.

Click the **Now** button to set the timestamp to the current date and time. You can also use the **Copy from** option to copy from another timestamp.

  
![](/Manual/images/media/image069.png)

You can copy timestamps from the created and modified timestamps, in the case of pictures from the date taken and date digitized EXIF fields, and also the timestamp from the parent folder. You can also copy from various document-related timestamps.

The **Sub-folders** section of the dialog lets you control what happens how folders are processed by this function.

- **Make the same changes to files within selected folders**: If you turn this option on, the **Change Attributes & Times** function will recursively set the attributes and times you've specified to all files within selected folders (and to files within sub-folders, and so on). If this option is off, any selected folders will have their attributes and times modified as normal but their contents won't be changed.
- **Use filter**: Lets you specify a filter to control which files within sub-folders are modified. You can either enter a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) directly, select a [pre-configured filter](/Manual/preferences/preferences_categories/file_operations/filters.md) from the drop-down, or click the **Define** button to [define a new filter](copying_moving_and_deleting_files/filtered_operations/RAEDME.md).

When you click **OK**, Opus will proceed to make your requested changes to the selected files and folders. All files and folders in the current file display that were selected when you invoked the **Change Attributes & Times** function will be modified. The contents of sub-folders will also be modified if you have the **Make the same changes** option (above) turned on.
