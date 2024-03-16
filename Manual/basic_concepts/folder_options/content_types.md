# Content Types

The content types system lets you configure Opus to automatically change the display format for a folder based on the contents of that folder. For example, the display can automatically change to thumbnails mode whenever you navigate to a folder containing mostly images.

There are two distinct concepts that make up the Content Types system:

- **File Type Groups**: Content types are built on the configured [file type groups](/Manual/file_types/file_type_groups.md). So you can have content type formats for Images, Music, etc. - any file type group that you create can have a content type format associated with it.
- **Folder Formats**: The [Folder Formats](folder_formats.md) system is used to define the display format that is applied for each file type group.

##### Enabling Content Type formats

Because it can be confusing to have Opus change the folder format when you're not expecting it, you need to specifically enable the content types system in Preferences.

Each file type group is listed in the **Content Type Formats** category on the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) page in Preferences. Use the checkbox next to the group name to enable its content type format. You can edit each content type's format from there as well.

##### Content Type threshold

To identify a folder as matching a particular content type, a configurable percentage of files within it must belong to the related file type group. Each content type format is shown with a percentage value to the right of it - click that value to edit the threshold.

The **Consider subfolders when calculating content threshold** checkbox when editing the threshold allows you to choose whether folders should be counted or ignored when considering the percentage of items in the folder.

For example, if the **Content threshold** for the **Images** content type format has been set to *25%*, it means that if you navigate to a folder where at least 25% of the files within it are images (or rather, files whose extensions have been added to the **Images** file type group), the display would change to use the format defined by the content type.

##### Adding new content types

You can add new file type groups, or edit the existing ones, through the [File Types](/Manual/file_types/RAEDME.md) editor.

When you [add a new group](/Manual/file_types/file_type_groups.md) through the [File Types](/Manual/file_types/RAEDME.md) editor an entry for it will automatically be created in the **Content Type Formats** section of the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) Preferences page.

More:  
[File Type Groups](/Manual/file_types/file_type_groups.md)  
[File Types](/Manual/file_types/RAEDME.md)  
[Folder Formats](folder_formats.md)  
[Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md)  
