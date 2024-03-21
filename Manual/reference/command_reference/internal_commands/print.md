# Print

The **Print** internal command can be used to:

- Print photos and other images using the Windows Photo Printing wizard
- Print supported image files directly
- Print other files via their registered handlers
- Generate a folder listing and either print it, save it to a file or copy it to the clipboard
- Export a folder listing in **CSV** format for import into Excel, etc.
- Display a list of installed printers and let you modify the default printer

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Prints selected files. If only image files are selected (or no files at all are selected), the Windows Photo Printing wizard will be invoked. Non-image files will be printed via their registered print handler.<br /><br />*Example:* `Print` |
| AS | /K | **txt** | Use plain text format when printing a folder to disk or the clipboard.<br /><br />*Example:* `Print FOLDER TO=clip AS=txt QUIET` |
|  |  | **csv** | Use CSV (comma-separated value) format when printing a folder to disk or the clipboard.<br /><br />*Example:* `Print FOLDER TO /desktop/dirprint.csv AS=csv QUIET` |
|  |  | **tab** | Use tab-separated format when printing a folder to disk or the clipboard.<br /><br />*Example:* `Print FOLDER TO clip AS tab QUIET` |
| AUTOSIZECOLUMNS | /K | **yes** | When printing a folder listing to a printer, or as a plain-text file, column widths will be auto-calculated to fit their contents.<br /><br />*Example:* `Print FOLDER "Brother HL-4050CDN" AUTOSIZECOLUMNS=yes` |
|  |  | **no** | Columns will not be autosized - instead the widths from the folder format will be used.<br /><br />*Example:* `Print FOLDER TO /desktop/dir.txt AS=txt AUTOSIZECOLUMNS=no` |
| CALCSIZES | /K | **yes** | Calculate folder sizes when printing a folder.<br /><br />*Example:* `Print FOLDER TO clip CALCSIZES=yes QUIET` |
|  |  | **no** | Do not calculate folder sizes.<br /><br />*Example:* `Print FOLDER TO clip CALCSIZES=no QUIET` |
| DEFAULTLIST | /S | *(no value)* | Displays a generated list of installed printers (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). You can use this list to change the default printer, and right-click the items in the list to display the printer's context menu. You can also print a file by dropping it on the generated button for a printer.<br /><br />*Example:* `Print DEFAULTLIST` |
| ENCODING | /K | **ansi** | When printing a folder listing to a file, specifies that **ANSI** encoding should be used. This is the default encoding type initially, but if the *Print Folder* dialog is used in interactive mode it will remember the last encoding type manually selected. Using this argument lets you override the last used encoding type.<br /><br />*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=ansi QUIET` |
|  |  | **utf8** | Sets the encoding type to **UTF8** with a BOM (Byte Order Mark).<br /><br />*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=bom QUIET` |
|  |  | **utf8nobom** | Sets the encoding type to **UTF8** without a BOM.<br /><br />*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=utf8nobom` |
| FILTER | /K | *\<filter\>* | Use a [filter](/Manual/file_operations/filtered_operations/README.md) when printing the contents of sub-folders (via the **FLATVIEW** argument). This can be the name of a filter you have previously created via the **[File Operations / Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences, or it can be a simple [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to filter by filename.<br /><br />*Example:* `Print FOLDER FILTER \*.jpg FLATVIEW=nofolders QUIET` |
| FILTERDEF | /K/R | *\<filter\>* | Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to filter the contents of sub-folders when printing folder contents. This is similar to the **FILTER** argument, however the filter does not need to be predefined.<br /><br />This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.<br /><br />*Example:* `Print FOLDER FLATVIEW=nofolders QUIET FILTERDEF name match \*.zip and size match \> 2 mb` |
| FLATVIEW | /K | **no** | Do not print the contents of sub-folders when printing a folder listing.<br /><br />*Example:* `Print FOLDER FLATVIEW=no QUIET` |
|  |  | **mixed** | Prints the contents of sub-folders in "mixed" mode. This mixes files and folders together in a flat list.<br /><br />*Example:* `Print FOLDER FLATVIEW=mixed TO clip QUIET` |
|  |  | **nofolders** | Prints the contents of sub-folders in "mixed - no folders mode". All files from sub-folders are listed, but the folders themselves are not shown.<br /><br />*Example:* `Print FOLDER FLATVIEW=nofolders QUIET` |
|  |  | **grouped** | Prints the contents of sub-folders in "grouped" mode. Files and folders are indented to reflect the tree hierarchy.<br /><br />*Example:* `Print FOLDER TO /desktop/dirtree.txt FLATVIEW=grouped QUIET` |
| FOLDER | /O | *(no value)* | Displays the **[Print Folder](/Manual/additional_functionality/print_folder.md)** dialog, which lets you print or export the contents of the current folder displayed in the Lister.<br /><br />*Example:* `Print FOLDER` |
|  |  | **selected** | Only selected files in the current folder will be printed by the Print Folder function.<br /><br />*Example:* `Print FOLDER=selected` |
|  |  | *\<path\>* | Specify the folder path to print.<br /><br />*Example:* `Print FOLDER /desktop TO clip QUIET` |
| FONT | /K | *\<name\>,\<size\>* | Specify the font to use when printing to the printer.<br /><br />*Example:* `Print FOLDER FONT Arial,20 QUIET` |
| FORMAT | /K | *\<format name\>* | Use the specified favorite folder format to control the columns, sort order, and similar details of the printed information.<br /><br />The named format must first have been created from the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** page in Preferences.<br /><br />*Example:* `Print FOLDER FORMAT="My Format" QUIET`<br /><br />The **FORMAT** argument also accepts the following special keywords:<br /><br />- **!current**: Use the file display's current format, including any ad-hoc edits made to it.<br />- **!default**: Use the Folder Type format applicable to current folder. For example, **Network Drives** if it's a network drive.<br />- **!factory**: Use the hardcoded factory-default format.<br />- **!folder**: Use the format for the current folder. This is generally the format you would get when opening the current folder in a new window.<br />- **!user**: Use the **User Default** format.<br /><br />*Example:* `Print FOLDER FORMAT=!current QUIET` |
| HEADER | /K | **top** | Print a header at the top of each page (or when printing to disk or the clipboard, at the top of the listing).<br /><br />*Example:* `Print FOLDER HEADER=top QUIET` |
|  |  | **bottom** | Print a footer at the bottom of each page (or the bottom of the listing).<br /><br />*Example:* `Print FOLDER HEADER=bottom QUIET` |
|  |  | **both** | Print both a header and a footer.<br /><br />*Example:* `Print FOLDER HEADER=both QUIET` |
|  |  | **none** | Do not print a header or a footer.<br /><br />*Example:* `Print FOLDER HEADER=none QUIET` |
| HEADING | /O | *(no value)* | When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.<br /><br />When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.<br /><br />*Example:* `Print DEFAULTLIST HEADING` |
|  |  | *\<heading text\>* | You can specify the heading text if you want it to be different to the button's label.<br /><br />*Example:* `Print DEFAULTLIST HEADING="Default Printer"` |
| KEYWORDS | /S | *(no value)* | When printing a folder listing, the headings for each column will show keywords (sometimes called "raw names") instead of display names. Keywords uniquely identify each column and do not vary by language, while display names are translated and may not be unique.<br /><br />*Example:* `Print FOLDER AS=csv TO=clip FLATVIEW=no QUIET KEYWORDS` |
| NOWIZARD | /S | *(no value)* | Bypass the Windows Photo Printing Wizard for image files; Opus can natively print any image format that it is able to view.<br /><br />*Example:* `Print NOWIZARD` |
| QUIET | /S | *(no value)* | Print the folder using the specified options without displaying the *Print Folder* dialog first.<br /><br />*Example:* `Print FOLDER QUIET` |
| SETDEFAULT | /K | *\<printer name\>* | Set the named printer as the system default printer. The name you provide must be the full name of the printer as shown in the Printers Control Panel. Make sure you enclose the name in quotes if it contains a space.<br /><br />*Example:* `Print SETDEFAULT "Brother HL-4050CDN"` |
| TO | /K | *\<printer name\>* | Print selected files or folders to the specified printer (overriding the default printer). A button with this command can also accept files dropped on it to print them.<br /><br />*Example:* `Print TO "Brother HL-4050CDN"` |
|  |  | *\<file name\>* | Print the folder contents to a specified disk file.<br /><br />*Example:* `Print TO dirlist.txt FOLDER C:\Data QUIET AS txt` |
|  |  | **clip** | Print the folder listing to the clipboard.<br /><br />*Example:* `Print FOLDER TO clip AS csv` |

