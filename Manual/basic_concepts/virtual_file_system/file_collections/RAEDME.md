# File Collections

A file collection is a virtual folder that acts as a container for other files and folders. The items in a file collection do not need to be stored in the same physical folder - they can reside in other folders, on other disks, or even in other [virtual file systems](/Manual/basic_concepts/virtual_file_system/RAEDME.md) like FTP. When you add items to a collection they are not actually moved or modified at all - all Opus stores is a reference to the original file.

![](/Manual/images/media/coll_search.png)

File collections are used by the **[Find Files](../searching_and_filtering/find_files/RAEDME.md)** and **[Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md)** functions to display the results of the search. When you perform a search with these tools, any matching files are automatically added to the specified file collection. You can see an example of this in the above screenshot - a search for image files returned pictures stored in two different locations, but in the results collection they are presented as if they were all in the same place.

You can work with the files in a file collection (copy them, rename them, delete them, etc.) just like you would with the real files. Collections are also used by the [Flickr photo-sharing synchronization](/Manual/additional_functionality/flickr_synchronization.md) system to store references to your photos no matter where on your system they are physically located.

The root **File Collections** folder contains all your file collections (you can't add items to the root itself). To access the file collections root you can:

- Click on the **File Collections** item in the folder tree (unless you have disabled this from the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/folder_tree_contents.md)** page in Preferences)
- Double-click on the **File Collections** item on the Desktop (unless this has been disabled on the **[Folders / Virtual Folders](/Manual/preferences/preferences_categories/folders/virtual_folders/RAEDME.md)** Preferences page)
- Select the **File Collections** command from the drop-down menu attached to the Up button on the [File Display Toolbar](../the_lister/toolbars/the_default_toolbars/file_display_toolbar.md) (the ![](/Manual/images/media/location_toolbar_-_up.png) button on the toolbar - right-click it or click-and-hold with the left button to show the menu)
- Click in the [location field](../the_lister/navigation/breadcrumbs_location_field.md) and enter the path **coll://** (see below for more information about this path format)

From the file collections root you can use the **New Folder** function on the toolbar to create a new collection. You can also create sub-collections in the same way - simply navigate to the parent collection and create a new folder like normal. You can assign your own icon to a file collection through its Properties dialog - you can also assign a description string if desired.

You can also define the default format for collections - this comes pre-configured to add the **Location **column whenever you navigate to a collection. This column is useful as it displays the real location of the items in the collection.

The **[File Types](/Manual/file_types/RAEDME.md)** dialog can be used to add commands to the context menu for items in collections. Two commands are pre-defined; **Remove from Collection** (mentioned above), and **Open Containing Folder**. The latter command uses the **[Go OPENCONTAINER](/Manual/reference/command_reference/internal_commands/go.md)** function to open the real folder that contains the selected collection item.

File collections are referenced internally using a URL-style path format, with the **coll://** prefix. For example, the path of the default find results collection is **coll://Find Results/**. You can type this sort of path into the location field, or use it in buttons and hotkeys with the internal command set to automate your use of collections. For example, say you had a collection called **FavePhotos** you use often to keep track of your favorite photos. Whenever you have an image that you want to add to it, you could expand the **File Collections** branch in the tree, locate your collection, then click and drag the image and drop it on the collection folder. If you're doing that often though, there's a much quicker way - you could [set up a button or hotkey](/Manual/customize/creating_your_own_buttons/RAEDME.md) to automatically add the selected files to that collection, using the raw **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command.

![](/Manual/images/media/coll_faves_hotkey.png) 

This screenshot illustrates an example hotkey that performs this function. Now all you would need to do is select the photos you want to keep, press **Ctrl+Shift+P**, and the files would be automatically added to the **FavePhotos** file collection.

Unfortunately the file collections system is only available within Directory Opus - you can't access your collections from other programs or from Explorer. However there are a couple of options on the **[Miscellaneous / Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/RAEDME.md)** page in Preferences that let you integrate collections more tightly into the system:

- **Add File Collections icon to the Desktop**: If this option is enabled Opus will place an icon on your desktop that represents the root file collections folder; double-clicking it will open a Lister showing your file collections.
- **Add File Collections list to the Send To menu**: This option causes Opus to add links for your file collections to the *Send To* menu (the menu that is displayed when you right-click a file and select *Send to* from its context menu). This lets you add items to file collections from outside of Opus.

The **[DOpusRT](/Manual/reference/dopusrt_reference/RAEDME.md)** command can also be used from outside of Opus to access and manipulate file collections - see **[External Manipulation of File Collections](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.md)** for more information.

More:

[Stored Queries](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)  
