# Using Wildcards when Copying

The **Copy File** and **Move** commands have the ability to rename files as they are copied (or moved). This is known as **Copy As** or **Move As** (as in, *copy file XXX as YYY*).

To use this functionality, select the files you want to copy or move and then select the **Copy As** or **Move As** commands from the **Copy Files **or **Move** drop-down menus. The commands will display a dialog box that lets you enter the new name for the copied or moved file.

![](/Manual/images/media/13/copy_as.png) 

- The **Old name** field identifies the original file name.
- The **New name** field lets you enter a new name for the file.

If you simply enter a new name and click **OK**, the file will be copied or moved using the name you supplied. If you had multiple files selected then the dialog will reappear after the first file has been copied, to prompt you for a new name for the second file (and so on).

### Renaming using wildcards

As an alternative to entering a new name for each file, you can use a simple wildcard system to rename all copied or moved files at once. This is not a full pattern matching (or regular expressions) system; instead, the only wildcard character that's recognised is \* (the asterisk). This is the same system used in the **[Simple Wildcard Rename](../../renaming_files/simple_wildcard_rename.md)** function. The asterisk is used to mark areas of text that are to be matched and retained from the old to new names.

- Enter the "from" pattern in the **Old name** field.
- Enter the "to" pattern in the **New name** field.

For example, to copy all files beginning with **IMG** to new files that begin with **Image** instead, you might do the following:

![](/Manual/images/media/13/copy_as_2.png) 

You can use as many asterisks as you like in the old and new patterns. The following image shows an example of this; the **Old** and **New name** fields each used two asterisks to preserve two separate parts of the name, while replacing the rest.

![](/Manual/images/media/13/copy_as_3.png) 
