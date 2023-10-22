# Folder Options Dialog

The Folder Options dialog can be accessed using the **Folder / Folder Options** command from the default **Menu** toolbar, or by right-clicking the file display column header and choosing **More**.

![](/Manual/images/media/folder_options_-_top_bit.png) 

The **Save Format** section at the top of the Folder Options dialog is a quick way to manage the stored folder format for the current folder. If you want to change an aspect of the display for a folder permanently there are two ways to do it; you can go into Preferences, to the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) page, and define a folder format for that folder. Or, using the Folder Options dialog, you can make the changes in real time and then save them to create a folder format automatically.

- **Save**: Use this to save the current folder options as the format for the current folder. See below for a discussion of the save options.
- **Clear**: Use this to remove a stored format for the current folder. The options on the **Clear** drop-down are:
  - **For This Folder**: If the current folder has a folder format defined, this option will let you remove it.
  - **For All Folders**: This option will remove all stored folder formats.

- **Reset**: Use this to quickly reset the current folder options to the default values. You can choose from **User default** (the user-configurable default format) or **Factory default** (the built-in folder options that can't be changed).

Selecting the **Save** button brings up the Save Folder Format dialog:

![](/Manual/images/media/image042.png)

  
There are three main options when saving a format:

- **Save format for a folder**: The format will be saved for one specific folder (by default, the one currently displayed in the file display - but you can use the up button (![](/Manual/images/media/favorites_-_up.png)) to save the format for a parent of the current folder if desired).

If you turn on the **Replace this folder’s format…** option ,  Opus will search through all your saved Lister layouts, saved folder tabs (and styles), and any currently open folder tabs for this folder, and update their format as well.  
The **Save for all sub-folders** option causes the **Use as the default format for all sub-folders** option to be turned on in the saved format.

- **Save format for all folders**: The format will be saved as the new *User Default* format, which is used for a folder that doesn’t have a specific folder format saved for it. If you turn on the **Clear any saved folder formats** option, and folders for which you’ve previously saved a specific format will be reset. And the **Replace the folder format…** option causes any saved layouts, tabs and styles to also have their formats reset.

- **Save a favorite format**: This lets you save the format as a favorite format (either a new one, or over the top of an existing favorite).

Below the **Save Format** section are six tabs which give you access to the various options that can be configured as part of the folder format.

- **[Columns](/Manual/basic_concepts/folder_options/folder_options_dialog/columns/RAEDME.md)**: Lets you choose which columns are displayed in the file display in details and power mode. The selection of columns also has an impact on other display modes, as you can only sort or group the list by a column that has been turned on.
- **[Display](/Manual/basic_concepts/folder_options/folder_options_dialog/display.md)**: Contains various options that affect the display of the file list (view mode, etc) and options that affect how the list is sorted (note that the actual sort field is specified on the Columns tab, however).
- **[Hide Filters / Show Filters](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.md)**: Let you filter the list by wildcard pattern or attributes.
- **[Options](/Manual/basic_concepts/folder_options/folder_options_dialog/options.md):** Contains miscellaneous options.
- **[Labels](/Manual/basic_concepts/folder_options/folder_options_dialog/labels.md)**: Lets you configure wildcard or filter [labels](/Manual/file_operations/labels.md) that only apply in this folder.

More:

[Columns](/Manual/basic_concepts/folder_options/folder_options_dialog/columns/RAEDME.md)  
[Display](/Manual/basic_concepts/folder_options/folder_options_dialog/display.md)  
[Filters](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.md)  
[Options](/Manual/basic_concepts/folder_options/folder_options_dialog/options.md)  
[Labels](/Manual/basic_concepts/folder_options/folder_options_dialog/labels.md)  
