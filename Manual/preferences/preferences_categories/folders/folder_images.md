# Folder Images

The **Folder Images** page lets you change the background image and color in specific folders, or specific types of folders. It's similar in operation to the [Folder Formats](folder_formats/RAEDME.md) page. Folders and colors defined here will override the relevant global settings on the [Images](/Manual/preferences/preferences_categories/colors_and_fonts/images.md) and [Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md) pages.

The list of folders is split into different groups:

##### Folders

This group defines images and colors for specific folders. You can also define an image for a path using a wildcard string.

##### System folders

Defines images for certain special locations. There are currently only two locations in this group - the **Computer** folder, which applies when Opus displays that folder itself rather than hosting Explorer, and the **Portable Devices** folder, which applies when viewing the root of the [mtp:](/Manual/basic_concepts/virtual_file_system/mtp.md) namespace.

##### Content Types

The Content Types section defines images for [file type groups](/Manual/file_types/file_type_groups.md). When the [Content Types](/Manual/basic_concepts/folder_options/content_types.md) system is enabled, these images will be used automatically when a folder containing enough of those types of files is read.

##### Folder Types

This section defines default images for certain types of folder when a specific image hasn't been defined. The types are:

      * **Archives**: ZIP and other archive files.
      * **Cloud Storage**: Cloud storage folders (OneDrive, Dropbox, etc.)
      * **Collection**: General [[:basic_concepts:virtual_file_system:file_collections|File Collection]] folders. 
      * **Duplicate Files**: A file collection that's used to show the results of the [[:additional_functionality:duplicate_file_finder|duplicate finder]].
      * **Find Results**: A file collection that's used to show the results of the [[:basic_concepts:searching_and_filtering:find_files|find tool]].
      * **Flat View**: Applies whenever a file display is put into [[:basic_concepts:flat_view|Flat View]] mode. 
      * **FTP**: FTP sites. 
      * **Local Drives**: Folders located on local drives (fixed hard drives like C:). 
      * **Network Drives**: The Folders located on network drives.
      * **Portable Devices**: Folders located on portable devices (like phones and cameras). 
      * **Removable Drives**: Removable drives like USB flash drives. 
      * **Search Results**: A file collection that is used to present quick search results.
      * **Synchronize**: Applies whenever the [[:file_operations:copying_moving_and_deleting_files:copying_updated_files:synchronize|Synchronize]] tool is used. 

##### Working with the folder list

The toolbar above the list lets you add or remove specific folders and path wildcards. A path wildcard can be defined using the standard Opus [wildcard system](/Manual/reference/wildcard_reference/pattern_matching_syntax.md), or using [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md). If the **Expand aliases** option is turned on then Opus will attempt to expand folder aliases and environment variables in the entered string before performing the pattern matching.

To enable an image for a particular folder or type of folder, turn its checkbox on. When the item is selected, the bottom part of the dialog will show that image's settings

##### Image settings

![](/Manual/images/media/13/folder_images.png)

- **Image**: This specifies the image to use. The path can be given using aliases or as an absolute path. The down arrow on the right drops down a list of other images that are in use currently, making it easy to assign the same image to multiple folders. You can leave the image empty if you only want to change the background color).
- **Image fit**: Defines how the image is scaled to fit the window. The options are:
  - **Tiled**: The image is tiled across the window; if it's smaller than the dimensions of the window, it's repeated to fill the bounds of the element.
  - **Stretched**: The image is stretched to the dimensions of the window (either smaller or larger.)
  - **Aspect Fit**: Makes the image large enough to cover the window's width or height without cropping, and preserves the original aspect ratio.
  - **Aspect Fill**: Makes the image large enough to cover the whole window, cropping the image where needed (and also preserves the aspect ratio).
  - **Aspect Tile**: Similar to **Aspect Fit**, except the image is then tiled to fill the window completely.
  - **Top/Left**: The image is anchored to the top/left corner of the window , and is clipped if it's larger than the window.
  - **Top/Right**: The image is anchored to the top/right corner.
  - **Bottom/Left**: The image is anchored to the bottom/left corner.
  - **Bottom/Right**: The image is anchored to the bottom/right corner.
  - **Center**: The image is centered within the element.
- **Opacity**: Specify the opacity of the image; 100% is fully opaque, 0% is fully transparent.
- **Fill color**: Specifies the background fill color. The checkerboard pattern shown above indicates that no color is selected.
- **Shared**: The image will be shared with other elements across the whole Lister.
- **Apply settings to all sub-folders**: The defined image will also be used for any sub-folders under that path, unless they have their own specific image defined as well.
