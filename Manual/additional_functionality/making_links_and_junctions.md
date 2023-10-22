# Making Links and Junctions

A link in general terms is a file or folder that points, or redirects to another file or folder. Windows supports four distinct types of link:

- **Shortcuts**: The ones you're probably most familiar with, these are implemented as a separate .lnk file (although the file extension is often hidden), that stores the details of the file or folder it points to. Shortcuts can refer to a file or folder on any drive, including on a network share.
- **Hard links**: Hard links can only point to a file. They are implemented at the file system level. Technically speaking, all files are "hard links" - there's no concept of an original file. Once a link has been created, there is no way to tell which one is older. A file is only deleted when the last hard link that points to it is deleted. Hard links can only be created on the same drive partition as the original file.
- **Junctions**: Junctions can only point to a folder. They are implemented at the file system level.
- **Soft links**: Soft links are only available in Vista and later. A soft link can point to either a file or a folder, and they are able to span hard drives. Creating a soft link requires administrator permissions - Opus will display a [UAC](/Manual/file_operations/uac_and_administrator_mode.md) prompt if needed. Soft links can be *absolute* or *relative*.

Note that hard links, soft links and junctions are only supported on NTFS-formatted drives. 

Windows (particularly in Vista and above) uses links and junctions quite a lot. If you turn off the **Hide protected operating system files** option on the **[Folders / Global Filters](/Manual/preferences/preferences_categories/folders/global_filters.md)** page in Preferences, you will notice several folders appear in red in various locations (the root of *C:* for one, and your user profile folder). Microsoft uses these hidden junctions to maintain backwards compatibility with software that has hard-coded the names of legacy paths. For example, in Windows XP, user data is stored in *C:\Documents and Settings*, but in Vista and above it's in *C:\Users*. By default Windows creates a hidden junction called *Documents and Settings* that points to the new *User* folder, so that software that specifically references the old path will still operate.

![](/Manual/images/media/junction_targets.png) 

If you turn on the **Description** column in a Lister you can see the target of links and junctions. See the [Folder Options](/Manual/basic_concepts/folder_options/RAEDME.md) section for information on adding columns to the display.

Opus is able to create all these types of links for you. Creating a shortcut is the simplest, and you can do this in Opus just as you can in Explorer, either by:

- Dragging and dropping an item with the right mouse button. The popup menu will contain a **Create Shortcut Here** command.
- Copying a file or folder to the clipboard, and then right-clicking in a folder and choosing the **Paste Shortcut** command from the context menu.

Aside from basic shortcuts, other types of links and junctions are generally used only rarely and by experienced users (at least on Windows). If you are not familiar with how they work, be careful and test with copies of both target and source folders first. Be aware that most actions in most software are not "link aware". For example, be careful when deleting or overwriting links that you are not deleting or overwriting the things they point to, unless that is your intention. Test how the things behave first before risking important data!

Commands to create the other types of links and junctions can be found in the default toolbars under the **Copy Files** button's menu, within the **Create Advanced Links** sub-menu:

![](/Manual/images/media/makinglinks_menu.png)

Like the main **Copy Files** button itself, the menu items work between dual file displays, taking the selected items in the source folder and creating junctions or links in the destination folder which point to them.

Behind the default menu items is the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command, which is used to create shortcuts as well as the other types of links. For example, you the command to create a button or menu item to create soft links in the destination folder to selected files in the source is: **Copy MAKELINK=softlink**.

When creating soft links, there are two ways the target of the link can be stored:

- *Absolute* links store the entire path name of the link target. Absolute links can reference files or folders on different drives as well as the same drive.
- *Relative* links store the path of the target relative to the location the link is created. For example, consider the following:  
  \* **Link path**: *C:\Test\Folder\Link.txt*
  - **Target path**: *C:\Test\Original.txt*  
    Creating *Link.txt* as a relative link would store the target path as *..\Original.txt* - the **..** notation indicates the parent folder. The advantage of a relative link is the common parent folder (in this example, *C:\Test*) can be renamed or moved, and the link will still work. Relative links are created using the **Copy MAKELINK=relsoftlink** command. If the target path can not be expressed relative to the link path then a regular, absolute link will be created instead.

See the documentation on the **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command for more information, and the [Customize](/Manual/customize/RAEDME.md) section for information on how to configure buttons and hotkeys. You may also like to see the File Types [Drop Menu](/Manual/file_types/filetype_editor/drop_menu.md) page - it's possible to add commands to the drag-and-drop menu, and you could, for example, add a **Create Softlink** command to go along with the **Create Shortcut** command that already appears on this menu.

![](/Manual/images/media/drop_menu_-_results.png)
