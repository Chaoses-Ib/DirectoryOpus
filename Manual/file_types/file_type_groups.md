# File Type Groups

File type groups let you create pseudo file-types that contain multiple file extensions. Changes that you make to a file type group (like adding a context menu) are automatically reflected for all files that belong to that group. For example, the **Images** group by default adds a context menu command called **Convert Image** which invokes the [Image Conversion](/Manual/additional_functionality/image_conversion/RAEDME.md) tool. This command will be displayed on the context menu for all files that belong to the **Images** group.

![](/Manual/images/media/groups.png)

  
You can add your own groups, and a number of groups are defined by default:

- **Archives**: Represents the archive formats that Opus supports (**.zip**, **.7z**, etc). If you enable or disable support for individual formats through the **[Archive and VFS Plugins](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.md)** Preferences page, their file extensions will automatically be added to or removed from this group.
- **Documents**: Contains various common document formats (**.doc**, **.xls**, **.mdb**, etc.)
- **Images**: Contains various common image formats (**.bmp**, **.gif**, **.jpg**, etc.)
- **Movies**: Contains common movie file extensions (**.avi**, **.wmv**, **.mpg**, etc.)
- **Music**: Contains various common music formats (**.mp3**, **.wav**, **.wma**, etc.)
- **Programs**: Contains executable file formats like **.exe** and **.dll**.

You can change the file extensions assigned to groups by [editing](filetype_editor/RAEDME.md) them like normal file types. At any time you can reset one of the default groups by right-clicking its entry in the list and choosing the **Reset to Defaults** command from the context menu. You can also reset all of the default groups at once by right-clicking the **File Type Groups** header in the list.

The concept of groups is similar to that of file types themselves; they both refer to one or more file extensions. The difference (apart from groups being an Opus-only concept) is that a group contains file extensions for related classes of file whereas file types contain file extensions for the same type of file.

To explain briefly, consider the **JPEG Image** file type that is created by default on a Windows machine.

![](/Manual/images/media/filetypes_-_jpeg.png)

The **JPEG Image** file type has a number of file extensions assigned to it (**.jpe**, **.jpeg**, **.jpg** and **.jfif**) - but they all represent JPEG-format images. On the other hand, the **Images** group contains file extensions for multiple types of image file.

![](/Manual/images/media/groups_-_images.png) 

  
The **Images** group contains the JPEG file extensions, but it also contains file extensions for other formats of image file (**.bmp**, **.gif**, etc).

Groups are also used by the [Content Types](/Manual/basic_concepts/folder_options/content_types.md) system; for each group you can define a folder format (sort order, view mode, etc) which is then automatically applied whenever you navigate to a folder containing mostly files that belong to that group (so for example, the display can automatically switch to thumbnails mode when you navigate to a folder containing mostly images).
