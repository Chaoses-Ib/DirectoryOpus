# Operations Toolbar

This toolbar contains commands relating to file and folder operations. The top-level buttons (**Copy Files**, etc) provide quick access to the most commonly used file functions, while the drop-down menus attached to those buttons contain more complicated or less-frequently used commands related to their parent button (so, for example, the drop-down menu for **Copy Files** contains **Copy As** and **Duplicate** commands as well).

Most of these buttons require one or more files or folders to be selected before they are available. They also generally use the [Source and Destination](/Manual/basic_concepts/source_and_destination.md) concept - the **Copy Files** button will copy all selected items from the current source file display to the destination. In a [dual-display](../../dual_display/README.md) Lister the destination is always the non-active file display. If no destination file display is available, Opus will prompt you to select a destination folder.

![](/Manual/images/media/13/operations_toolbar.png)

### Copy Files

The parent button will [copy](/Manual/file_operations/copying_moving_and_deleting_files/README.md) selected files and folders to the destination folder. The drop-down attached to this button contains the following additional commands:

- **Copy As**: This command lets you [provide new filenames](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for the copied files - either one at a time, or for all selected files as a batch using a wildcard.
- **Duplicate**: This command makes copies of the selected files in the current directory (that is, the files are duplicated in the same location, they are not copied to the destination). You must [provide new filenames](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for the duplicated files and folders.
- **Update All**: This command copies selected files to the destination if they either a) don't exist in the destination, or b) exist but are newer than those in the destination (see [Copying Updated Files](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.md) for more information).
- **Update Existing**: This command copies selected files to the destination only if they already exist but are newer than those in the destination (see [Copying Updated Files](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.md) for more information).
- **Send To**: This sub-menu contains the system ***Send To*** menu that lets you send selected files and folders to various destinations. Using this drop-down menu is equivalent to right-clicking on the file and selecting from the *Send To* context menu.
- **Copy Filter**: This command toggles the recursive [copy filter](/Manual/file_operations/filtered_operations/README.md) on or off in the current Lister.

### Move Files

The parent button will [move](/Manual/file_operations/copying_moving_and_deleting_files/README.md) selected files and folders to the destination. The drop-down menu contains the following additional commands:

- **Move As**: This command lets you [provide new filenames](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for the files as they are moved - either one at a time, or for all selected files as a batch using a wildcard.

### Rename

The parent command lets you rename selected files and folders using the **[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md)** dialog. The drop-down menu contains several examples of how the raw Rename command can be "scripted" to perform specialized renaming tasks:

- **Use Simple Rename**: Turn this on to make the **Rename** button trigger the simple Rename dialog (which only supports basic wildcard renames), rather than the Advanced Rename dialog.
- **Capitalize Words**: Capitalizes the first letter of each word in the filename, lower-cases all other letters.
- **Make Web-safe**: Makes filenames "safe" for use on websites, by removing any characters that can cause problems in URLs (anything other than `-`, `0-9`, `a-z`, `A-Z`, `.`, `_`, `]` and `+` is removed).
- **Number Files**: Inserts an incrementing number before the names of selected files. This function is implemented as a VBScript [rename script](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.md), and so provides a good example of a more complicated rename function.
- **Time-Stamp Names**: Appends a date- and time-stamp to the names of selected files.
- **Underscores to Spaces**: Replaces any underscores in filenames with spaces.

### New Folder

The parent command displays a dialog that lets you create a new folder in the active file display. If you are currently in the [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) root folder, a new collection will be created, and if you are currently in the [Libraries](/Manual/basic_concepts/virtual_file_system/libraries.md) root folder, a new library will be created. The drop-down menu contains the following additional commands:

- **New Archive**: This command [creates a new archive](/Manual/file_operations/creating_archives/README.md) (you will be prompted for the archive type and any options applicable to the archive format).
- **New Text Document**: This command creates a new empty text document (**.txt** file) in the current folder. This is equivalent to right-clicking on the file display background and choosing **New -\> Text Document** from the context menu.
- **New**: This sub-menu displays the system **New** menu, that lets you create new files of various types.
- **New Dated Folder**: Creates a new folder in the current file display with the current date and time as its name.
- **Move into Dated Folder**: Creates a new folder using the current date and time, and automatically moves any selected files and folders into it.

### Delete

The parent button will delete all selected files and folders. By default the recycle bin will be used to provide an undoable delete if possible, although this can be modified through [Preferences](/Manual/preferences/preferences_categories/file_operations/deleting_files.md). The following additional commands can be found in the attached drop-down menu:

- **Secure Wipe**: This command deletes all selected files using a [secure delete](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.md) algorithm, which makes it extremely difficult (if not impossible) for anyone to recover the deleted information.
- **Remove From Collection**: When used within a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), this command removes all selected items from that collection. If you use the parent **Delete** command on collection items, the real files and folders are deleted - use the **Remove** command to remove them from the collection without deleting the actual files.
- **Delete Filter**: This command toggles the recursive [delete filter](/Manual/file_operations/filtered_operations/README.md) on or off in the current Lister.

### Admin

This button turns on [Administrator Mode](/Manual/file_operations/uac_and_administrator_mode.md) in the current Lister.

### Archive Files

The parent command lets you add all selected files and folders to a [new archive](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.md) in the current folder (you will be prompted for the archive type and parameters). The drop-down menu contains the following additional commands:

- **Files to Separate Archives**: Adds all selected items to separate archives (one archive per selected file or folder). This command will create ZIP files by default; you can change the archive format used by editing the command (e.g. change **Copy ARCHIVE=single** to **Copy ARCHIVE=.7z,single** to use 7zip by default).
- **Files to Destination Archives**: This is the same as the parent **Archive Files** command except that the new archive will be created in the destination.
- **ZIP And Email Files**: Adds selected items to a ZIP archive and sends it via e-mail to a recipient (you will be prompted for the e-mail address).
- **Extract to Folders**: Extracts the contents of any selected archives to new folders named after the extracted archives (e.g. the contents of ***Pictures.zip*** would be extracted to a new folder called ***Pictures***).
- **Extract to Destination**: Extracts the contents of any selected archives to the destination folder.
- **Extract to Destination Folders**: Extracts the contents of any selected archives to new folders in the destination.

### Properties

The parent button displays the system Properties dialog for all selected items. The drop-down menu commands are:

      * **Attributes**: Displays the **[[:file_operations:changing_attributes|Change Attributes & Times]]** dialog which lets you modify the attributes and date/time-stamps of selected items. 
      * **Description**: Displays the **[[:file_operations:file_descriptions|Set Description]]** dialog that lets you assign a description string to selected items. 
      * **Edit Metadata**: Displays the **[[:file_operations:editing_metadata|Set Metadata]]** dialog that lets you edit the metadata for any selected files. 
      * **Set Label**: This sub-menu lets you assign a label to selected files and folders. Labelled files can be shown in different colors and/or font styles. Use the **[[:preferences:preferences_categories:labels:label_definitions|Label Definitions]]** page in Preferences to create and edit your labels.

### Slideshow

This button launches a [slideshow](/Manual/additional_functionality/viewing_images/README.md) of all selected image files. If no files are selected, all image files in the current folder will be displayed. The drop-down menu commands are:

      * **Show Pictures**: Displays selected files in the standalone viewer. 
      * **Play Sounds**: Plays selected files in the internal sound player.

### Help

The Help menu contains links to various useful web sites (the main [GP Software](http://www.gpsoft.com.au/) support site as well as the [Opus Resource Centre](http://resource.dopus.com/)), as well as a link to this help site itself and the check for updates function. It also has a **Secure Screenshot** command which lets you take screenshots of Opus with the names of potentially sensitive files obscured.
