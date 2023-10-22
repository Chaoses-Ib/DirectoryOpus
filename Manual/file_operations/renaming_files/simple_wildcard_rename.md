# Simple Wildcard Rename

The *Simple Rename* dialog lets you batch rename files using a simple wildcard system. The \* character (asterisk) is used to specify one or more parts of the existing filename that are to be retained in the new name. It is basically equivalent to the *[Standard Wildcard Rename](advanced_rename/rename_modes/standard_wildcard_rename.md)* mode in the *[Advanced Rename](advanced_rename/RAEDME.md)* dialog. This wildcard system is also used in the **Copy As** and **Move As** functions - see the documentation on [Using Wildcards when Copying](../copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for more examples.

The *Simple Rename* function isn't exposed in the default toolbars - instead, we recommend the use of the *Advanced Rename* dialog, as it can do everything the simple one can do plus much more. If you want to use *Simple Rename*, however, you'll need to [configure a button or hotkey](/Manual/customize/creating_your_own_buttons/RAEDME.md) to access it. The command you need is **Rename SIMPLE**.

![](/Manual/images/media/simple_rename.png) 

  
In this example, we want to rename any file that begins with **Img\_** and ends with **.jpg**. The match is not case sensitive, so this will match **Img_2481.jpg**, **img_2481.jpg**, etc. The \* indicates that any text between the prefix and suffix is to be preserved, and the \* in the **New name** field indicates where that text would be placed. Given the following input filenames, the resultant new names would be:

    Img_2481.jpg    IMG2481.jpg

    IMG_2483.JPG    IMG2483.jpg

    Img_2486.jpg    IMG2486.jpg

The rename operation will operate on all files and folders that were selected when the command was invoked, however files within sub-folders will not be renamed (you need to use *Advanced Rename* for that).

If you don't enter a wildcard pattern, but instead just supply a literal new name, the function will rename each selected file in turn - the first file will be renamed, and the dialog will re-open showing the name for the second selected file, and so on.
