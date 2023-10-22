# Simple Find

The simple mode of the [Find tool]() lets you search for files using one or more criteria.

![](/Manual/images/media/find_simple.png)

In the header above the simple find dialog are **Presets** and **Reset** menus which make it easy to quickly load, save or reset the find criteria.

The labels on the left of each criteria appear in **bold** when something is defined for them, making it a easy to see exactly what you’re searching for. In the example above, we are searching for all files that end with a **.txt** extension, that have been modified within the past seven days, and that contain the text string "individuality". Time, size and type are all being ignored.

You can use the following criteria with Simple Find:

------------------------------------------------------------------------

**Name**: Specify the name of the file to search for.

- The **Wildcards** option lets you use [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) in this field to search for names using wildcards. You can also enter **regex:** followed by a pattern to use [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md).
- The **Any word** option treats every word you enter as a separate search term. For example, if this was turned on and you typed “horse donkey” into the field, Opus would match filenames containing “horse” or “donkey” (or both, in any order). This saves you having to construct complicated *OR* wildcard patterns.
- The **Partial match** option means that the string you enter can match part of the filename, and does not have to match the whole filename.

------------------------------------------------------------------------

**Text**: Searches the file's data, rather than the file's name. If a string is specified here then each file (if it also matches the other criteria) will be searched to see if it contains the specified text. Searching for containing text can make a search much slower. File types that don't store their data as plain text require an IFilter for content searching to work, and these are the same IFilter components which Windows and other software also use.

- The **Wildcards** option lets you use standard pattern matching when defining the text string to search for - if you leave this off, the string must match exactly. The **Case sensitive** option lets you specify that the case (upper/lowercase) of the supplied string must match exactly as well - if this is turned off, then upper and lower case letters are considered the same.

------------------------------------------------------------------------

**Type**: You can use this to search for files or folders of a certain type. For example, instead of specifying **\*.bmp** for the **Name matching** field, you can select **File Type**, **Bitmap Image** from the drop-downs to find bitmap files.

- **All files and folders**: Search for all files or folders matching the other conditions.
- **Files**: Search for only files.
- **Folders**: Search for only folders.
- **Junctions and Links**: Only search for junctions or soft-links.
- **File Type Group**: Search files belonging to a specified file type group. You can use the second drop-down control to choose the group to search for.
- **File Type**: Search files of a particular file type. Use the second drop-down to choose the file type to search for.

------------------------------------------------------------------------

**Date**: This lets you match on a file's last modification date. Only the date is considered, not the time. The following options are available for the **Date** drop-down:  
\* **Ignore**: The date is not considered.

- **On**: Search for files whose datestamp falls exactly on the specified date.
- **Before**: The datestamp must be before the specified date.
- **After**: The datestamp must be after the specified date.
- **Between**: The datestamp must be between the two specified dates.
- **Not Between**: The datestamp must **not** be between the two dates (it must be either earlier than the first date or later than the second).
- **Within**: Lets you specify a date relative to the current date. For example, **Within 7 days** to search for files modified within the past week.

------------------------------------------------------------------------

**Time**: This lets you match on a file's last modification time. Only the time is considered, not the date. Seconds are ignored by this - you only need to specify the hours and minutes of the time to search for. The following options are available:  
\* **Ignore**: The time is not considered.

- **At**: Search for files whose timestamp is exactly the specified time.
- **Before**: The timestamp must be before the specified time.
- **After**: The timestamp must be after the specified time.
- **Between**: The timestamp must fall between the two specified times.
- **Not Between**: The timestamp must **not** fall between the two times.
- **+/- One Hour**: The timestamp must be within one hour (plus or minus) of the specified time.
- **+/- Six Hours**: The timestamp must be within six hours of the specified time.
- **Within**: Lets you specify a time relative to the current time. For example, **Within 30 minutes** to search for files modified in the past half-hour.

------------------------------------------------------------------------

**Size**: This lets you search for a file by size. The size value must be given in **KB** (kilobytes). When the size is compared, it is rounded to the nearest kilobyte, so a search for **Size Equals 1** (kb) would find a file that was 1400 bytes. The options available are:  
\* **Ignore**: The size is not considered.

- **Equals**: The size must match exactly (after rounding).
- **Smaller Than**: The file must be smaller than the specified size.
- **Greater Than**: The file must be larger than the specified size.
- **Between**: The file size must be between the two specified values.
- **Not Between**: The file size must not be between the two specified values.
- **+/- 25%**: The file size must be within 25% (plus or minus) of the specified value.
- **+/- 50%**: The file size must be within 50% (plus or minus) of the specified value.

------------------------------------------------------------------------
