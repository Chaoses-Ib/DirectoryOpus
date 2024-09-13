# Folder Formats

This page lets you configure the [Folder Formats](/Manual/basic_concepts/folder_options/folder_formats.md) system, which lets you define folder formats (display parameters) for specific folders, folders containing certain types of files, or defaults for certain types of folders. For example, you can make it so that Opus automatically sorts a particular folder by date in reverse, or switches into thumbnails mode in any folder containing mostly images.

The Folder Formats system is powerful but rather complex. There's an [FAQ on it at the Resource Centre](https://resource.dopus.com/t/folder-formats-quick-guide/1313?u=chaoses-ib) that we recommend you have a read of as it may explain things in a bit more detail than this help file does.

There's also the [Automatic Formats](/Manual/preferences/preferences_categories/folders/folder_formats/automatic_formats.md) system, which can remember changes to folder formats automatically rather than you having to configure them by hand.

The Formats list is grouped into different sections: 

![](/Manual/images/media/13/folder_formats.png)

 

### Favorite Formats

These are formats that aren't linked to a specific folder, but instead can be applied quickly to any folder through a drop-down list in the Lister's *Folder* menu.

### Path Formats

This group contains formats that have been defined for specific folders. You can also define a format for a path using a wildcard string.

### System folders

Contains formats that can be defined for certain special locations. There are currently only two formats in this group - the **Computer** folder, which is used when Opus displays that folder itself rather than hosting Explorer, and the **Portable Devices** folder, which is used when viewing the root of the [mtp:](/Manual/basic_concepts/virtual_file_system/mtp.md) namespace.

### Content Type Formats

The Content Type section contains formats that are defined for [file type groups](/Manual/file_types/file_type_groups.md). When the [Content Types](/Manual/basic_concepts/folder_options/content_types.md) system is enabled, these formats will be used automatically when a folder containing enough of those types of files is read. For example, the Content Type format for the Images group can be set to switch the display into thumbnails mode. If you navigated to a folder that contained mostly images, this format would be applied automatically.

### Folder Type Formats

This section defines the default formats that are used for certain types of folder when a specific format hasn't been defined. The default types are:

      * **Archives**: The default format for ZIP and other archive files.
      * **Cloud Storage**: The default format for cloud storage folders (OneDrive, Dropbox, etc.)
      * **Collection**: The default format for [[:basic_concepts:virtual_file_system:file_collections|File Collection]] folders. 
      * **Duplicate Files**: The default format for a File Collection that is used to show the results of the [[:additional_functionality:duplicate_file_finder|duplicate finder]]. This will override the **Collection** format for these collections. 
      * **Find Results**: The default format for a File Collection that is used to show the results of the [[:basic_concepts:searching_and_filtering:find_files|find tool]]. This will override the **Collection** format for these collections. 
      * **Flat View**: This specifies a format that is applied whenever a file display is put into [[:basic_concepts:flat_view|Flat View]] mode. 
      * **FTP**: The default format for FTP sites. 
      * **Local Drives**: The default format for folders located on local drives (fixed hard drives like C:). 
      * **Network Drives**: The default format for folders located on network drives.
      * **Portable Devices**: The default format for folders located on portable devices (like phones and cameras). 
      * **Removable Drives**: The default format for removable drives like USB flash drives. 
      * **Search Results**: The default format for a File Collection that is used to present quick search results. This will override the **Collection** format for these collections. 
      * **Synchronize**: This is a format that is applied whenever the [[:file_operations:copying_moving_and_deleting_files:copying_updated_files:synchronize|Synchronize]] tool is used. 

### Default Format

The last group contains a single item - the *User Default* format. This is the "format of last resort" that's used if no other format has been defined (see below).

  

### How folder formats are used

Whenever you navigate to a new folder, Opus consults the Formats list to work out what format to display it with. The list is searched from top-to-bottom:

1.  If a **Path Format** has been configured for that specific folder, or the folder matches a configured wildcard format, it will be used.
2.  If [automatic formats](/Manual/preferences/preferences_categories/folders/folder_formats/automatic_formats.md) are enabled, Opus checks for an automatically saved format, and uses that if found.
3.  The **Content Types** system is checked if enabled. If the folder contains enough files to meet the requirements of one of the Content Type formats, that format will be used.
4.  If no other format has matched, the **Folder Type Formats** for that type of folder or drive is used if it's turned on.
5.  If a **Folder Type Format** hasn't been configured (or is turned off), the **User Default **format is used. This is a "catch-all" format that can never be turned off and represents the underlying default format for all folders.

(As a side note: There are some cases when the above doesn't happen when you navigate to a new folder. If you have edited the format in the current file display with the **[Folder Format](/Manual/basic_concepts/folder_options/README.md)** dialog, your manually edited format will be maintained until you navigate to a folder with its own specific format defined. And if you have the [format lock](/Manual/basic_concepts/folder_options/locking_the_format.md) turned on, the format will **never** automatically change).

### Working with the format list

Firstly, you'll notice that some formats in the list have checkboxes - this lets you turn a format on or off (in the case of Path Formats, it lets you temporarily disable a format without deleting it from the list).

The toolbar above the list lets you add, edit, rename and delete formats. You can also share them with other people and paste in formats others have shared with you.

Use the ![](/Manual/images/media/13/button_add.png) **Add** button to add a new format. The drop-down lets you select the type of format to add:

- **Path Format**: a format for a specific path.
- **Wildcard Path Format**: a format for any path that matches the specified wildcard pattern. You can define the pattern using the standard Opus [wildcard system](/Manual/reference/wildcard_reference/pattern_matching_syntax.md), or using [regular expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md). If the **Expand aliases** option is turned on then Opus will attempt to expand folder aliases and environment variables in the entered string before performing the pattern matching. For example, **/\$Data** (which is a folder alias for a drive called *Data*) would let you create a folder format that applies to a drive labeled *Data* no matter what drive letter it has.
- **Content Type Formats**: Actually this option doesn't do anything except open the [File Types dialog](/Manual/file_types/README.md) for you. Content Type formats are based on [File Type Groups](/Manual/file_types/file_type_groups.md), and so to add a new Content Type you have to use the File Type editor to add a new group. Once you add the group through the File Type editor, it will appear in the Content Types section in the Formats list and you can then define the format for it.
- **Favorite Format**: You will be prompted for the name of the new format.

As well as using the toolbar buttons, you can also:

- Double-click a format to quickly edit it
- Right-click a format to copy its definition and paste it into another, an existing format to your favorites list, or copy the definition of a favorite format into another format.

### Editing a format

![](/Manual/images/media/13/format_editor.png)

When you edit a format Opus displays the **Edit Format** dialog.

This dialog contains several tabs with options that control various aspects of the folder display. Each tab can be enabled or disabled separately. When a tab is disabled the options within that tab are not applied to the display even when the format itself is used. This means that "more specific" formats (like a Path Format for a certain folder) can inherit settings from "more general" formats like one of the Defaults. For example, the wildcard format for *Visual Studio Projects* in the screenshot above does nothing except set the file display to be grouped by Date modified. The rest of the display parameters will come from the applicable default format.

See the [Folder Formats](/Manual/basic_concepts/folder_options/README.md) page for a full discussion of the options available for folder formats.

### Inheritable columns

At the bottom of the **Columns** tab is the **Include columns from other matching formats** option. This option affects which columns are displayed when this format is in use.

- If turned off (and the checkbox for the **Columns** page is enabled), the only columns displayed in details or power mode will be the columns defined by this format.
- If this option is turned on, then the columns defined by this format will be displayed, *as well as the columns for any other formats that match the current folder*.

In the second case, the method used to find a folder format described above is modified slightly. The first matching format is still used, but the search doesn't stop immediately - Opus will continue down the order of priority looking for other formats that match, and apply any columns (and only columns - no other settings) that those formats define. This process stops as soon as a matching format is encountered that doesn't have the **Include columns from other matching formats** option turned on.

### Apply to sub-folders

At the very bottom of the **Edit Format** dialog is the **Use as the default format for all sub-folders** option.

This option is used with path formats - if turned on, the format defined for a path will also be used for any sub-folders under that path, unless they have their own specific path format defined as well.
