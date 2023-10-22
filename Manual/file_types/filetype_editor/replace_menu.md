# Replace Menu

The **Replace Menu** tab lets you add commands to the context menu displayed when you right-click on a file icon in the **[Confirm File Replace](/Manual/file_operations/copying_moving_and_deleting_files/the_confirm_file_replace_dialog.md)** dialog (displayed when copying a file over one that already exists). Using this you can define commands that, for example, let you compare the old and new files using an external comparison tool.

![](/Manual/images/media/replace_menu_edit.png)

For example, a command to compare the two files using Beyond Compare might look like this:

"C:\Program Files (x86)\Beyond Compare 4\BCompare.exe" {filepath\$} {filepathdest\$}

Then, in the Replace dialog, clicking either of the file thumbnails shows this command at the top of the context menu.

![](/Manual/images/media/replace_menu.png)

  
