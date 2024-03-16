# Libraries

Libraries are a concept introduced by Microsoft in Windows 7. A library is a virtual folder that displays the contents of other folders. Unlike a file collection, which can store references to individual files and folders, a library displays the entire contents of one or more folders. You can't add individual files to a library - all you can do is change which folders make up that library. You can work with the files in a library (copy them, rename them, delete them, etc.) just like you would with the real files.

##### Default libraries

By default four libraries are created by Windows - **Documents**, **Music**, **Pictures** and **Videos**. You can restore these default libraries at any time by right-clicking on the root Libraries folder and choosing the **Restore default libraries** command.

##### Library paths

Libraries are referenced internally using a URL-style path format, with the `lib://` prefix. For example, the path of the default pictures library is `lib://Pictures/`. You can type this sort of path into the location field, or use it in buttons and hotkeys with the internal command set to automate your use of collections. For example, you could [set up a button or hotkey](/Manual/customize/creating_your_own_buttons/RAEDME.md) to automatically navigate to the Pictures library using the raw command `Go lib://Pictures`.

The `lib://` path system isn't recognised outside of Opus, so if you ever want to copy a library path to the clipboard and paste it into another program, you should use the **Edit / Copy Other / Folder Path** menu command rather than copying the contents of the location field.

##### Libraries root folder

The root **Libraries** folder holds all your libraries. To access the libraries root you can:

- Click on the **Libraries** item in the folder tree (unless you have disabled this from the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/contents.md)** page in Preferences)
- Double-click on the **Libraries** item on the Desktop (unless this has been disabled on the **[Virtual Folders / Desktop](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.md)** Preferences page)
- Select **Libraries** from the drop-down menu in the [location field](../the_lister/navigation/breadcrumbs_location_field.md)
- Click in the [location field](../the_lister/navigation/breadcrumbs_location_field.md) and enter the path `lib://`

##### Creating a new library

From the libraries root you can use the **New Folder** function on the toolbar to create a new library.

Newly created libraries initially have no member folders, and so will appear empty - you need to use the *Properties* dialog to include one or more folders in the library in order to use them. Right-click on your newly created library and select the **Properties** command to display it.

##### Adding a folder to a library

The list of member folders is displayed in the **Library locations** list in the *Properties* dialog.

Click the **Include a folder** button to add a new member folder to the library. When you click **Apply** or **OK** the contents of the new member folder will instantly appear inside the library. To remove a member folder, select it in the list and click the **Remove** button.

You can also add a folder to a library from the folder's right-click context menu (using the **Include in library** sub-menu).

##### Default save location

Each library has a default location that new files are saved. If the library only has one member folder, that will always be the save location. If the library has more than one, the default save location is indicated with a checkmark in the *Properties* dialog. To change which member is the default save location, select it in the list and click the **Set save location** button.

##### The location column

When you navigate to a library, the file display shows the unified contents of all member folders. If your various member folders contain sub-folders or files with the same filename, it may not be obvious when looking at the library which item is which.

The **Location** column can help with this. It displays the true location of each item in the library, making it much easier to tell where they come from. You can add the **Location** column (and other columns) using the **[Folder Format](../folder_options/RAEDME.md)** dialog - or use the **[Folder Formats](../folder_options/folder_formats.md)** system to set the default format for a library.

##### Folder tree

If the **Show member folders individually** option on the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/contents.md)** page in Preferences is turned on, the folder tree will display an additional branch level for each member folder. This lets you use drag and drop to save new files into a specific member folder rather than the default save location.

You can hide an individual library from the tree by right-clicking it and selecting the **Don't show in navigation pane** option. To add it back to the tree, use the similarly-named option on the library's *Properties* dialog.
