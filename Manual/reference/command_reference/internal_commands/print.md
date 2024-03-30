# Print

The **Print** internal command can be used to:

- Print photos and other images using the Windows Photo Printing wizard
- Print supported image files directly
- Print other files via their registered handlers
- Generate a folder listing and either print it, save it to a file or copy it to the clipboard
- Export a folder listing in **CSV** format for import into Excel, etc.
- Display a list of installed printers and let you modify the default printer

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

Prints selected files. If only image files are selected (or no files at all are selected), the Windows Photo Printing wizard will be invoked. Non-image files will be printed via their registered print handler.

*Example:* `Print`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

**txt**</td><td>

Use plain text format when printing a folder to disk or the clipboard.

*Example:* `Print FOLDER TO=clip AS=txt QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**csv**</td><td>

Use CSV (comma-separated value) format when printing a folder to disk or the clipboard.

*Example:* `Print FOLDER TO /desktop/dirprint.csv AS=csv QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**tab**</td><td>

Use tab-separated format when printing a folder to disk or the clipboard.

*Example:* `Print FOLDER TO clip AS tab QUIET`
</td></tr><tr><td>
AUTOSIZECOLUMNS</td><td>
/K</td><td>

**yes**</td><td>

When printing a folder listing to a printer, or as a plain-text file, column widths will be auto-calculated to fit their contents.

*Example:* `Print FOLDER "Brother HL-4050CDN" AUTOSIZECOLUMNS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Columns will not be autosized - instead the widths from the folder format will be used.

*Example:* `Print FOLDER TO /desktop/dir.txt AS=txt AUTOSIZECOLUMNS=no`
</td></tr><tr><td>
CALCSIZES</td><td>
/K</td><td>

**yes**</td><td>

Calculate folder sizes when printing a folder.

*Example:* `Print FOLDER TO clip CALCSIZES=yes QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not calculate folder sizes.

*Example:* `Print FOLDER TO clip CALCSIZES=no QUIET`
</td></tr><tr><td>
DEFAULTLIST</td><td>
/S</td><td>

*(no value)*</td><td>

Displays a generated list of installed printers (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). You can use this list to change the default printer, and right-click the items in the list to display the printer's context menu. You can also print a file by dropping it on the generated button for a printer.

*Example:* `Print DEFAULTLIST`
</td></tr><tr><td>
ENCODING</td><td>
/K</td><td>

**ansi**</td><td>

When printing a folder listing to a file, specifies that **ANSI** encoding should be used. This is the default encoding type initially, but if the *Print Folder* dialog is used in interactive mode it will remember the last encoding type manually selected. Using this argument lets you override the last used encoding type.

*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=ansi QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**utf8**</td><td>

Sets the encoding type to **UTF8** with a BOM (Byte Order Mark).

*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=bom QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**utf8nobom**</td><td>

Sets the encoding type to **UTF8** without a BOM.

*Example:* `PRINT FOLDER TO /desktop/dirprint.txt ENCODING=utf8nobom`
</td></tr><tr><td>
FILTER</td><td>
/K</td><td>

*\<filter\>*</td><td>

Use a [filter](/Manual/file_operations/filtered_operations/README.md) when printing the contents of sub-folders (via the **FLATVIEW** argument). This can be the name of a filter you have previously created via the **[File Operations / Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences, or it can be a simple [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to filter by filename.

*Example:* `Print FOLDER FILTER \*.jpg FLATVIEW=nofolders QUIET`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to filter the contents of sub-folders when printing folder contents. This is similar to the **FILTER** argument, however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `Print FOLDER FLATVIEW=nofolders QUIET FILTERDEF name match \*.zip and size match \> 2 mb`
</td></tr><tr><td>
FLATVIEW</td><td>
/K</td><td>

**no**</td><td>

Do not print the contents of sub-folders when printing a folder listing.

*Example:* `Print FOLDER FLATVIEW=no QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

Prints the contents of sub-folders in "mixed" mode. This mixes files and folders together in a flat list.

*Example:* `Print FOLDER FLATVIEW=mixed TO clip QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**nofolders**</td><td>

Prints the contents of sub-folders in "mixed - no folders mode". All files from sub-folders are listed, but the folders themselves are not shown.

*Example:* `Print FOLDER FLATVIEW=nofolders QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**grouped**</td><td>

Prints the contents of sub-folders in "grouped" mode. Files and folders are indented to reflect the tree hierarchy.

*Example:* `Print FOLDER TO /desktop/dirtree.txt FLATVIEW=grouped QUIET`
</td></tr><tr><td>
FOLDER</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **[Print Folder](/Manual/additional_functionality/print_folder.md)** dialog, which lets you print or export the contents of the current folder displayed in the Lister.

*Example:* `Print FOLDER`
</td></tr><tr><td>
</td><td>
</td><td>

**selected**</td><td>

Only selected files in the current folder will be printed by the Print Folder function.

*Example:* `Print FOLDER=selected`
</td></tr><tr><td>
</td><td>
</td><td>

*\<path\>*</td><td>

Specify the folder path to print.

*Example:* `Print FOLDER /desktop TO clip QUIET`
</td></tr><tr><td>
FONT</td><td>
/K</td><td>

*\<name\>,\<size\>*</td><td>

Specify the font to use when printing to the printer.

*Example:* `Print FOLDER FONT Arial,20 QUIET`
</td></tr><tr><td>
FORMAT</td><td>
/K</td><td>

*\<format name\>*</td><td>

Use the specified favorite folder format to control the columns, sort order, and similar details of the printed information.

The named format must first have been created from the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** page in Preferences.

*Example:* `Print FOLDER FORMAT="My Format" QUIET`

The **FORMAT** argument also accepts the following special keywords:

- **!current**: Use the file display's current format, including any ad-hoc edits made to it.
- **!default**: Use the Folder Type format applicable to current folder. For example, **Network Drives** if it's a network drive.
- **!factory**: Use the hardcoded factory-default format.
- **!folder**: Use the format for the current folder. This is generally the format you would get when opening the current folder in a new window.
- **!user**: Use the **User Default** format.

*Example:* `Print FOLDER FORMAT=!current QUIET`
</td></tr><tr><td>
HEADER</td><td>
/K</td><td>

**top**</td><td>

Print a header at the top of each page (or when printing to disk or the clipboard, at the top of the listing).

*Example:* `Print FOLDER HEADER=top QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

Print a footer at the bottom of each page (or the bottom of the listing).

*Example:* `Print FOLDER HEADER=bottom QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Print both a header and a footer.

*Example:* `Print FOLDER HEADER=both QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Do not print a header or a footer.

*Example:* `Print FOLDER HEADER=none QUIET`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Print DEFAULTLIST HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Print DEFAULTLIST HEADING="Default Printer"`
</td></tr><tr><td>
KEYWORDS</td><td>
/S</td><td>

*(no value)*</td><td>

When printing a folder listing, the headings for each column will show keywords (sometimes called "raw names") instead of display names. Keywords uniquely identify each column and do not vary by language, while display names are translated and may not be unique.

*Example:* `Print FOLDER AS=csv TO=clip FLATVIEW=no QUIET KEYWORDS`
</td></tr><tr><td>
NOWIZARD</td><td>
/S</td><td>

*(no value)*</td><td>

Bypass the Windows Photo Printing Wizard for image files; Opus can natively print any image format that it is able to view.

*Example:* `Print NOWIZARD`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(no value)*</td><td>

Print the folder using the specified options without displaying the *Print Folder* dialog first.

*Example:* `Print FOLDER QUIET`
</td></tr><tr><td>
SETDEFAULT</td><td>
/K</td><td>

*\<printer name\>*</td><td>

Set the named printer as the system default printer. The name you provide must be the full name of the printer as shown in the Printers Control Panel. Make sure you enclose the name in quotes if it contains a space.

*Example:* `Print SETDEFAULT "Brother HL-4050CDN"`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<printer name\>*</td><td>

Print selected files or folders to the specified printer (overriding the default printer). A button with this command can also accept files dropped on it to print them.

*Example:* `Print TO "Brother HL-4050CDN"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<file name\>*</td><td>

Print the folder contents to a specified disk file.

*Example:* `Print TO dirlist.txt FOLDER C:\Data QUIET AS txt`
</td></tr><tr><td>
</td><td>
</td><td>

**clip**</td><td>

Print the folder listing to the clipboard.

*Example:* `Print FOLDER TO clip AS csv`
</td></tr></tbody>
</table>

