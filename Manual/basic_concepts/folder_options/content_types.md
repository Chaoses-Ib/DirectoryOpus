# Content Types

The Content Types system lets you configure Opus to automatically change the display format for a folder based on the contents of that folder. For example, the display can automatically change to thumbnails mode whenever you navigate to a folder containing mostly images.

There are two distinct concepts that make up the Content Types system:

- **File Type Groups**: Content Types are built on the configured [file type groups](/Manual/file_types/file_type_groups.md). So you can have content type formats for Images, Music, etc. - any file type group that you create can have a content type format associated with it.
- **Folder Formats**: The [Folder Formats](folder_formats.md) system is used to define the display format that is applied for each file type group.

  
Because it can be confusing to have Opus change the folder format when you're not expecting it, you need to specifically enable the content types system in Preferences. The option is on the [Folders / Folder Behavior](/Manual/preferences/preferences_categories/folders/folder_behaviour.md) page, called **Enable Folder Content Type detection**. You can enable it for all folders or selectively based on the type of drive (local, network, etc.)

![](/Manual/images/media/enable_content_types.png)

Once the Content Type system is enabled, you can define the folder formats (what aspects of the folder display are changed, and what they're changed to) through the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) page in Preferences.

![](/Manual/images/media/content_type_formats.png)

The content type format can be enabled or disabled, and the actual format can be defined, for each configured file type group. On the **Options** tab for each content type format, the **Content threshold** setting lets you configure the percentage of files in a folder that must match the file type group for the content type format to be used. The **Consider subfolders when calculating content threshold** checkbox allows you to choose whether folders should be counted or ignored when considering the percentage of items in the folder.

![](/Manual/images/media/content_type_threshold.png) 

In the above screenshot, you can see that the **Content threshold** for the **Images** content type format has been set to *25%*. This means that if you navigate to a folder where at least 25% of the files within it are images (or rather, files whose extensions have been added to the **Images** file type group), the display would change to use the format defined by the content type.

You can add new file type groups, or edit the existing ones, through the [File Types](/Manual/file_types/RAEDME.md) editor.

![](/Manual/images/media/content_type_groups.png) 

When you [add a new group](/Manual/file_types/file_type_groups.md) through the [File Types](/Manual/file_types/RAEDME.md) editor an entry for it will automatically be created in the **Content Type Formats** section of the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) Preferences page.

More:

[File Type Groups](/Manual/file_types/file_type_groups.md)  
[File Types](/Manual/file_types/RAEDME.md)  
[Folder Formats](folder_formats.md)  
[Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md)  
