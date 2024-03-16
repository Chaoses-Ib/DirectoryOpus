# Simple Wildcard Rename

The *Simple Rename* dialog lets you batch rename files using a simple wildcard system. The \* character (asterisk) is used to specify one or more parts of the existing filename that are to be retained in the new name. It is basically equivalent to the *[Standard Wildcard Rename](advanced_rename/rename_modes/standard_wildcard_rename.md)* mode in the *[Advanced Rename](advanced_rename/RAEDME.md)* dialog. This wildcard system is also used in the **Copy As** and **Move As** functions - see the documentation on [Using Wildcards when Copying](../copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for more examples.

The easiest way to access *Simple Rename* is to select the option in the *Rename* dropdown menu - this makes it the default mode, and clicking the *Rename* button after that will bring it up in simple mode by default. You can switch back to the advanced mode at any time.

You can also access it using the raw command `Rename SIMPLE`.

![](/Manual/images/media/13/simple_rename.png) 

In this example, we want to rename any file that begins with **Img\_** and ends with **.jpg**. The match is not case sensitive, so this will match **Img_2481.jpg**, **img_2481.jpg**, etc. The \* indicates that any text between the prefix and suffix is to be preserved, and the \* in the **New name** field indicates where that text would be placed. Given the following input filenames, the resultant new names would be:

    Img_2481.jpg    IMG2481.jpg

    IMG_2483.JPG    IMG2483.jpg

    Img_2486.jpg    IMG2486.jpg

The rename operation will operate on all files and folders that were selected when the command was invoked, however files within sub-folders will not be renamed (you need to use *Advanced Rename* for that).

If you don't enter a wildcard pattern, but instead just supply a literal new name, the function will rename each selected file in turn - the first file will be renamed, and the dialog will re-open showing the name for the second selected file, and so on.
