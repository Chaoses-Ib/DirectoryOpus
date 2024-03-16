# Renaming with Metadata

You can use metadata (information about a file) to build up the new names of files by using various metadata insertion codes in the new name field.

![](/Manual/images/media/13/renaming_with_metadata.png) 

In this example the original names of the MP3 files gave no information as to their content (*01.mp3*, *02.mp3*, etc). Luckily, MP3 files usually contain metadata describing the music. Not only are we are using this metadata to rename the files, but we're using it to organize the music into folders.

Click the drop-down button to the left of the **New name** field to display a list of all the metadata fields that Opus supports.

![](/Manual/images/media/13/rename_metadata_menu.png)

These are the same fields as you can add to the file display as columns. When you pick a column from this menu (or one of the special, rename-only, options that appear at the bottom of the menu), the appropriate code is automatically inserted into the new name field at the current cursor position.

In the above example, we are using four music-related fields:

- \<ib:inline-code\>`{mp3artist}`\</ib:inline-code\> to retrieve the name of the artist (*Nick Cave and the Bad Seeds*).
- \<ib:inline-code\>`{mp3album}`\</ib:inline-code\> for the album name (*Abattoir Blues* - an excellent album I should add).
- \<ib:inline-code\>`{mp3track}`\</ib:inline-code\> for the track number on the album.
- \<ib:inline-code\>`{mp3title}`\</ib:inline-code\> for the actual name of the song.

The back-slashes that we've inserted between these fields has the effect of moving the file into sub-folders (relative to the current folder) as well as renaming it. The sub-folders will be created automatically if they don't already exist.

The [Keywords for Columns](/Manual/reference/metadata_keywords/keywords_for_columns.md) page contains a full list of the keywords that can be used by the **Rename** function.

##### Additional codes for rename

As well as the full list of columns, the following codes can be used in the **New name** field:

- \<ib:inline-code\>`[#]`\</ib:inline-code\>: Mark the position where the automatically incrementing number is inserted in the filename (when the **Numbering** action is turned on).
- \<ib:inline-code\>`{parent}`\</ib:inline-code\>: The name of the parent folder of the file being renamed. The **Rename files in selected sub-folders** option affects the name that \<ib:inline-code\>`{parent}`\</ib:inline-code\> returns - if the rename operation recurses into a sub-folder, \<ib:inline-code\>`{parent}`\</ib:inline-code\> would return the name of that sub-folder for files within it.
- \<ib:inline-code\>`{parent2}`\</ib:inline-code\>: Second-level parent folder (i.e. the parent of the parent)
- \<ib:inline-code\>`{parent3}`\</ib:inline-code\>: Third-level parent folder, and so on.
- \<ib:inline-code\>`{parentbase}`\</ib:inline-code\> (Base folder): This code is similar to \<ib:inline-code\>`{parent}`\</ib:inline-code\> except it returns the name of the base folder rather than that of the file's parent - that is, the folder that the rename operation started in. This is most useful with a recursive rename, where the name returned by \<ib:inline-code\>`{parent}`\</ib:inline-code\> would change for files inside sub-folders.
- \<ib:inline-code\>`{parentbase2}`\</ib:inline-code\>: Base folder's parent, and so on.
- \<ib:inline-code\>`{date}`\</ib:inline-code\> or \<ib:inline-code\>`{time}`\</ib:inline-code\>: The current date or time in the local time zone.
- \<ib:inline-code\>`{dateu}`\</ib:inline-code\> or \<ib:inline-code\>`{timeu}`\</ib:inline-code\>: The current date or time in UTC.
- \<ib:inline-code\>`{= ... =}`\</ib:inline-code\>: Inserts the value of an [evaluator expression](/Manual/evaluator/applicable_contexts/rename.md).

The \<ib:inline-code\>`{parent}`\</ib:inline-code\> and \<ib:inline-code\>`{parentbase}`\</ib:inline-code\> codes can also strip the file extension from the parent name, which is usual if the parent folder is an archive file. To do this, add \<ib:inline-code\>`|noext`\</ib:inline-code\> to the code (e.g. \<ib:inline-code\>`{parentbase|noext}`\</ib:inline-code\>).

If you want to use rename to move files into new folders, adding \<ib:inline-code\>`$.\`\</ib:inline-code\> at the start of the new name lets each file be moved relative to the base folder rather than its parent.

The original filename can be retrieved without the file extension using \<ib:inline-code\>`{name|noext}`\</ib:inline-code\>.

##### Legal filenames

Sometimes metadata may contain characters that aren't valid in filenames. For example, the **{time}** field normally formats the time using colons (*HH:MM:SS*), and colons are not legal filename characters. By default illegal characters will be converted to the closest legal alternative (so for example, a colon will be converted to a semi-colon). However you may wish to control this process yourself:

##### Date and time fields

Date and time fields let you configure the date format, the time format, or both. For example,

- \<ib:inline-code\>`{datetaken|D#yyyy-MM-dd}`\</ib:inline-code\>: Inserts the date only in **yyyy-MM-dd** format (e.g. *2008-09-22*)
- \<ib:inline-code\>`{modified|T#HH-mm-ss}`\</ib:inline-code\>: Inserts the modified time in **HH-mm-ss** format (e.g. *13:10:55*)
- \<ib:inline-code\>`{datetaken|D#yyyyMMddT#HHmmss}`\</ib:inline-code\>: Inserts both the date and time as **yyyyMMddHHmmss** (e.g. *20051130154410*).

As you can see in the examples, \<ib:inline-code\>`D#`\</ib:inline-code\> is used to mark the date format, and \<ib:inline-code\>`T#`\</ib:inline-code\> is used to mark the time format. See the [Codes for date and time](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.md) page for information on date and time formats.

##### Numeric fields

Numeric fields let you control zero-padding. For example,

- \<ib:inline-code\>`{size|#8}`\</ib:inline-code\>: Zero-pads the size in bytes to eight places (e.g. *00045412*)
- \<ib:inline-code\>`{mp3track|#2}`\</ib:inline-code\>: Zero-pads the track number to two places (e.g. *08*)

##### Including literal metadata codes

If for some reason you want to include a metadata code in the new filename literally (e.g. you really want to call a file *Blah{size}*) you can escape the leading \<ib:inline-code\>`{`\</ib:inline-code\> with another \<ib:inline-code\>`{`\</ib:inline-code\> character. E.g. \<ib:inline-code\>`*{{size}`\</ib:inline-code\> as a new name would add the literal string \<ib:inline-code\>`{size}`\</ib:inline-code\> to the name of every file.
