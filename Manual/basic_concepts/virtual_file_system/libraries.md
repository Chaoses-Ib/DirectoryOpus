# Libraries

Libraries are a concept introduced by Microsoft in Windows 7. A library is a virtual folder that displays the contents of other folders. Unlike a file collection, which can store references to individual files and folders, a library displays the entire contents of one or more folders. You can't add individual files to a library - all you can do is change which folders make up that library. You can work with the files in a library (copy them, rename them, delete them, etc.) just like you would with the real files. Opus emulates the library system for Windows XP and Vista users - for these users, libraries won't be available in other programs like they are in Windows 7, but you can at least use them Opus.

By default four libraries are defined - **Documents**, **Music**, **Pictures** and **Videos**. Under Windows 7 the system sets these up; in the emulated libraries that Opus provides for earlier operating systems, Opus creates them automatically. In Microsoft's new model, the use of the old user profile folders like *My Documents* and *My Pictures* is discouraged - instead the corresponding libraries can be used instead. You can restore these default libraries at any time by right-clicking on the root Libraries folder and choosing the **Restore default libraries** command.

The root **Libraries** folder holds all your libraries. To access the libraries root you can:

- Click on the **Libraries** item in the folder tree (unless you have disabled this from the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences)
- Double-click on the **Libraries** item on the Desktop (unless this has been disabled on the **[Folders / Virtual Folders](/Manual/preferences/preferences_categories/folders/virtual_folders/RAEDME.md)** Preferences page)
- Select the **Libraries** command from the drop-down menu attached to the Up button on the [File Display Toolbar](../the_lister/toolbars/the_default_toolbars/file_display_toolbar.md) (the ![](/Manual/images/media/location_toolbar_-_up.png) button on the toolbar - right-click it or click-and-hold with the left button to show the menu)
- Click in the [location field](../the_lister/navigation/breadcrumbs_location_field.md) and enter the path **lib://** (see below for more information about this path format)

From the libraries root you can use the **New Folder** function on the toolbar to create a new library. Newly created libraries initially have no member folders, and so will appear empty - you need to include one or more folders in the library in order to use them. This is accomplished with the use of the **Properties** dialog - right-click on your newly created library and select the **Properties** command to display it.

![](/Manual/images/media/library_locations.png) 

The list of member folders is displayed in the **Library locations** list. Click the **Include a folder** button to add a new member folder to the library. When you click **Apply** or **OK** the contents of the new member folder will instantly appear inside the library. To remove a member folder, select it in the list and click the **Remove** button.

The checked member folder (**My Pictures** in the above screenshot) is the default *save location* for the library. This folder is used whenever you copy or move a file into the library (or in Windows 7, when you save a file to the library from another program). To change which member is the default save location, select it in the list and click the **Set save location** button.

On Windows 7 you can also add a folder to a library from the right-click context menu (using the **Include in library** sub-menu). This is not available on earlier operating systems by default, but if you like you can add it yourself using the **[File Types](/Manual/file_types/RAEDME.md)** system - all you need to do is add the command **Copy INCLUDEINLIBRARY** to the context menu for the ***All Folders*** file type.

When you navigate to a library, the file display shows the unified contents of all member folders. If your various member folders contain sub-folders or files with the same filename, it may not be obvious when looking at the library which item is which.

![](/Manual/images/media/libraries_1.png) 

The **Location** column can help with this. As you can see in the above screenshot, two of the **Documents** library's member folders contain a sub-folder called **Word Docs**. The **Location** column displays the true location of these folders, making it much easier to tell them apart. You can add the **Location** column (and other columns) using the **[Folder Options](../folder_options/RAEDME.md)** dialog - or use the **[Folder Formats](../folder_options/folder_formats.md)** system to set the default format for a library.

Another option that can make it easier to keep track of library members is the **Show member folders individually** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences.

![](/Manual/images/media/libraries_2.png) 

With this option turned on the folder tree (this doesn't affect the file display) will display an additional branch level for each member folder. As you can see from the above screenshot, this makes it obvious there are two separate **Word Docs** folders. You can also take advantage of this to copy files into a library member other than the default save location, by dragging and dropping it to the specific member folder.

You can hide an individual library from the tree by right-clicking it and turning off the **Show in Folder Tree** option. To add it back to the tree, use the similarly-named option on the library's **Properties** dialog.

Libraries are referenced internally using a URL-style path format, with the **lib://** prefix. For example, the path of the default Pictures library is **lib://Pictures/**. You can type this sort of path into the location field, or use it in buttons and hotkeys with the internal command set to automate your use of collections. For example, you could [set up a button or hotkey](/Manual/customize/creating_your_own_buttons/RAEDME.md) to automatically navigate to the Pictures library using the raw command **Go lib://Pictures**.

The **lib://** path system isn't recognised outside of Opus, even on Windows 7, so if you ever want to copy a library path to the clipboard and paste it into another program, you should use the **Edit / Copy Other / Folder Path** menu command rather than copying the contents of the location field.
