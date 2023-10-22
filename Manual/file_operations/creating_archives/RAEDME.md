# Creating Archives

Opus supports multiple archive formats (Zip support is built-in, and support for other formats like 7zip and RAR is provided by means of a plugin). There are a number of ways to create an archive, but if you want a completely new, empty archive file, the easiest way is with the **New Archive** command in the **New Folder** dropdown menu.

![](/Manual/images/media/new_archive.png) 

This dialog works very much like the [New Folder](creating_folders.md) dialog. Enter the name of the archive (or accept the default name) and use the **Archive Type** drop-down to select the type of archive you want to create. The file extension of the new archive will change automatically to match the type of the archive you're creating.

The other options in this dialog are:

- **Create multiple archives**: Select this option if you want to be able to create more than one archive at once. If this is turned on you can enter multiple names in the name field, separated by commas.  
  ![](/Manual/images/media/multiple_archives.png)  
  The archives will all be created in the same location.
- **Read new archive automatically**: If this is selected the file display will automatically navigate into the new archive once it is created.
- **Open in dual display**: The new archive will be opened in the other file display (the Lister will be put into dual-display mode if needed). If you are creating multiple archives, only the first archive will be read.
- **Open in new Folder Tab**: The new archive will be opened in a new folder tab. If you are creating multiple archives a new tab will be created for each new archive. You can combine this option with the **Open in dual display** option to have the new tabs created in the other file display.  
  ![](/Manual/images/media/new_arc_-_tristate.png)  
  The **Open in new Folder Tab** option is a "tri-state" checkbox - it can be checked, unchecked, or in the "indeterminate" state. Normally when this option creates a new tab (or multiple tabs) the first new tab will be set to active automatically, but setting this option to the "indeterminate" state has the effect of not making the newly created tab active.

Once you've created a new archive, you can add files to it in several ways. Opus treats archives exactly like a folder; this means you can:

- Drag and drop files to it. If you have the display of archives in the folder tree enabled in [Preferences](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md) you can also drag and drop to archives in the tree.
- Copy files from one folder using the clipboard, then navigate to the archive and paste them in
- Open it in a dual-display and use the **[Copy Files](copying_moving_and_deleting_files/RAEDME.md)** function to copy files directly to the archive

The **New Archive** command creates an empty archive which you can then copy files into, but if you have one or more files that you want to add to a new archive, you can skip the **New Archive** step by using the [context menu items](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.md) that Opus can add. If turned on, right-clicking the files or folders will display one or more commands for [adding to a new archive](/Manual/file_operations/creating_archives/adding_to_archives.md).

More:

[Adding to Archives](/Manual/file_operations/creating_archives/adding_to_archives.md)  
[Add to Archive Dialog](/Manual/file_operations/creating_archives/add_to_archive_dialog/RAEDME.md)  
[Zip Files](/Manual/file_operations/creating_archives/zip_files/RAEDME.md)  
