# Filter Clause Types

Each clause has a type which specifies exactly which attribute of a candidate file that clause will match. The clause type is chosen from a drop-down list. A sub-clause is created by selecting *Subclause* from the same drop-down list, but sub-clauses are described on the [Defining a Filter](defining_a_filter.md) page rather than here.

There are a number of clause types that apply to all types of file and folder.

### Attributes

Lets you match based on the file's attributes.

![](/Manual/images/media/13/filter_-_attributes.png)

- **On** attributes must be on (set) for the clause to match
- **Off** attributes must be off (unset) for the clause to match

In the example above, the clause would match only if the file's **R** attribute were set, and **E** and **C** attributes were not set. Supported attributes are:

<table>
<thead>
<tr class="header">
<th>Letter</th>
<th>Attribute</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>R</td>
<td>Read-only</td>
<td>The file can't normally be overwritten or deleted. For example, if you set a <strong>.txt</strong> file to read-only and then try to edit it in Notepad, Notepad would not be able to save over the existing file. Read-only files can still be deleted to the recycle bin as normal.</td>
</tr>
<tr class="even">
<td>A</td>
<td>Archive</td>
<td>Usually used to indicate that a file needs to be archived. The <strong>A</strong> attribute is normally set automatically when a file is saved or edited, and backup tools can use this to tell that a file needs to be backed up (and they would then clear it automatically after doing so).</td>
</tr>
<tr class="odd">
<td>H</td>
<td>Hidden</td>
<td>Marks the file as "hidden". When a file is set to hidden its icon will be faded, but the file itself is not necessarily hidden from the display. You can configure whether Opus shows hidden files and folders through the <strong>Global hide filters</strong> options in the <a href="/preferences/preferences_categories/filtering_and_sorting/global_filters">Global Filters</a> Preferences page. The display of hidden files can also be controlled on a per-folder basis using the <a href="/basic_concepts/folder_options/folder_formats">Folder Formats</a> system.</td>
</tr>
<tr class="even">
<td>S</td>
<td>System</td>
<td>Generally used in conjunction with the <strong>H</strong> attribute to mark files and folders that "belong" to the operating system. By default, files marked <strong>H+S</strong> will be hidden from the display, although you can enable the display of these items by turning off the <strong>Hide operating system files</strong> option on the <a href="/preferences/preferences_categories/filtering_and_sorting/global_filters">Global Filters</a> Preferences page.</td>
</tr>
<tr class="odd">
<td>E</td>
<td>Encrypted</td>
<td>The file is encrypted. Only NTFS supports file encryption - FAT/FAT32 formatted disks don't offer this feature.<br />
<br />
When a file is encrypted, only the users who have been associated with the file will be able to decrypt it - for example, if your laptop is stolen, the thief might have access to the files on the hard drive, but without your login password would not be able to decrypt the data.<br />
<br />
If a folder is set as encrypted then all new files created in that folder will be encrypted by default. This option is exclusive with <strong>Compressed</strong> (you can't both encrypt and compress the same file).</td>
</tr>
<tr class="even">
<td>C</td>
<td>Compressed</td>
<td>The file is compressed. Only NTFS supports file compression - FAT/FAT32 formatted disks don't offer this feature.<br />
<br />
If a folder is set as compressed then all new files created in that folder will be compressed by default. This option is exclusive with <strong>Encrypted</strong> (you can't both compress and encrypt the same file).</td>
</tr>
<tr class="odd">
<td>O</td>
<td>Offline</td>
<td>Indicates that the file is "offline" - that is, it resides on a network or other computer and will only be copied to your computer when you try to access it. This is most commonly used by cloud storage services like Microsoft OneDrive.</td>
</tr>
<tr class="even">
<td>I</td>
<td>Non-Indexed</td>
<td>The file's content will not be indexed by the system (for searching), only its name and other metadata.</td>
</tr>
<tr class="odd">
<td>P</td>
<td>Pinned</td>
<td>The file is "pinned" - that is, marked to remain permanently on this machine rather than being moved to offline storage. This is most commonly used by cloud storage services like Microsoft OneDrive.</td>
</tr>
</tbody>
</table>

### Availability

Lets you match based on a file's offline status (for cloud storage).

### Contains

Searches files for the supplied text string.

![](/Manual/images/media/13/filter_-_contains.png)

The contents of files will be searched to see if they contain the specified string. This works with text files and other files (e.g. Word documents, PDFs) for which the system has an [IFilter](https://en.wikipedia.org/wiki/IFilter) installed.

Because searching files can be a time-consuming operation, **Contains** clauses are "deferred" and processed as the very last step before a file matches a filter.

The options that affect the search are:                                             

- **Use wildcards**: Lets you specify a search pattern using [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).
- **Use regular expression**: Lets you specify the search pattern using [regular expressions](../renaming_files/advanced_rename/rename_modes/regular_expressions.md).
- **Match any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Assume UTF-8 with no BOM**: Tells Opus to assume that plain text files without a Byte Order Mark (BOM) are encoded in UTF8 rather than your computer's default 8-bit character set.
- **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).
- **Partial match**: If this is turned on, words you enter only need to match part of a word to be considered a match. For example, searching for "quint" would match "quintuplet".
- **Ignore diacritics**: Ignores diacritics (accented characters).

### Date

Compares the file's timestamp, but only looks at date and not the time.

The parameters that affect a **Date** comparison are:                                             

- Which timestamp: Select from *Modified* (last modified date), *Created* (creation date) and *Accessed* (last access date).
- Comparison type: Select from *After*, *Before*, *Between* and *Within*.
- Comparison date: Enter the actual date to compare against. For *After* and *Before* this is a single date. For *Between* this is two dates (making a range the date must fall within), and for *Within* this is a relative date from the current day in days, months, weeks or years.

### Date/Time

Compares the file's timestamp, comparing both date and time.

This is similar to a **Date** except that both the time and date portions of the timestamp are compared - you specify both a date and time to compare against. *Within* is not an available comparison type for **Date/Time** clauses.

### Description

Compares the file's description (if it has one assigned to it). The search options are the same as for a **Contains** clause (except for the **Assume UTF-8** option).

### Document

Lets you filter on various document fields, applicable to files like Office or PDF documents.

A drop-down lets you select from the various document fields to compare against:

- **Any field**: Searches for the specified string in any of the text-based document fields.
- **Author**: The document's author.
- **Category**: The document's category (if it has been assigned one).
- **Comment**: Any comment stored in the document.
- **Company**: The company field from the document.
- **Copyright**: The copyright field.
- **Creator**: The person who created the document (not necesarily the same as the author).
- **Document Created**: The date the document was created on. You can specify a date and select a *before*, *after* or *on* comparison.
- **Last Edit Time**: The date the document was last edited.
- **Last Saved By**: The person who last saved the document.
- **Last Saved Date**: The date the document was last saved.
- **Pages**: The number of pages in the document. You can specify the number of pages and select a *greater than*, *less than* or *equals* comparison.
- **Producer**: The producer field.
- **Subject**: The document's subject.
- **Title**: The document's title.

The document fields that take a string parameter to compare against (which are most of them) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.

### Filter

This lets you refer to another pre-configured filter (one listed on the [Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md) page in Preferences). For example, you could have a standard filter that excludes certain types of files that you never want to process it, and then refer to that in other, more specific filters that you create later on. Referencing another filter saves you from having to duplicate all those filters' parameters, and also any changes you make later to the referenced filter will automatically have effect on any filters that use it.

### Full path

This lets you match a file or folder on its full pathname (which includes its own filename).

For example, `C:\Data\Pictures\*\*.jpg` would match any file ending in **.jpg** that was located in any sub-folder of the *C:\Data\Pictures* directory.

Wildcards in Full path clauses are applied to the string as a whole, rather than on individual path components.

### Image

Lets you filter on various image-related fields. All recognized image formats are supported.

The drop-down lets you select from the various fields you can compare on:

- **Aperture**: The aperture of the lens that the image was taken with (as an F-stop value).
- **Artists**: The "artists" text field in the image metadata.
- **Aspect ratio**: The aspect ratio of the image (as a decimal fraction - e.g 1.78 is roughly 1920:1080).
- **Bit depth**: The bit depth of the image.
- **Camera make**: The make (manufacturer) of the camera that took the image.
- **Camera model**: The model of the camera that took the image.
- **Color model**: The color model of the image (*grayscale*, *RGB*, *CMYK*, *YCCK* or *YUV*).
- **Contrast**: The contrast setting when the image was recorded (*hard*, *normal* or *soft*).
- **Copyright**: The copyright information from the image (if any).
- **Creation software**: The software that was used to create the image.
- **Date digitized**: The date the image was digitized. This is sometimes the same as **Date taken** but might be different if the image was originally taken as a non-digital image.
- **Date taken**: The date the image was recorded (a.k.a. shooting time). You can specify a date and select *on*, *after* or *before* as a comparison.
- **Digital zoom**: The digital zoom ratio used to record the image (if any). You can specify a multiplier and select *equal to*, *greater than* or *less than* as a comparison.
- **Dimensions**: The image dimensions. This lets you pick from a drop-down of several common image sizes. If you want more control you can use the **Width** and **Height** fields.
- **Exposure bias**: The camera's exposure bias setting when the image was recorded, specified in *stops*.
- **Exposure program**: The exposure program used to record the image (aperture priority, shutter priority, action, landscape, etc.)
- **Exposure time**: The exposure time used to record the image, specified in seconds or fractions of a second. You can enter the time as a whole number, a fraction (e.g. **1/5**) or a decimal (e.g. **1.8**).
- **F-number**: The f-number (aperture setting) used to record the image, specified in *stops*.
- **Flash**: Whether the flash fired or not when the image was taken, and if so what mode was used.
- **Focal length**: The focal length of the lens when the image was recorded, specified in mm. This is the absolute focal length of the lens.
- **Focal length (35mm)**: The focal length of the lens as a 35mm equivalent value (e.g. a digital camera with a lens focal length of 6mm may be equivalent to a 28mm focal length lens on a 35mm film camera).
- **Height**: The height of the image, in pixels. You can select *equal to*, *greater than* or *less than* as a comparison.
- **Image description**:
- **ISO speed**: The (equivalent) film speed when the image was taken, expressed using the ISO scale.
- **Lens make**: The make (manufacturer) of the lens that took the image.
- **Lens model**: The model of the lens that took the image.
- **Metering mode**: The exposure metering mode used when the image was taken (average, spot, multi-spot, etc).
- **Resolution (X)**: The horizontal (X) resolution of the image, expressed in dots per inch (dpi).
- **Resolution (Y)**: The vertical (Y) resolution of the image in dpi.
- **Rotation**: The rotation information stored in the image, usually from the camera's orientation sensor. This reflects the orientation of the camera when the image was recorded. Select from 0, 90, 180 and 270 degrees.
- **Saturation**: The saturation of the image (*normal*, *high* or *low*).
- **Scene capture type**: The type of scene capture program used by the camera (standard, night, portrait, etc).
- **Sharpness**: The sharpness of the image (*normal*, *hard* or *soft*).
- **Shutter speed**: The speed of the shutter when the image was taken, expressed in seconds or fractions of a second. You can enter the time as a whole number, a fraction (e.g. **1/5**) or a decimal (e.g. **1.8**). 
- **Special instructions**: A general purpose text field in the image metadata.
- **Subject**: A general purpose text field in the image metadata.
- **Subject distance**: The distance from the focal point to the subject, expressed in metres or fractions of a metre. You can enter the distance as a whole number, a fraction or a decimal. For example, **0.2** would correspond to 20 centimeters.
- **Title**: The "title" text field in the image metadata.
- **White balance**: The cameras white balance setting.
- **Width**: The width of the image, in pixels. You can select *equal to*, *greater than* or *less than* as a comparison.

The image fields that take a string parameter to compare against (for example, **Camera make** or **model**) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.

### Label

Matches a file on the basis of its assigned [label](../labels.md) (if it has one).

A drop-down control displays a list of the [configured labels](/Manual/file_operations/labels.md) for you to choose from, or you can type in a pattern to match label names by wildcard.

### Location

This is similar to **Full Path** except it only considers the location (path) of the file, but not the filename. This can be particularly useful when searching [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), as it lets you filter for files based on their real location on disk.

### Music

Lets you filter on various music-related fields. All recognized music formats are supported.

Use the drop-down to select from the various fields you can compare on:

- **Album**: The title of the album.
- **Album artist**: The album's artist.
- **Any field**: Compares the specified text against all text-based music fields.
- **Artists**: The artist or artists of the album (or track).
- **Auto bit rate**: The bit rate the music is digitized at, specified in bits-per-second (bps).
- **BPM**: The beats-per-minute setting of the track (if any).
- **Codec**: The codec used to encode the music file.
- **Comment**: Any comment assigned to the music file.
- **Composers**: The composers of the track.
- **Conductors**: The conductors of the track.
- **Disc number**: The number of the disc (for multi-disc sets).
- **Encoded by**: This field is either used for the name of the person who encoded the track, or the name of the software application they used to do it.
- **Encoding software**: The name of the software application used to encode the track.
- **Genre**: The genre of the music.
- **Initial key**: The initial key of the music.
- **Protected**: Whether the music is DRM-protected or not (*yes* or *no*).
- **Publisher**: The music's publisher.
- **Release date**: The date the music (normally the actual recording) was released.
- **Sample rate**: The sample rate the music is digitized at, specified in hertz (Hz).
- **Song length**: The duration of the music, specified as *hours:minutes:seconds*.
- **Title**: The title of the track.
- **Track number**: The track number within an album (if any).
- **Year**: The year the track was released.

The music fields that take a string parameter to compare against (for example, **Album** or **Genre**) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.

### Name

Compares the file's name against the specified string.

The options for a **Name** clause are:                                             

- **Use wildcards**: Lets you specify a search pattern using [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).
- **Use regular expression**: Lets you specify the search pattern using [regular expressions](../renaming_files/advanced_rename/rename_modes/regular_expressions.md).
- **Match any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).
- **Partial match**: If this is turned on, words you enter only need to match part of a word to be considered a match. For example, searching for "quint" would match "quintuplet".
- **Ignore diacritics**: Ignores diacritics (accented characters).

### Owner

Match against the file's owner. [Standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) are enabled for this search; if you don't specify any wildcards then the search will automatically perform a partial match (so "Fred" will match "Frederick" automatically).

### Path length

Lets you search for files or folders based on the total path length (that is, the number of characters in the full file path, including its name). This is useful for identifying files whose paths exceed the normal Windows 260 character path length limit.

### Rating

Match the rating assigned to the file or folder (if any). You can rate your files using the **[Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md)**.

### Script column

Test the file or folder against a [column generated by a script add-in](/Manual/scripting/example_scripts/adding_a_new_column.md).

Details depend on the type of column the script adds, but will generally be similar to one of the other clause types.

Filtering using script columns allows you to expand the capabilities of Opus's filtering in arbitrary ways, based on anything you can express as a script. Some script add-ins provide columns intended more for filtering than display, although there is no technical difference between the two. A common use for this is to filter folders based on the files they contain, by writing a script column which looks inside each folder and populates a column with "Yes" and "No" values (or similar) to signal whether it should match or not.

### Shell column

Match the value of any column added by third-party shell extension handlers.

The drop-down gives you a list of available columns, and you can use [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md)to match against the value of the selected column. For numeric columns, limited numeric comparison is available using the following operators:

|      |                       |
|------|-----------------------|
| !=   | not equals            |
| ==   | equals                |
| \<   | less than             |
| \>   | greater than          |
| \<=  | less than or equal    |
| \>=  | greater than or equal |
| &&   | and                   |
| \|\| | or                    |

### Size

Compare the file's size.

The parameters that affect a **Size** comparison are:                                             

      * Comparison type: Select from //equal to//, //greater or equal  to//, //greater than//, //less than or equal to// and //less  than//.  
      * Comparison size: Enter the actual size value to compare against.  
      * Comparison units: Specify the units that the comparison size is  specified in. Select from //bytes//, //KB// (kilobytes),  //MB// (megabytes) and //GB// (gigabytes). The search engine  automatically rounds file sizes when comparing against units other than  bytes; for example, a 1158-byte file would match a clause that specified  **equal to 1 KB**. 

A **Size** clause can also be used to compare the size of folders. Because calculating a folder's size can be time consuming, you must specifically enable this behaviour by also including a **Type** clause that specifies *Folders*. For example, the following two clauses would match all empty folders:

![](/Manual/images/media/13/filter_-_empty_dirs.png)

### Sub-folder

This is a special type of sub-clause that controls which folders a recursive operation will descend into. When Opus encounters a sub-folder that it would normally enter as part of an operation (for example, when copying a folder containing multiply-nested sub-folders), it tests each sub-folder against the **Sub-folder** clause. If it fails, the operation skips that sub-folder and all its contents completely.

![](/Manual/images/media/13/filter_-_subclause.png)

In the above example, a **Copy File** operation using that filter would skip over any directories called **.svn** (and all of their contents) no matter where in the folder tree they were encountered. **Sub-folder** clauses have no effect on files matched by the filter; they only control which sub-folders are entered.

Only the **Sub-folder** clause stops Opus from recursing into directories. If a **Sub-folder** clause does not match a folder then Opus will skip that folder and all of its children, even if some of the children may have matched the filter.

On the other hand, with the **Full path** and **Location** clauses, Opus will still examine a folder's children even if the folder itself does not match the filter. Both of these methods can be useful, depending on what you actually want to do. If your aim is to ignore everything below a certain folder then a **Sub-folder** clause is usually best because it avoids inspecting the folder's children unnecessarily. For some examples, see the Opus Forum/FAQ post, [How to filter items by location or sub-folder](https://resource.dopus.com/t/how-to-filter-items-by-location-or-sub-folder/7644).

*Note: Sub-folder clauses do not work with the [Synchronize](../copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool.*

### Tags

Compares against any tags assigned to the file. [Standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) are enabled for this search; if you don't specify any wildcards then the search will automatically perform a partial match (so "account" will match "accounting" automatically). The string you enter is compared against all tags assigned to the file separately, so if you want to match two specific tags, you need to use two separate **Tags** clauses.

### Target

If a file is a junction, shortcut or link, the **Target** clause lets you match on what it points to (the path of the target of the shortcut).

For example, `C:\Program Files\*\*.exe` would match shortcuts that pointed to any .exe (application files) below the *C:\Program Files* folder.

You can choose from the following options:

- **Use wildcards**: Lets you specify a search pattern using [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).
- **Use regular expression**: Lets you specify the search pattern using [regular expressions](../renaming_files/advanced_rename/rename_modes/regular_expressions.md).
- **Match any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).
- **Partial match**: If this is turned on, words you enter only need to match part of a word to be considered a match. For example, searching for "quint" would match "quintuplet".
- **Ignore diacritics**: Ignores diacritics (accented characters).
- **File**: Only match shortcuts that point to files.
- **Folder**: Only match shortcuts that point to folders.

### Time

Similar to a **Date** clause, this compares the file's timestamp, but only looks at the time portion and not the date.

The parameters that affect a **Time** comparison are:

      * Which timestamp: Select from //Modified// (last modified date),  //Created// (creation date) and //Accessed// (last access date).  
      * Comparison type: Select from //After//, //Before//,  //Between// and //Within//.  
      * Comparison time: Enter the actual time to compare against. For  //After// and //Before// this is a single time. For //Between//  this is two times (making a range the time must fall within), and for  //Within// this is a relative time from the current time within  hours, minutes or seconds. The time for a //Within// comparison is  relative to //now// - that is, if the current time when the filter is  used is 15:35 and the clause specified **within 1 hour**,  anything dated the current date between 14:35 and 15:35 would match, but a  file from yesterday at 15:10 would not.

### Type

This lets you match a file by file type.

The first drop-down lets you choose how you want to match by type:

- **File Type**: Match a single filetype. The second drop-down lets you pick from a list of all registered file types. So instead of using a **Name Match \*.bmp** clause, you can specify **Type Match File Type Bitmap Image**.
- **File Type Group**: Match any files that are a member of the specified group. The second drop-down lets you pick from a list of groups.
- **Files**: Matches all files, but not folders
- **Folders**: Matches all folders, but not files.
- **Junctions and Links**: Matches shortcuts, folder junctions and hard or soft links. You can use this in conjunction with the **Target** clause to search for, for example, shortcuts pointing to a specific folder or file.
