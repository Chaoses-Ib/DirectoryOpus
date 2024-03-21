# Desktop

These options apply when Opus implements its own display for the *Desktop* folder. See [Virtual Folders](../virtual_folders/README.md) for more information.

- **Use the Opus implementation for the Desktop folder**: Lets you enable or disable native display for the virtual Desktop folder. When native display is on, you can choose which desktop contents are included.

You can configure the file display format for *Desktop* when the native display is enabled using the [Folder Formats](../folder_formats/README.md) page, by adding a **Path Format** for the desktop folder.

##### Desktop contents

- **All Users / Shared Desktop contents**: Includes desktop files and folders from the *All Users* desktop. As well as the special folders like *This PC*, *Network*, etc, the desktop presents a merged view of two underlying disk folders, which is where files that you drop on the desktop are actually stored. One folder contains your own personal files, and the other contains files that are accessible to all users. This option lets you hide the All Users files, leaving only your own personal files displayed.
- **Collections**: Includes a link to the *File Collections* root folder (the folder that displays all your top-level [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md)).
- **Control Panel**: Includes a shortcut to the *Control Panel*.
- **Cloud Storage (and folders added by other software)**: See [Special Folders](../special_folders.md) for more information. Folders that you select to show on the desktop will appear if this option is turned on.
- **Documents / Profile folders**: Includes folders for your personal files.
- **FTP**: Includes an item for the *FTP* root folder (the folder that displays the top-level of your FTP Address Book).
- **Libraries**: Includes an item for the *Libraries* root folder (the folder that displays all your [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md)).
- **Network**: Includes an item for the *Network* virtual folder (the folder that displays your local network).
- **Operating system files**: If this option is off, operating system files (those marked with the **H** and **S** attributes) will be hidden from the desktop. The desktop quite often contains two **desktop.ini** files (one in your personal desktop folder and one in the All Users folder) so being able to hide these is quite useful.
- **Recycle Bin**: Includes a link to the *Recycle Bin* folder.
- **This PC**: Includes an item for the *Computer* virtual folder (the folder that displays your disk drives and network shares).

##### Additional folders

The **Include additional folders when using Windows Search from the Desktop** option at the bottom of the page controls which folders are searched when you use Windows Search (e.g. via the search field in the top right of the Lister) from the Desktop folder. By default, Opus only searches your personal Desktop folder (**/desktopdir**) and, if configured to appear, the shared desktop folder (**/commondesktopdir**). If this option is turned on the search will include the profile and shared Desktop folders and also the Documents folder, and potentially others. (It is up to Windows exactly which folders are searched, and you'll see similar from Explorer.)
