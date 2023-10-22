# Tiles Mode

The **Tiles Mode **page in the [file type editor](../filetype_editor/RAEDME.md) lets you define what is shown for files of that type when the file display is in [tiles mode](/Manual/basic_concepts/the_lister/view_modes.md).

When Opus needs to display a file in tiles mode, it checks file types in the following order:

1.  The specific file type for that file (e.g. for a **.jpg** file this might be the **JPEG Image** file type)
2.  The file type group that contains that file extension (e.g. **Images**)
3.  The **Recognized images** file type if the file is a recognized image file
4.  The **All files** file type (or for a folder, **All folders**)
5.  The **All files and folders** file type.

The first, most specific, file type with tiles mode text defined is the one used. So if you want to assign tiles mode text to all members of a group you can edit the file type group definition, and then override it on a per file-type basis if needed.

![](/Manual/images/media/tiles_-_images.png) 

  
The tiles mode definition (the image above illustrates the default tiles mode text for the **Images** group) uses various **{..}** codes to insert information about the file into the tile's label. Each line in the edit field corresponds to a line in the label. Bear in mind that the amount of text that can be displayed on a tile is limited, but you can still use this for useful effect. You can configure the size of tiles (and therefore how much information can be displayed in the label) on the [Tiles Mode](/Manual/preferences/preferences_categories/file_display_modes/tiles_mode.md) Preferences page.

![](/Manual/images/media/tiles_-_example.png)

  
You can see that the **Images** group tiles mode definition has resulted in the type, image dimensions and file size being displayed in the tile for the **.jpg** file, whereas the **.txt** file only displays the type and file size (this comes from the default tile definition for the **[All Files](../directory_opus_file_types.md)** file type).

The keywords used in tiles are the same as used by the [Rename](/Manual/file_operations/renaming_files/RAEDME.md) function when [renaming files using metadata](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md), and the **[Set](/Manual/reference/command_reference/internal_commands/set.md)** command when adding and removing columns to the file display. See the [Keywords for Columns](/Manual/reference/metadata_keywords/keywords_for_columns.md) page for a full list of supported keywords. Two special keywords that are specific to the tiles mode definition are:

- **{foldersize}**: This code applies to tiles for folders, and its use will cause Opus to calculate the total size of the folder when its tile is displayed. 
- **{foldercontent}**: This code also applies to folders; it will result in Opus displaying the names of the first few files and sub-folders contained in the folder.

Any text you enter into the tile definition that isn't a **{..}** code is displayed as-is. You can also use some simple HTML-style markup codes to control font styles in the tile:

- **\<#RRGGBB\>...\</#\>**: This sets the text color for text between the tags. The color is given in [hexadecimal](http://en.wikipedia.org/wiki/Web_colors), e.g. **\<#32CD32\>Hello!\</#\>** would display the text **Hello!** in lime green.
- **\<b\>..\</b\>**: This displays text between the tags in **bold**.
- **\<i\>..\</i\>**: This displays the text between the tags in *italics.*
- **\<u\>..\</u\>**: This underlines the text between the tags.

At the bottom of the tiles page are several buttons:

- **Insert Field**: This displays a drop-down list of all the information fields (arranged by category) that you can use in tiles. This list is also automatically displayed in a pop-up menu when you press the **{** key in the tile definition field. So don't worry, you don't have to memorise all of the codes!
- **Samples**: This lets you access several sample tile definitions for reference (the samples are the defaults for the various default file type groups plus generic tile definitions for other files and folders).
- **Clear**: Clears the tile definition completely.
