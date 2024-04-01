# Copying Files

These are general options that affect how Directory Opus copies files.

- **Automatically select newly copied files**: When newly copied files are added to the file display, they will be automatically selected.
- **Automatically manage file copy queues**: This option enables automatic copy queuing. When this option is on, Opus will automatically create copy queues based on the source and destination locations and the types of drive involved. If you turn this off, copy queuing can be used manually with the **QUEUE** argument to the Copy command. 
- **Display confirmation when a job is queued**: If a copy is queued automatically, this option causes Opus to display a prompt confirming the fact. You can disable this prompt by turning this option off, or by specifying the **QUEUE=quiet** argument to the Copy command.
- **Generate thumbnails for network files in *Confirm File Replace* dialog**: If turned on, the [replace dialog](/Manual/file_operations/copying_moving_and_deleting_files/the_confirm_file_replace_dialog.md) will automatically load thumbnails where possible for files on network folders. If turned off, generic icons are shown for network files and a "?" button lets you generate them on demand.
- **Show icon overlays for files being copied**: Files that are currently being copied, or are queued to be copied, will have a small icon overlaid on their own icons to indicate that they are part of a copy operation.
- **Show ghost files for queued copies**: When files are queued to be copied, [ghost files](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/ghost_files.md) are shown in the destination to indicate that a file is queued to be copied there.

  
=='Copy of' template==

This template is used to define the new name of a copy of an existing file (for example, when you select a file and press <kbd>Ctrl+C</kbd> followed by <kbd>Ctrl+V</kbd>). You can use two codes in the template string to insert information:

- **%1**: Inserts the original file name.
- **%2**: Inserts the copy count in brackets (if greater than one).

The original file name is inserted without the file extension (which is automatically applied to the end of the new file).

For example, the default template is `%1 - Copy %2`. Say you pick a file "Document.txt" and press <kbd>Ctrl+C</kbd>, <kbd>Ctrl+V</kbd>.

The first copy of an existing file has a "copy count" of 1, which is not shown - so `%2` will expand to nothing. The first copy's name would be <nobr>`Document - Copy.txt`</nobr>.

If you press <kbd>Ctrl+V</kbd> again to make a second copy, the copy count would be 2, and the new filename would be <nobr>`Document - Copy (2).txt`</nobr>.
