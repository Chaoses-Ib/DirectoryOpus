# Folder Format Dialog

The Folder Format dialog can be accessed using the **Folder / Folder Format** command from the default **Menu** toolbar, or by right-clicking the file display column header and choosing **More**.

The six tabs at the top of the dialog give you access to the various options that can be configured as part of the folder format.

- **[Columns](/Manual/basic_concepts/folder_options/folder_options_dialog/columns/README.md)**: Lets you choose which columns are displayed in the file display in details and power mode. The selection of columns also has an impact on other display modes, as you can only sort the list by a column that has been turned on. You can configure column widths and sort order on this tab.
- **[Sorting](/Manual/basic_concepts/folder_options/folder_options_dialog/sorting.md)**: Options related to how the file list is sorted (other than which columns it's sorted by).
- **[Grouping](/Manual/basic_concepts/folder_options/folder_options_dialog/grouping.md)**: Options relating to how the file list is grouped.
- **[Display](/Manual/basic_concepts/folder_options/folder_options_dialog/display.md)**: Contains various options that affect the display of the file list (view mode, etc).
- **[Filters](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.md)**: The two filters tabs let you filter the list by wildcard pattern or attributes.

In some contexts the six tabs will have checkboxes which let you turn the individual pages on or off - for example, a saved format can override just part of the default format.

### Saving a folder format

The **Save** button at the bottom of the dialog is a quick way to manage the stored folder format for the current folder. If you want to change an aspect of the display for a folder permanently there are two ways to do it; you can go into Preferences, to the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md) page, and define a folder format for that folder. Or, using the Folder Format dialog, you can make the changes in real time and then save them to create a folder format automatically.

When you click **Save** the *Save Folder Format* dialog appears.

![](/Manual/images/media/13/save_format.png)

There are three main options when saving a format:

- **Save format for a folder**: The format will be saved for one specific folder (by default, the one currently displayed in the file display - but you can use the up button to save the format for a parent of the current folder if desired).
  If you turn on the **Replace this folder’s format…** option ,  Opus will search through all your saved Lister layouts, saved folder tabs (and styles), and any currently open folder tabs for this folder, and update their format as well. The **Save for all sub-folders** option causes the **Use as the default format for all sub-folders** option to be turned on in the saved format. 

- **Save format for all folders**: The format will be saved as the new *User Default* format, which is used for a folder that doesn’t have a specific folder format saved for it.
  If you turn on the **Clear any saved folder formats** option, and folders for which you’ve previously saved a specific format will be reset. And the **Replace the folder format…** option causes any saved layouts, tabs and styles to also have their formats reset.

- **Save a favorite format**: This lets you save the format as a favorite format (either a new one, or over the top of an existing favorite).
