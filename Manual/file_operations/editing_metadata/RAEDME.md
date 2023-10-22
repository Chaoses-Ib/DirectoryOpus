# Editing Metadata

Metadata is information that is stored in a file that describes the file itself. For example, photos you take with your digital camera contain metadata like the date and time you took the picture, and the exposure settings used to take it.

Opus lets you edit file metadata in three ways; the easiest are with the **[Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md)**, and with the **Set Metadata** dialog. The actual process of editing metadata is the same in both cases. The **Metadata Pane** lets you view metadata and make changes for selected files directly in the Lister or image viewer, whereas the **Set Metadata** dialog works like a typical file operation - it displays a dialog letting you choose the changes to make, and then when you click **OK** the changes will be applied to all selected files.

The third way of editing metadata is [programmatically](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.md) - you can use the internal **[SetAttr META](/Manual/reference/command_reference/internal_commands/setattr.md)** command to create buttons or hotkeys that automatically modify the metadata of selected files.

![](/Manual/images/media/edit_metadata_command.png)     ![](/Manual/images/media/metadata_pane_command.png)

To invoke the **Set Metadata** dialog, select the files you wish to edit, and choose the **Edit Metadata** command from the drop-down **Properties** menu. To display the **Metadata Pane**, select the **Metadata Pane** command from the **Lister Configuration** drop-down menu. In the standalone [image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md), select **Edit Metadata** from the **Edit** menu. In the Lister, the **Metadata Pane** will update in real time as you select and deselect files in the file display.

Whichever method of editing you choose, the same display is used to both display the current metadata settings and to let you make changes.

![](/Manual/images/media/metadata_example.png) 

The list of metadata properties is divided into a number of categories. The categories and properties shown will change, depending on the type or types of files you have selected. Individual categories can be collapsed to hide their contents by clicking the small ![](/Manual/images/media/metadata_collapse.png) button to the left of the category name.

- **Non-editable Properties**: These are *intrinsic* properties of the files that are shown here for information only - they can't be edited. These are only shown in the **Metadata Pane**, not in the **Set Metadata** dialog.
- **[Document Properties](/Manual/file_operations/editing_metadata/document_properties.md)**: Properties that apply to documents (author, copyright, subject, etc.). Some non-document file types support some of these properties too - for example, an image file can have authors and a subject just like a Word document.
- **[Picture Properties](/Manual/file_operations/editing_metadata/picture_properties.md)**: These are properties that apply to images. They are stored in **EXIF** format and so the image format must support the use of [EXIF data](http://en.wikipedia.org/wiki/EXIF) (e.g. **JPEG**, **PNG**, **TIFF**).
- **[Music Properties](/Manual/file_operations/editing_metadata/music_properties/RAEDME.md)**: These are properties that apply to music files like **MP3** and **WMA**.
- **[Video Properties](/Manual/file_operations/editing_metadata/video_properties.md)**: These are properties that apply to video files like **AVI** and **WMV**.
- **Music & Movie Properties**: These are properties that apply to both music and video files. This category will only be shown if you have both music and video files selected at once.
- **[Extended Properties](/Manual/file_operations/editing_metadata/extended_properties.md)**: These are properties that are nominally available for all file types, like **Comment**, **Rating** and **Tags**. If the selected file formats support those properties natively (for example, **JPEG** files do) then the information will be stored in the file itself. If the selected file formats don't support these properties (like **.txt** files, for example) then Opus will attempt to store the information in an [Alternate Data Stream](http://en.wikipedia.org/wiki/Alternate_data_stream) attached to the file. Because only NTFS file systems support the ADS system, these properties won't be available for files stored on other file systems. If the *Rating* column is displayed in the file display, you can edit a file’s rating directly by clicking the stars (rather than going through the Metadata panel).
- **Standard Properties**: These are properties that are applicable to all files - attributes and timestamps. You can modify these properties through the metadata system as an alternative to using the **[Change Attributes & Times](changing_attributes.md)** dialog. The two timestamp properties have a **Select operation** field that lets you enter a *[time shift](/Manual/file_operations/editing_metadata/time_shifting.md)* string that will perform relative adjustments to the current value of the date fields.

You can edit the metadata of multiple files simultaneously simply by selecting multiple files at once (for the **Metadata Pane**), or by having multiple files selected when invoking the **Edit Metadata** command. Only properties that all selected files have in common can be edited. For example, if you select four image files at once, all the **Document** and **Picture Properties** fields will be shown as normal, but if you select four image files and one music file, only the few **Document** fields they have in common will be available.

The metadata display shows the current values, if any, of the various properties of the selected files. If multiple files are selected and they have different values for a given property, the indication *multiple values* is shown.

![](/Manual/images/media/metadata_multiple_values.png)

This indicates that the selected files did not all have the same initial value for that property. If you edit a property when multiple files are selected, the new value will be applied to all files, so (except in a few special cases) editing a field where *multiple values* is displayed will result in the loss of the individual properties for the selected files.

To edit a value in the metadata display, simply click it to invoke the editing controls. The type of control used will depend on the field being edited. For example, for a string this will be a text edit field, but for a property with only certain options to choose from this might be a drop-down list.

![](/Manual/images/media/metadata_edit_example.png) 

To accept changes you have made to a field, simply click out of it (or on another field). You can also move between fields using the keyboard - press the **Tab** key to move to the next field, or **Shift+Tab** to move to the previous one. You can press the **Enter** key to accept changes you have made to a field, or press **Escape** to undo changes to the current field.

When a property has been modified it is indicated with a red triangle to the left of the field name.

![](/Manual/images/media/metadata_changed.png)

In the **Metadata Pane**, making one or more changes also enables the **Apply** and **Cancel** links in the pane's titlebar. Once you have finished editing the metadata for the selected files, click the **Apply** link to save the changes. You can also click the **Cancel** link to discard any changes and reset all properties to their original values. The arrow buttons (![](/Manual/images/media/metadata_-_move_left.png) ![](/Manual/images/media/metadata_-_move_right.png)) in the title let you quickly move through a list of files - click ![](/Manual/images/media/metadata_-_move_right.png) to go to the next file and ![](/Manual/images/media/metadata_-_move_left.png) to go to the previous file. If you hold the **Shift** key down when you click these arrows, any changes you have made to the current file's metadata will be automatically saved.

In the **Set Metadata** dialog, once you have finished editing the metadata, click the **OK** button to apply the changes to the selected files.

Using drag-and-drop, you can copy certain combinations of properties from one file to one or many target files. When you are editing the metadata for one or more files in the metadata pane or the separate dialog, you can drag-and-drop another file over the properties list. If you drag with the left button, a default set of properties will be copied; dragging with the right mouse button displays a popup menu that lets you choose which properties you want to copy from the dropped file.

![](/Manual/images/media/copy_metadata.png) 

More:

[Document Properties](/Manual/file_operations/editing_metadata/document_properties.md)  
[Picture Properties](/Manual/file_operations/editing_metadata/picture_properties.md)  
[Time Shifting](/Manual/file_operations/editing_metadata/time_shifting.md)  
[Music Properties](/Manual/file_operations/editing_metadata/music_properties/RAEDME.md)  
[Video Properties](/Manual/file_operations/editing_metadata/video_properties.md)  
[Extended Properties](/Manual/file_operations/editing_metadata/extended_properties.md)  
[Programmatic setting of Metadata](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.md)  
