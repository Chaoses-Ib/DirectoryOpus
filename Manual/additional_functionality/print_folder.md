# Print Folder

The Print Folder function lets you print a listing of the contents of a directory. As well as printing to a printer, it can also print to a file or to the clipboard. In these cases you can choose from various export formats (plain text, tab separated or comma separated) which would then let you import the listing into a program like Excel.

To access the Print Folder dialog, select the **Print / Export Folder Listing** command from the **Tools** menu.

![](/Manual/images/media/print_folder.png) 

The Print Folder dialog is divided into three sections; **Source** (specifies which folder to print), **Destination** (specifies where to print or export it to) and **Format** (specifies the information to be included in the output).

The **Source** section contains the following options:

- **Folder**: Specifies the folder that you want to print the contents of. When you run the Print Folder command this will default to the current folder shown in the file display, but you can change this using the **Browse** button.
- **Calculate sub-folder sizes**: Select this option if you want the total sizes of any folders in the listing to be calculated. If turned off, folder sizes will not be displayed. This option also controls whether columns like *File count* and *Sub-folder count* work when added to the **Format** section of the **Print Folder** dialog. Any columns that require recursively enumerating the contents of folders will only work as expected if the **Calculate sub-folder sizes** option is switched on.
- **Flat View**: Similar to the Lister's **[Flat View](/Manual/basic_concepts/flat_view.md)** mode, this lets you print the contents of sub-folders as well as the selected folder. The drop-down lets you pick the following modes:
  - **Mixed**: The contents of all sub-folders (and their sub-folders, and so on) are shown on the parent level, as if the directory tree was just one big folder.
  - **Mixed (No Folders)**: The same as **Mixed**, but only files are included in the listing, not folders.
  - **Grouped**: Prints the folder as a nested tree structure. The contents of sub-folders will be shown indented from their parents.

- **Use filter**: Lets you specify a filter to control which files and folders are included in the listing. You can either enter a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) directly, select a [pre-configured filter](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md) from the drop-down, or click the **Define** button to [define a new filter](/Manual/file_operations/filtered_operations/README.md).

The **Destination** section specifies where you want the folder listing to go.

- **Printer**: The folder listing will be printed to the selected printer. The drop-down shows a list of your installed printers, and the **Setup** button lets you configure the printer properties.
- **File**: The folder listing will be saved to a file. Click the **Browse** button to specify the output filename (or enter it manually in the field). The file extension (or option you choose for the **Save as type** drop-down in the browse dialog) defines the format of the file that's exported. You can choose from the following formats:
  - **Text File**: Exports the folder listing to a plain text (**.txt**) file.
  - **Comma-Separated List**: Exports the folder listing to a comma-separated (**.csv**) file. This can then be imported into a program like Excel for further processing.
  - **Tab-Separated List**: An alternative to **.csv**, this format can also be imported into Excel and similar software.

- **Clipboard**: The folder listing will be placed on the clipboard, and you can then paste it into another program as in any copy/paste operation. The **Clipboard** drop-down lets you pick from the same formats as the **File** option above.

The **Format** section defines the format of the print-out, including which columns are included in the listing.

- **Edit**: Click the **Edit** button to edit the folder format used for the print out. This displays a standard [folder options](/Manual/basic_concepts/folder_options/README.md)-type dialog that lets you select columns, configure display and sorting options, etc.
- **Current**: The Print Folder dialog remembers its format from use to use. The **Current** button lets you update the format settings in the Print Folder dialog with those from the file display that you launched the Print Folder command from. So if you have a specific folder format set in a file display and want to print a list that looks the same, you could click the **Current** button to avoid having to reconfigure the Print Folder format manually.
- **Reset**: This resets the format to the one that was set when the Print Folder dialog was invoked. This lets you undo any changes you have made to the format (or if you accidentally clicked the **Current** button, etc).
- **Font**: This command lets you pick the font that's used to print the listing. The font is only used when printing to a printer; when exporting to a file or the clipboard, the font setting is ignored.
- **Column widths**: The Print Folder dialog displays a "preview" of the columns that have been specified in the format for printing. This lets you control how wide each column is, by clicking on the separators between the header items and dragging them to resize. The specified column widths are used when outputting to a printer and when sending the results to a text file or the clipboard using the 'Normal' format. (The widths are ignored when using the Comma-Separated or Tab-Separated output formats.)  
  ![](/Manual/images/media/print_folder_-_widths.png)  
  Below the header are two rows of information; the first row displays the widths of each column, and the second row displays the total width.  
  When printing, the widths are expressed in "nominal characters" (an average character width calculated from the specified font) and you can use them as a guide to make sure your folder listing will fit horizontally across the page.  
  When outputting to a text file or the clipboard using the 'Normal' format, the widths are the number of fixed-width characters used for each column, and will be rounded up to a multiple of 8 characters (to match the tab stops in most text editors).
- **Header/Footer**: This option lets you enable a header, a footer, or both. The header and footer show the name of the folder being printed and the current date and time. If printing to a printer, the header and footer are printed to each page. If printing to a file, the header is printed once, at the start of the file, and the footer is printed once at the end.
