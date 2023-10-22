# Deleting Files

To delete a file or folder, you can either:

- Select the file and press the **Delete** key on the keyboard
- Right-click the file and choose the **Delete** command from the context menu
- Select the file and click the **Delete** button on the toolbar.

By default, Opus deletes files to the recycle bin when possible. Files that are deleted to the recycle bin can normally be recovered (via the [Undo](../tracking_and_undoing_file_operations.md) command), until the recycle bin is emptied. The recycle bin is not supported on network drives or removable media, and files deleted from inside archives or on FTP sites also can not be recovered.

If you hold the **Shift** key down when pressing **Delete** or clicking the toolbar button, you can bypass the recycle bin and permanently delete the file. You can also disable the recycle bin altogether through Preferences.

The **[File Operations / Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page contains several options that let you configure the Delete function in Opus. You can choose whether Opus asks you for confirmation before the delete (you can even have it ask you before each file if you like). As mentioned above, the use of the recycle bin can be configured. You can also choose whether files marked as read-only can be deleted without a special confirmation prompt.

The drop-down menu attached to the **Delete** button on the default toolbar contains several other commands relating to deleting files:

\<WRAP c1borderless\> \|![](/Manual/images/media/delete_dropdown.png)\| \|\<WRAP\>\<wrap topspace\>\</wrap\>

- **Delete**: Delete selected files or folders, to the recycle bin by default
- **Secure Wipe**: [Securely deletes](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.md) selected files or folders so they can't be recovered
- **Remove From Collection**: When viewing the contents of a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md), this lets you remove an item from the collection without actually deleting it. If you use the regular Delete command in a file collection, the real file will be deleted.
- **Delete Filter**: Activates the [recursive filter](filtered_operations/RAEDME.md) for the Delete function, which lets you selectively delete the contents of selected sub-folders. \</WRAP\>\|

\</WRAP\>\<wrap clear/\>

More:

[Secure Delete](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.md)  
