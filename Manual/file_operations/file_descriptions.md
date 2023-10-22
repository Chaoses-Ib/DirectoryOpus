# File Descriptions

File Descriptions are a user-defined string that can be assigned to a file or folder, often used to keep notes about the file contents. Unfortunately Windows does not provide a standardised system for adding a user-defined description to files and folders. Opus does allow you to do this, and provides two different mechanisms for storing these descriptions:

- The *descript.ion* system is an old, pseudo-standard, that saves all the descriptions for the items in a folder to a separate file (called "descript.ion") in the same folder. You can enable support for this system using the option on the **[Folders / Folder Behaviour](/Manual/preferences/preferences_categories/folders/folder_behaviour.md)** page in Preferences.
- The *NTFS comments* system uses the [Alternate Data Stream](http://en.wikipedia.org/wiki/Alternate_Data_Stream#NTFS) feature of the NTFS file system to store the description for a file in a separate data stream attached to the file.

Each of these two systems have their own advantages and disadvantages. The *descript.ion* system may be supported by other programs - for example, some image viewing tools support it, and you may want to enable this in Opus so that descriptions added by one program can be seen in the other. The disadvantages of *descript.ion* are that it is less efficient - every time a description is read or written, the *descript.ion* file has to be opened and parsed. The *descript.ion* files can also clutter up your file listings, although Opus does give you the ability to hide them if desired.

Using the *NTFS comments* system is more efficient than *descript.ion* and as alternate data streams are not normally visible, it can give a more elegant and unified feel to using file comments. The main disadvantage is that they are only supported on NTFS-formatted drives - if you're using another file system like FAT32, this system doesn't work.

Whichever system you elect to use, you can assign a description to a file in two ways:

- Using the **Description** command in the **Properties** drop-down on the default toolbar.

![](/Manual/images/media/setdesc_menu.png)

You can also press **Ctrl+P**. This displays the Set Description dialog, which displays the current description (if any) and lets you clear or edit it.

![](/Manual/images/media/setdesc_menu_001.png)

The **Set this description for files within selected folders** switch causes the function to operate recursively - all files inside any selected folders will be given the same description.

- Using the [Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md) or the [Set Metadata](editing_metadata/RAEDME.md) dialog. These let you edit the description for selected files using the **Comment** field in the **Extended Properties** category.

![](/Manual/images/media/meta_desc.png)

See the [Editing Metadata](editing_metadata/RAEDME.md) page for more information on using the metadata editor.

By default Opus does not preserve file descriptions when you copy a file, as (particularly when using *descript.ion*) this can slow down the file copy process. The **Preserve the descriptions of copied files** option on the **[File Operations / Copy Attributes](/Manual/preferences/preferences_categories/file_operations/copy_attributes.md)** page in Preferences lets you enable this if desired.
