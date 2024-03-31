# Selecting Files

Whenever you want to do something with a file (copy it, delete it, or just view it) you must select it first. Most file operations in Directory Opus operate on all currently selected files (and folders), so it's important to know how to select files, and how to tell how many files you have selected.

### Selecting files manually

See [Using the mouse or keyboard](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/README.md) for information on how to select files using the mouse or keyboard.

### Selecting files automatically

The internal [Select](/Manual/reference/command_reference/internal_commands/select.md) command lets you select files automatically in many different ways. The default **Edit** menu has a number of pre-defined **Select** commands:

- **Select All**: Select all items in the current folder.
- **Select by Pattern**: Displays a dialog that lets you select files using [simple wildcard patterns](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md). You can switch this dialog into an advanced mode that lets you select files using [multiple different criteria](/Manual/basic_concepts/selecting_files/advanced_selection.md).
- **Invert Selection**: Inverts the selection state of all items in the folder.

Even more commands are available in the **Edit / Select Other** sub-menu:

- **Reselect Files**: Select all files that were used (and deselected) by the previously executed command.
- **Select Same Extensions**: Selects all files with the same extensions as the currently selected files (e.g. select one **.txt** file and then use this command to automatically select all other **.txt** files.)
- **Select Empty Folders**: Selects all folders that have nothing in them at all.
- **Select Zero-Byte Folders**: Selects folders that have zero bytes in them (i.e. they're not empty - they may contain sub-folders or zero byte files.)
- **Select Expanded Folder Items**: Selects items that are inside [expanded folders](/Manual/basic_concepts/expandable_folders.md).
- **Select Source to Destination**: Select files in the destination with the same names as the files currently selected in the source.
- **Select Source All to Destination**: Select files in the destination with the same names as the files in the source (they don't need to be selected.)
- **Select Source All to Destination (ignore extensions)**: Select files in the destination with the same names as the files in the source (ignoring file extensions).
- **Select Source-not-in-Destination**: Select those files in the source which do not exist in the destination.
- **Selection to Checkboxes**: Set the checkbox state to match the current selection. The file display will be set to [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) if it isn't already.
- **Checkboxes to Selection**: Set the selection to match the checkbox state.
- **Select Duplicates...**: Displays the selection dialog for the [duplicate file finder](/Manual/additional_functionality/duplicate_file_finder.md).

### Counts shown on the status bar

The easiest way to tell how many files and folders are currently selected is to look in the [status bar](the_lister/status_bar.md).

![](/Manual/images/media/13/status_bar_1.png)

The status bar shows you the number of files and folders selected (and the total number) in the current file display. Whenever you click a button like **Copy Files** or **Delete**, it's these selected files that will be used in the function.

More:

[Selecting with the mouse and keyboard](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/README.md)  
[Simple Wildcard Selection](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md)  
[Advanced Selection](/Manual/basic_concepts/selecting_files/advanced_selection.md)  
