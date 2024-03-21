# File Types

File types are the set of registered types that are used to group files by file extension, throughout the system. For example, all files that end with **.txt** are said to be of type **Text Document**. The type of a file is displayed (by default) in the **Type** column in a Lister. Opus lets you configure a number of different settings on a per file-type basis. Actions such as double-clicking a file, or the display of tooltips for a file, can be different for different types of file.

Opus also extends the file types concept with the addition of [File Type Groups](/Manual/file_types/file_type_groups.md), which let you define a group of file types and then configure things for the group as a whole. So instead of having to add the same context menu item manually for each type of image file, you can add it to the **Images** group and it will automatically appear for all file types in that group. Groups are also used by the [Content Types](basic_concepts/folder_options/content_types.md) system; for each group you can define a folder format (sort order, view mode, etc) which is then automatically applied whenever you navigate to a folder containing mostly files that belong to that group (so for example, the display can automatically switch to thumbnails mode when you navigate to a folder containing mostly images).

The things that can be configured through the file types system are:

- [Standard file type parameters](/Manual/file_types/filetype_editor/README.md) like icon, description, the MIME type (if any) and the extensions assigned to the file type.
- **[Actions](/Manual/file_types/filetype_editor/actions.md)**: What happens when certain actions are performed on the file. Actions include standard context menu commands like explore, find, print, etc.
- **[Events](/Manual/file_types/filetype_editor/events.md)**: Lets you define what happens when certain mouse-based events occur on the file. For example, double-clicking a file can do something different based on whether the Shift key is held down or not. You can also define a command that is run when a particular type of file is dragged and dropped.
- **[Context Menu](/Manual/file_types/filetype_editor/context_menu.md)**: You can add commands to the context menu (right-click menu) for files or folders.
- **[Drop Menu](/Manual/file_types/filetype_editor/drop_menu.md)**: You can also add commands to the drop menu (the menu you get if you drag a file with the right mouse button and drop it).
- **[Info Tip](/Manual/file_types/filetype_editor/info_tip.md)**: You can define the appearance of info tips (the tool tip that's displayed when the mouse hovers over a file) on a per file-type basis. For example, image files can display a thumbnail in their popup tooltip.
- **[Tiles Mode](/Manual/file_types/filetype_editor/tiles_mode.md)**: You can also define how files will appear (what information they display) when the file display is in tiles mode.

![](/Manual/images/media/file_types.png) 

The File Types dialogs are accessed via **Settings / File Types** in the default menus.

The main File Types dialog displays a list of all registered file extensions, their description, and the group they are assigned to if any. In the above screenshot you can see that **.JPE**, **.JPEG** and **.JPG** are all part of the **JPEG Image** file type, and are also assigned to the **Images** group. You can change the group that a file type is assigned to by moving the mouse over the **Group** column - a drop-down control will appear that lets you pick the group.

The **New** drop-down is used to create a new file type or group. The **Copy** button lets you duplicate an existing file type, and the **Delete** button lets you delete it.

You can locate file types using the **Find** function, which lets you search by extension, descriptions and other properties. You can also quickly jump to a file extension by activating the file type list and typing the extension in.

The area at the bottom of the dialog displays information for the currently selected file type including its "default handler" (*Opens with: Directory Opus Viewer* in the above screenshot). The default handler is the program that will (normally) be used to open the file when it's double-clicked - you can change this, and also edit the items shown on the [Open With](/Manual/file_types/the_open_with_editor.md) menu for a file type, using the **Change** button.

One thing to be aware of is that the file types system in Opus is shared with the rest of the system. For any given file type there are a number of different classes of settings:

- ![](/anchor/global/)**Global**: The definition of file extensions and types, information set for file types (icons, descriptions, Opens with, etc) will all be used by Windows and reflected by other programs in the system. Changing these in Opus will also change these parameters throughout the system.
- ![](/anchor/mixed/)**Mixed**: Some things you change in Opus can affect either Opus only, or the whole system, on a case-by-case basis. For example, you can add context menus that appear in Explorer as well as Opus, but you can also add context menus that only appear in Opus.
- ![](/anchor/opusonly/)**Opus-only**: Some things Opus lets you change only affect the behavior in Opus. For example, the **Events** tab in the file type editor which let you override the behavior when a file is double-clicked only affects Opus. So it's quite possible to configure a file to open with one program when double-clicked in Explorer and another when double-clicked in Opus.

Use the **Edit** button at the bottom of the dialog to display the [File Type Editor](/Manual/file_types/filetype_editor/README.md) for the currently selected file type.

More:

[Directory Opus File Types](/Manual/file_types/directory_opus_file_types.md)  
[File Type Groups](/Manual/file_types/file_type_groups.md)  
[The Open With editor](/Manual/file_types/the_open_with_editor.md)  
[Filetype Editor](/Manual/file_types/filetype_editor/README.md)  
