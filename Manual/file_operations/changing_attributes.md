# Changing Attributes

The **Change Attributes & Timestamps** dialog lets you modify both the attributes of a file and its timestamps. To access this function, select the files and folders you wish to modify and choose the **Attributes** command from the **Properties** drop-down menu.

### Attributes

*Attributes* are the set of "flags" that all files and folders have, that control certain properties of the file entry as part of the filesystem. File attributes are displayed in the **Attr** column in the file display (in details and power mode) using a single letter to represent each attribute.

The attributes that you can change through this dialog are:

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>Letter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Archive</td>
<td>A</td>
<td>Usually used to indicate that a file needs to be archived. The <strong>A</strong> attribute is normally set automatically when a file is saved or edited, and backup tools can use this to tell that a file needs to be backed up (and they would then clear it automatically after doing so).</td>
</tr>
<tr class="even">
<td>Compressed</td>
<td>C</td>
<td>The file is compressed. Only NTFS supports file compression - FAT/FAT32 formatted disks don't offer this feature.<br />
<br />
If a folder is set as compressed then all new files created in that folder will be compressed by default. This option is exclusive with <strong>Encrypted</strong> (you can't both compress and encrypt the same file).</td>
</tr>
<tr class="odd">
<td>Encrypted</td>
<td>E</td>
<td>The file is encrypted. Only NTFS supports file encryption - FAT/FAT32 formatted disks don't offer this feature.<br />
<br />
When a file is encrypted, only the users who have been associated with the file will be able to decrypt it - for example, if your laptop is stolen, the thief might have access to the files on the hard drive, but without your login password would not be able to decrypt the data.<br />
<br />
If a folder is set as encrypted then all new files created in that folder will be encrypted by default. This option is exclusive with <strong>Compressed</strong> (you can't both encrypt and compress the same file).</td>
</tr>
<tr class="even">
<td>Hidden</td>
<td>H</td>
<td>Marks the file as "hidden". When a file is set to hidden its icon will be faded, but the file itself is not necessarily hidden from the display. You can configure whether Opus shows hidden files and folders through the <strong>Global hide filters</strong> options in the <a href="/preferences/preferences_categories/filtering_and_sorting/global_filters">Global Filters</a> Preferences page. The display of hidden files can also be controlled on a per-folder basis using the <a href="/basic_concepts/folder_options/folder_formats">Folder Formats</a> system.</td>
</tr>
<tr class="odd">
<td>Non-Indexed</td>
<td>I</td>
<td>The file's content will not be indexed by the system (for searching), only its name and other metadata.</td>
</tr>
<tr class="even">
<td>Read-only</td>
<td>R</td>
<td>The file can't normally be overwritten or deleted. For example, if you set a <strong>.txt</strong> file to read-only and then try to edit it in Notepad, Notepad would not be able to save over the existing file. Read-only files can still be deleted to the recycle bin as normal.</td>
</tr>
<tr class="odd">
<td>System</td>
<td>S</td>
<td>Generally used in conjunction with the <strong>H</strong> attribute to mark files and folders that "belong" to the operating system. By default, files marked <strong>H+S</strong> will be hidden from the display, although you can enable the display of these items by turning off the <strong>Hide operating system files</strong> option on the <a href="/preferences/preferences_categories/filtering_and_sorting/global_filters">Global Filters</a> Preferences page.</td>
</tr>
</tbody>
</table>

### Modifying attributes

The **Attributes** section of the dialog lets you modify attributes in two ways:

- **Change attributes**: Select this option if you want to specify the absolute attributes the files are to have.
  Click the attributes in the list to toggle their checkmarks on or off. The file's existing attributes will be replaced with the new set of attributes you select.

- **Turn on** and **Turn off**: Select either or both of these options if you want to turn specific attributes on and/or off while leaving others unchanged.

### Timestamps

*Timestamps* are the various time and date values stored for each file and folder. The timestamps you can modify through this dialog are:

- **Creation time**: The timestamp that represents when the file was first created.
- **Last modified time**: The timestamp that represents the last time the file was modified.

### Modifying timestamps

The **Timestamps** section of the dialog lets you choose which timestamps you wish to modify.

- **Set creation time**: Turn on this option to modify the files' creation timestamp.
- **Set last modified time**: Turn on this option to modify the files' last modified timestamp.

For both timestamps you can enter a date, a time, or both. Use the checkboxes in the date and time fields to turn them on or off - turning a field off will cause that element in each file's timestamp to be preserved.

The dropdown to the right of the time field lets you set the value of the timestamp fields to the current date and time, or initialise them from the selected file:

![](/Manual/images/media/13/timestamp_now.png)

### Copying timestamps from other sources

You can use the **Copy from** dropdown to set each file's timestamp from another source:

- **Modified**: The file's last modified timestamp (only available for creation time).
- **Created**: The file's creation timestamp (only available for last modified time).
- **Date Taken**: The "date taken" value from image files.
- **Date Digitized**: The "date digitized" value from image files.
- **Parent folder**: The timestamp of the parent folder.
- **Document Created**: The "document created" value from document files.
- **Last Edit Time**: The "last edit time" value from document files.
- **Last Saved Date**: The "last saved date" value from document files.

If you select to copy a timestamp that a file doesn't have (e.g. an image value but the file isn't an image) then no change is made to its timestamp.

### Applying time shifts

The **Time shift** field lets you apply a time shift to each file's existing timestamp. See the [Time Shifting](editing_metadata/time_shifting.md) page for more information.

### Making changes to sub-folder contents

The **Sub-folders** section of the dialog lets you control what happens how folders are processed by this function.

- **Make the same changes to files within selected folders**: The function will recursively set the attributes and times you've specified to all files within selected folders (and to files within sub-folders, and so on). If this option is off, any selected folders will have their attributes and times modified as normal but their contents won't be changed.
- **Use filter**: Lets you specify a filter to control which files within sub-folders are modified. You can either enter a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) directly, select a [pre-configured filter](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md) from the drop-down, or click the **Define** button to [define a new filter](filtered_operations/README.md).
