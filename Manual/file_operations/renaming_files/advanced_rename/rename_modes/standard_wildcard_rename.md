# Standard Wildcard Rename

The *Standard Wildcard Rename* mode lets you batch rename files using a simple wildcard system. The \* character (asterisk) is used to specify one or more parts of the existing filename that are to be retained in the new name.

![](/Manual/images/media/13/standard_rename.png)

In the above example, you can see that the original filenames had a mix of *Img\_* and *IMG\_* prefixes, and the file extensions were also a mix of upper and lower-case.

The **Old name** pattern of *img\_\*.jpg* tells Opus to match any filename beginning with *img\_* and ending with .jpg (case does not matter as the **Case sensitive** option was not enabled). The \* in the pattern is used to mark the portion of the filename that will be carried through to the new name. The **Ignore extension** option has been turned off so that the wildcard will operate on the full filename including the file extension.

You can use as many instances of the \* character in the patterns as you like, as long as there are at least as many in the **Old name** field as there are in the new. For example, if you wanted to preserve the case of the file extension in the above example, you could specify an **Old name** pattern of *img\_\*.\** and *IMG\*.\** for the **New name** pattern.

You can't use this system if you want to change the order of preserved strings (as one asterisk looks very much like another) - to do that, you need to use *[Regular Expressions](regular_expressions.md)* mode, which lets you refer to preserved strings by number.
