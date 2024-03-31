# Simple Find

The simple mode of the [find tool]() lets you search for files using one or more criteria.

When multiple criteria are configured, they all must match for a file to be found. Use the [advanced mode](advanced_find/README.md) if you want more control over this.

The labels on the left of each criterion appear in **bold** when something is defined for them, making it a easy to see exactly what you’re searching for.

You can use the following criteria with simple find:

### Name

Search by filename. The options for **Name** are:

- **Wildcards**: Enables [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) to search for names using wildcards.
- **Regular expressions**: Enables [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md) instead of standard wildcards.
- **Any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Ignore diacritics**: Ignores diacritics (accented characters).
- **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).
- **Partial match**: If this is turned on, words you enter only need to match part of a word to be considered a match. For example, searching for "quint" would match "quintuplet".

### Text

Searches the file's contents, rather than the file's name. If a string is specified here then each file (if it also matches the other criteria) will be searched to see if it contains the specified text. Searching for containing text can make a search much slower. File types that don't store their data as plain text require an IFilter for content searching to work, and these are the same IFilter components which Windows and other software also use.

The options for **Text** are mostly the same as for **Name**, with the addition of:

- **Assume UTF8**: Tells Opus to assume that plain text files without a Byte Order Mark (BOM) are encoded in UTF8 rather than your computer's default 8-bit character set.

### Type

Search for files or folders of a certain type. For example, instead of specifying `*.bmp` for the **Name** field, you can select **File Type**, **Bitmap Image** from the drop-downs to find bitmap files.

- **All files and folders**: Search for all files or folders matching the other conditions.
- **Files**: Search for only files.
- **Folders**: Search for only folders.
- **Junctions and Links**: Only search for junctions or soft-links.
- **File Type Group**: Search files belonging to a specified file type group. You can use the second drop-down control to choose the group to search for.
- **File Type**: Search files of a particular file type. Use the second drop-down to choose the file type to search for.

### Date

Search for files by their last modification date. Only the date is considered, not the time. The following options are available for the **Date** drop-down:

- **Ignore**: The date is not considered.
- **On**: Search for files whose datestamp falls exactly on the specified date.
- **Before**: The datestamp must be before the specified date.
- **After**: The datestamp must be after the specified date.
- **Between**: The datestamp must be between the two specified dates.
- **Not Between**: The datestamp must **not** be between the two dates (it must be either earlier than the first date or later than the second).
- **Within**: Lets you specify a date relative to the current date. For example, **Within 7 days** to search for files modified within the past week.

### Time

Search based on a file's last modification time. Only the time is considered, not the date. Seconds are also ignored - you only need to specify the hours and minutes of the time to search for. The following options are available:

- **Ignore**: The time is not considered.
- **At**: Search for files whose timestamp is exactly the specified time.
- **Before**: The timestamp must be before the specified time.
- **After**: The timestamp must be after the specified time.
- **Between**: The timestamp must fall between the two specified times.
- **Not Between**: The timestamp must **not** fall between the two times.
- **+/- One Hour**: The timestamp must be within one hour (plus or minus) of the specified time.
- **+/- Six Hours**: The timestamp must be within six hours of the specified time.
- **Within**: Lets you specify a time relative to the current time. For example, **Within 30 minutes** to search for files modified in the past half-hour.

### Size

Search for a file by size. The size value must be given in **KB** (kilobytes). When the size is compared, it is rounded to the nearest kilobyte, so a search for **Size Equals 1** (kb) would find a file that was 1400 bytes. The options available are:

- **Ignore**: The size is not considered.
- **Equals**: The size must match exactly (after rounding).
- **Smaller Than**: The file must be smaller than the specified size.
- **Greater Than**: The file must be larger than the specified size.
- **Between**: The file size must be between the two specified values.
- **Not Between**: The file size must not be between the two specified values.
- **+/- 25%**: The file size must be within 25% (plus or minus) of the specified value.
- **+/- 50%**: The file size must be within 50% (plus or minus) of the specified value.
