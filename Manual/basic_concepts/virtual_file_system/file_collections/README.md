# File Collections

A file collection is a virtual folder that acts as a container for other files and folders. The items in a file collection do not need to be stored in the same physical folder - they can reside in other folders, on other disks, or even in other [virtual file systems](/Manual/basic_concepts/virtual_file_system/README.md) like FTP. When you add items to a collection they are not actually moved or modified at all - all Opus stores is a reference to the original file.

### Collections are used for search results

File collections are used by the **[Quick Search](../searching_and_filtering/windows_search.md)**, **[Find Files](../searching_and_filtering/find_files/README.md)** and **[Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md)** functions to display the results of the search.

When you perform a search with these tools, any matching files are automatically added to the specified file collection.

You can save a quick search as a [stored query](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md) - a special type of file collection that regenerates its search results automatically whenever you navigate to the folder.

### Working with files in collections

You can work with the files in a file collection (copy them, rename them, delete them, etc.) just like you would with the real files.

> [!NOTE]
> When you delete a file in a collection, not only is it removed from the collection but the **real file** is deleted. To remove a file from a collection without deleting the real file, use the **Remove From Collection** command on the **Delete** drop-down menu.

### File collection paths

File collections are referenced internally using a URL-style path format, with the `coll://` prefix.

For example, the path of the default find results collection is `coll://Find Results/`.

You can type this sort of path into the location field, or use it in buttons and hotkeys with the internal command set to automate your use of collections. For example, the command `Copy TO "coll://Favorite Photos"` on a button would add any selected files to a collection called "Favorite Photos" automatically.

### File collections root folder

The file collections root folder contains all your top-level file collections (you can't add items to the root itself). To access the file collections root you can:

- Click on the **File Collections** item in the folder tree (unless you have disabled this from the **[Folder Tree / Contents](/Manual/preferences/preferences_categories/folder_tree/contents.md)** page in Preferences)
- Double-click on the **File Collections** item on the Desktop (unless this has been disabled on the **[Virtual Folders / Desktop](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.md)** Preferences page)
- Select **File Collections** item from the drop-down menu in the [location field](../the_lister/navigation/breadcrumbs_location_field.md)
- Click in the [location field](../the_lister/navigation/breadcrumbs_location_field.md) and enter the path `coll://`

### Making a new collection

From the file collections root you can use the **New Folder** function on the toolbar to create a new collection. You can assign your own icon to a file collection through its Properties dialog - you can also assign a description string if desired.

### Sub-collections

You can also have sub-collections, just like you can have sub-folders - simply navigate to the parent collection and create a new folder like normal.

### Folder format

You can define the default [folder format](../folder_options/README.md) for collections - this comes pre-configured to add the **Location **column whenever you navigate to a collection. This column is useful as it displays the real location of the items in the collection.

### Context menu for items in collections

The **[File Types](/Manual/file_types/README.md)** dialog can be used to add commands to the context menu for items in collections. Two commands are pre-defined; **Remove from Collection** (mentioned above), and **Open Containing Folder**. The latter command uses the `Go OPENCONTAINER` function to open the real folder that contains the selected collection item.

### Using collections outside of Opus

Unfortunately the file collections system is only available within Directory Opus - you can't access your collections from other programs or from Explorer. However there are a couple of options on the **[Miscellaneous / Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.md)** page in Preferences that let you integrate collections more tightly into the system:

- **Add File Collections icon to the Desktop**: If this option is enabled Opus will place an icon on your desktop that represents the root file collections folder; double-clicking it will open a Lister showing your file collections.
- **Add File Collections list to the Send To menu**: This option causes Opus to add links for your file collections to the *Send To* menu (the menu that is displayed when you right-click a file and select *Send to* from its context menu). This lets you add items to file collections from outside of Opus.

### Using file collections from external scripts

The **[DOpusRT](/Manual/reference/dopusrt_reference/README.md)** command can be used from outside of Opus to access and manipulate file collections - see **[External Manipulation of File Collections](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.md)** for more information.
