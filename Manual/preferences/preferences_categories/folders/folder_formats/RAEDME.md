# Folder Formats

This page lets you configure the [Folder Formats](/Manual/basic_concepts/folder_options/folder_formats.md) system, which lets you define folder formats (display parameters) for specific folders, folders containing certain types of files, or defaults for certain types of folders. For example, you can make it so that Opus automatically sorts a particular folder by date in reverse, or switches into thumbnails mode in any folder containing mostly images.

The Folder Formats system is powerful but rather complex. There's an [FAQ on it at the Resource Centre](https://resource.dopus.com/t/folder-formats-quick-guide/1313) that we recommend you have a read of as it may explain things in a bit more detail than this help file does.

![](/Manual/images/media/folder_formats.png) 

The Formats list is grouped into different sections:

- **Path Formats**: This group contains formats that have been defined for specific folders. You can also define a format for a path using a wildcard string - in the screenshot above, a format has been defined for any path below a folder called *Visual Studio Projects*, as well as for the folder// C:\Test//.  
  \* **System folders**: Contains formats that can be defined for certain special locations. There are currently only two formats in this group - the **Computer** folder, which is used when Opus displays My Computer itself rather than hosting Explorer, and the **Portable Devices** folder, which is used when viewing the root of the [mtp:](/Manual/basic_concepts/virtual_file_system/mtp.md) namespace.  
  \* **Content Type Formats**: The Content Type section contains formats that are defined for [file type groups](/Manual/file_types/file_type_groups.md). When the [Content Types](/Manual/basic_concepts/folder_options/content_types.md) system is enabled, these formats will be used automatically when a folder containing enough of those types of files is read. For example, the Content Type format for the Images group can be set to switch the display into thumbnails mode. If you navigated to a folder that contained mostly images, this format would be applied automatically.  
  \* **Folder Type Formats**: This section defines the default formats that are used for certain types of folder when a specific format hasn't been defined. The default types are:  
  \* **Collection**: The default format for [File Collection](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md) folders.
  - **Flat View**: This specifies a format that is applied whenever a file display is put into [Flat View](/Manual/basic_concepts/flat_view.md) mode.
  - **FTP**: The default format for FTP sites.
  - **Local Drives**: The default format for folders located on local drives (fixed hard drives like C:).
  - **Network Drives**: The default format for folders located on network drives.\\
  - **OneDrive**: The default format for OneDrive synchronized folders (only under Windows 10).
  - **Portable Devices**: The default format for folders located on portable devices (like phones and cameras).
  - **Removable Drives**: The default format for removable drives like USB flash drives.
  - **Search Results**: The default format for a File Collection that is used to present search results. This will override the **Collection** format for these collections.
  - **Synchronize**: This is a format that is applied whenever the [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool is used.
  - **ZIP**: The default format for ZIP files.

- **Favorite Formats**: These are formats that aren't linked to a specific folder, but instead can be applied quickly to any folder through a drop-down list in the Lister's *Folder Options* menu.  
  \* **Default Format**: Contains the *User Default* format. This is the over-all default format that is used if no other format has been defined (see below).

You'll notice that some formats in the list have checkboxes - this lets you turn a format on or off (in the case of Path Formats, it lets you temporarily disable a format without deleting it from the list).

Whenever you navigate to a new folder, Opus consults the Formats list to work out what format to display it with. The list is searched from top-to-bottom:

1.  First, if a **Path Format** has been configured for that specific folder, or the folder matches a configured wildcard format, it will be used.
2.  Secondly, the **Content Types** system is checked if enabled. If the folder contains enough files to meet the requirements of one of the Content Type formats, that format will be used.
3.  Next, if no other format has matched, the **Folder Type Formats** for that type of folder or drive is used if it's turned on.
4.  Finally, if a **Folder Type Format** hasn't been configured (or is turned off), the **User Default **format is used. This is a "catch-all" format that can never be turned off and represents the underlying default format for all folders.

(As a side note: There are some cases when the above doesn't happen when you navigate to a new folder. If you have edited the format in the current file display with the **[Folder Options](/Manual/basic_concepts/folder_options/RAEDME.md)** dialog, step 4 does not take place - your manually edited format will be maintained until you navigate to a folder with its own specific format defined. And if you have the [format lock](/Manual/basic_concepts/folder_options/locking_the_format.md) turned on, the format will **never** automatically change).

To edit the formats, use the toolbar buttons at the top of the page: ![](/Manual/images/media/favorites_-_add.png) (add a new format), ![](/Manual/images/media/favorties_-_edit.png) (edit an existing format), ![](/Manual/images/media/filters_-_rename.png) (rename a Favorite format) and ![](/Manual/images/media/favorites_-_delete.png) (delete a format). Clicking the **Add** button displays a drop-down menu that lets you select the type of format to add:

- **Path Format**: a format for a specific path.  
  \* **Wildcard Path Format**: a format for any path that matches the specified wildcard pattern. You can define the pattern using the standard Opus [wildcard system](/Manual/reference/wildcard_reference/pattern_matching_syntax.md), or using [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md). If the **Expand aliases** option is turned on then Opus will attempt to expand folder aliases and environment variables in the entered string before performing the pattern matching. For example, **/\$Data** (which is a folder alias for a drive called *Data*) would let you create a folder format that applies to a drive labeled *Data* no matter what drive letter it has.  
  \* **Content Type Formats**: Actually this option doesn't do anything except open the [File Types dialog](/Manual/file_types/RAEDME.md) for you. Content Type formats are based on [File Type Groups](/Manual/file_types/file_type_groups.md), and so to add a new Content Type you have to use the File Type editor to add a new group. Once you add the group through the File Type editor, it will appear in the Content Types section in the Formats list and you can then define the format for it.  
  \* **Favorite Format**: You will be prompted for the name of the new format.

As well as using the toolbar buttons, you can also:

- Double-click a format to quickly edit it
- Right-click a format to copy its definition and paste it into another, an existing format to your favorites list, or copy the definition of a favorite format into another format.

![](/Manual/images/media/format_editor.png)

When you edit a format Opus displays the **Edit Format** dialog. This dialog contains several tabs with options that control various aspects of the folder display. Each tab contains several sections and these sections can be enabled or disabled separately. When a section is disabled the options within that section are not applied to the display even when the format itself is used. This means that "more specific" formats (like a Path Format for a certain folder) can inherit settings from "more general" formats like one of the Defaults. For example, the wildcard format for *Visual Studio Projects* in the screenshot above does nothing except set the file display to be grouped by Date modified. The rest of the display parameters will come from the applicable default format.

See the [Folder Options](/Manual/basic_concepts/folder_options/RAEDME.md) page for a full discussion of the options available for folder formats. The **Options** tab has a couple of settings that only apply to saved folder formats:

- **Include columns from other matching formats**: This option affects which columns are displayed when this format is in use. If turned off (and the checkbox for the **Columns** page is enabled), the only columns displayed in details or power mode will be the columns defined by this format. If this option is turned on, then the columns defined by this format will be displayed, *as well as the columns for any other formats that match the current folder*. In this case, the method used to find a folder format described above is modified slightly. The first matching format is still used, but the search doesn't stop immediately - Opus will continue down the order of priority looking for other formats that match, and apply any columns (and only columns - no other settings) that those formats define. This process stops as soon as a matching format is encountered that doesn't set the Include columns from other matching formats option.  
  \* **Use as the default format for all sub-folders**: This option is used with path formats - if turned on, the format defined for a path will also be used for any sub-folders under that path, unless they have their own specific path format defined as well.

# Folder Formats
