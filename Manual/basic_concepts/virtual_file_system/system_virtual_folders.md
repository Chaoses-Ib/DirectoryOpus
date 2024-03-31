# System virtual folders

In Windows there are a number of virtual folders that are presented as being part of the file system (also known as *shell folders*). The *Desktop* folder is an example of a virtual folder. It is a folder that can contain real files (e.g. if you save a document to the desktop, it is stored in a real disk folder) but it also contains virtual items that don't correspond to a real file on a disk (for example, the desktop contains a link to the *Recycle Bin*, and to the *This PC* folder).

### Native implementation of some shell folders

Opus provides a native implementation of several virtual folders. This means that you can use Opus features like [Folder Formats](../folder_options/folder_formats.md), [Power mode](../the_lister/view_modes.md) or Preferences settings like [background images](/Manual/preferences/preferences_categories/colors_and_fonts/images.md) in some commonly used virtual folders. The virtual folders currently supported by Opus are:

- **Desktop**: Represents the contents of your desktop, and is nominally the root of the shell namespace. It displays the merged contents of two disk-based folders (your personal desktop folder, and the *All Users* desktop folder) as well as links to various virtual folders like Recycle Bin, Network, Libraries, etc. The native view provided by Opus can be configured from  the **[Virtual Folders / Desktop](/Manual/preferences/preferences_categories/folders/virtual_folders/desktop.md)** Preferences page - you can choose exactly which virtual folders are displayed on the Desktop.
- **This PC**: Displays the disk drives and devices installed in your system. By default empty disk drives (e.g. a DVD drive without a disc in it) are not displayed - you can change this from the **[Virtual Folders / This PC](/Manual/preferences/preferences_categories/folders/virtual_folders/this_pc.md)** Preferences page.
- **CD Burning**: Opus provides a native view of writeable CD and DVD disks when using the Windows CD burning system (with staged burning only - the LiveFS packet writing system is treated like a normal disk folder).

### Other shell folders are implemented by Explorer

When you navigate to a virtual folder other than the ones that Opus implements natively, the Lister acts as a container and hosts an instance of Explorer to provide the display. The advantage of doing this is that it lets you navigate the entirety of the shell namespace from within Opus, including any third-party *shell namespace extensions* you may have installed.

The disadvantage of hosting Explorer is that to Opus, the folder appears as a "black box". Opus literally has no idea what the contents of the folder are - even the display is provided by Explorer, with Opus doing no more than providing a place for Explorer to put its window. Therefore much of the native Opus functionality is unavailable in these virtual folders.

### Fully virtual or partly real?

Some virtual folders, like *Computer*, are purely virtual - they don't correspond to a real folder on disk.

Other folders, like the *C:\Windows\Fonts* directory, are real disk folders that have a virtual "overlay" when displayed in Explorer.

The options on the **[Virtual Folders / File System](/Manual/preferences/preferences_categories/folders/virtual_folders/file_system.md)** Preferences page let you control how Opus handles this sort of directory - if desired, you can choose to have Opus display the underlying "real" folder rather than the virtual presentation.
