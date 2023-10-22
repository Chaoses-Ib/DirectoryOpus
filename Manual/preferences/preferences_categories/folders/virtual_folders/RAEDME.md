# Virtual Folders

This section lets you configure how Opus handles certain [virtual folders](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.md). These are folders that do not relate to a physical location on a disk - that is, they can not be represented by a traditional path like *C:\Users\\* There are many virtual folders provided by Windows - some common examples are *My Computer* (or *Computer* under Windows 7), the *Desktop*, *Network* (used to be called *Network Neighborhood*) and so on. Third parties can also implement virtual folders via so-called "namespace shell extensions" - for example, your mobile phone may have come with software to access it through Explorer, and this would most likely be implemented as a virtual folder.

For most virtual folders, Opus provides a display of the folder by "hosting" Explorer within the file display. This lets you see the folder and interact with it in the same way as you would in Explorer itself (primarily via drag and drop, cut and paste, and context menus).

For the two most commonly used virtual folders - *Computer* and *Desktop* - Opus has the option of providing its own display (known as "native display") instead of hosting Explorer. The advantage of this is that then the full gamut of Opus functionality is available, including folder formats, configurable colors and images, and (for *Desktop*) Opus commands like Advanced Rename, etc. For the most part the Opus-provided displays of these folders will look exactly the same as the hosted form, so you may not even realise it is Opus and not Explorer providing the display.

The **Native display of the Desktop** option lets you enable or disable native display for the virtual Desktop folder. When native display is on, you can choose which desktop contents are included:

- **Documents / Profile folders**: Includes folders for your personal files. The actual folders vary depending on your OS version. For example, on Windows XP this will include the *My Documents* folder, on Windows 7 it will include your profile folder.
- **All Users / Shared Desktop contents**: Includes desktop files and folders from the *All Users* desktop. As well as the special folders like *Computer*, *Network*, etc, the desktop presents a merged view of two underlying disk folders, which is where files that you drop on the desktop are actually stored. One folder contains your own personal files, and the other contains files that are accessible to all users. This option lets you hide the All Users files, leaving only your own personal files displayed.
- **Computer**: Includes an item for the *Computer* virtual folder (the folder that displays your disk drives and network shares).
- **Collections**: Includes a link to the *File Collections* root folder (the folder that displays all your top-level [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md)).
- **Network**: Includes an item for the *Network* virtual folder (the folder that displays your local network).
- **Libraries**: Includes an item for the *Libraries* root folder (the folder that displays all your [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md)).
- **Recycle Bin**: Includes a link to the *Recycle Bin* folder.
- **FTP**: Includes an item for the *FTP* root folder (the folder that displays the top-level of your FTP Address Book).
- **Operating system files**: If this option is off, operating system files (those marked with the **H** and **S** attributes) will be hidden from the desktop. The desktop quite often contains two **desktop.ini** files (one in your personal desktop folder and one in the All Users folder) so being able to hide these is quite useful.
- **Control Panel**: Includes a link to the *Control Panel*. Note that in Vista and above, double-clicking this link will open Control Panel in Explorer.

The **Include additional folders when using Windows Search from the Desktop** option controls which folders are searched when you use Windows Search (e.g. via the search field in the top right of the Lister) from the Desktop folder. By default, Opus only searches your personal Desktop folder (**/desktopdir**) and, if configured to appear, the shared desktop folder (**/commondesktopdir**). If this option is turned on the search will include the profile and shared Desktop folders and also the Documents folder, and potentially others. (It is up to Windows exactly which folders are searched, and you'll see similar from Explorer.)

The **Native display of Computer** option similarly lets you enable or disable native display for the *Computer* (*My Computer*) folder. The options for this are:

- **Include "Files Stored on This Computer"**: This option adds a group to the Computer display which contains links to the document folders on this machine (your own personal folder, and the shared documents folder). This option is provided for compatibility with Windows XP's Explorer, which includes similar entries. Explorer in Vista and Windows 7 does not show these items in the Computer folder but in Opus you can enable them if desired.
- **Show empty disk drives**: If this option is turned off, removable disk drives will be hidden from the list of drives if they are empty.
- **Sort drives by name instead of letter**: By default drives are sorted by drive letter (C:, E:, L:, etc). If you turn this on, they will be sorted by their label.
- **Show drive labels as**: Lets you choose how drive labels are displayed.

You can configure the file display format for both these folders using the [Folder Formats](folder_formats/RAEDME.md) page - for *Desktop*, you would add a **Path Format**, and for *Computer*, use the item in the **System folders** category.

The bottom section of this dialog lets you control how Opus handles virtual folders that also have an underlying "real" disk folder behind them. Windows contains several folders like this - the *Desktop* is one, but others include the *Fonts* folder (usually *C:\Windows\Fonts*) and the *Global Assembly Cache* folder (usually *C:\Windows\Assembly*). These folders can be displayed in Opus in two different ways - as the underlying disk folder, in which case you will see all files in that folder, or as a virtual folder, in which case you will see the virtualized view that Windows provides.

![](/Manual/images/media/fonts_-_virtual.png) ![](/Manual/images/media/fonts_-_non_virtual.png)

The above screenshots show the difference between the virtualized and "real" views of the Fonts folder. You can choose from the following options:

- **Treat all "virtual filesystem folders" as virtual**: All such folders will be displayed in their virtualized forms.
- **Treat all virtual folders as real**: All such folders will be displayed as the real underlying folder. Note that this only applies to virtual folders that actually do have an underlying disk folder - some "purely virtual" folders like *Network Neighborhood* will always be virtual.
- **Treat the following virtual folders as real**: This option lets you specify exactly which folders should be displayed as real. For example, you could set the Fonts folder to always show as real but all other such folders will be displayed as virtual. Use the toolbar buttons to add (![](/Manual/images/media/favorites_-_add.png)) folders to the list, or remove (![](/Manual/images/media/favorites_-_delete.png)) existing folders.

- **Enable background images in virtual folders**: With this option on, Opus will try to use your background image settings when it is displaying a [virtual folder](virtual_folders/RAEDME.md) (e.g. Network Neighborhood). As these folders are provided by the operating system and Opus merely hosts them as a container, it won't necessarily work! Note that it isn't possible to change the text color in these folders, so this option isn't suitable for inverted color schemes.
- **Enable custom fonts in virtual folders**: With this option on, your choice of File Display font will be applied to [virtual folder](virtual_folders/RAEDME.md) in addition to the normal folders which Opus handles itself. Virtual folders are handled by Windows, or sometimes third-party components, and are largely outside of Opus's control. Opus can ask them to use a different font, but this can result in cosmetic issues or even crashes. If you run into problems using virtual folders, or when opening new windows or tabs, you should turn this option off again.

 
