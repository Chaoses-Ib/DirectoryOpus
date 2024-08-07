# Creating Folders

There are two ways to create a new folder using Opus. The first way is the same as in Explorer - right-click on the background of the file display (or on a folder in the tree) and choose **New / Folder**.

The second way is to use the *Create Folder* dialog, which you can get to using the **New Folder** button on the default toolbar.

As well as letting you make a new folder, the *Create Folder* dialog offers some additional functionality:

- You can make multiple folders simultaneously
- You can make a whole sub-tree of folders at once (so a folder, a sub-folder, a sub-sub-folder, and so on, all with the one command)
- You can make multiple sub-folders under the same parent folder at once
- You can automatically navigate to the newly created folder or folders

### Making a single folder

![](/Manual/images/media/13/create_folder.png) 

This shows the *Create Folder* in single folder mode.

The two numbers displayed in below the name field indicate the length of the name you have entered and the total length of the path once the folder is created. This can be useful to ensure that your path length doesn't grow beyond the normal maximum of 259 characters - although Opus has no problems dealing with longer paths than that, many other programs may have trouble.

### Making a folder tree

You can create a whole tree of sub-folders at once by entering the folder names separated by slashes. For example:

![](/Manual/images/media/13/create_sub_folders.png) 

This would create a folder called *One* in the current location, then a sub-folder in *One* called *Two*, a sub-folder in *Two* called *Three*, and so on, all in the one operation.

### Making multiple folders at once

If you turn on the **Create multiple folders** option you can create multiple folders simultaneously in the current location. If this is turned on the name field changes to a multi-line text box that lets you enter as many names as you like (one per line):

![](/Manual/images/media/13/create_folder_multi.png)

### Making multiple child folders

In the above example, the new folders will all be created relative to the current folder. You can also create multiple child-folders at the same sub-folder level using the vertical bar character (`|`) to separate the child folder names.

![](/Manual/images/media/13/makedir_multi.png)

The above example will create two child folders, *2023* and *2024*, and below those create 12 sub-folders (one for each month of the year).

### Making numbered folders

When the dialog is in **Create multiple folders** mode, it supports automatic creation of multiple numbered folders using the `<..>` insertion code.

The full format of this code is `<a-b+c>`, which will insert numbers from *a* through to *b*, incrementing by *c* each time.

The *a* value can include zero padding - for example, `<001-100>` would create folders 001, 002, 003, ..., 100.

The *-b* and *+c* values are optional:

- If *-b* is not given, the first number is assumed to be the top of the range and the bottom defaults to 1 - so to quickly create ten numbered folders, simply use `<10>`.
- If *+c* is not given the default increment value is 1.

Any text outside the numbering code is preserved verbatim, e.g. `New Folder <5>` would create "New Folder 1", "New Folder 2", etc.

### Using the dialog in multiple folder mode

In **Create multiple folders** mode, the <kbd>Enter</kbd> key moves to a new line in the text box, but you can still quickly *OK* the dialog by pushing <kbd>Enter</kbd> twice on the last line, or by pushing <kbd>Shift+Enter</kbd> on any line. Since double-tapping <kbd>Enter</kbd> at the end is only one extra keystroke, even when only creating a single folder, you may find it convenient to leave the dialog in this mode all the time.

### Automatically reading the new folder

The drop-down menu attached to the **OK** button lets you choose what to do with the new folder once it's been created.

![](/Manual/images/media/13/new_arc_-_tristate.png)

- **Create Folder**: The new folder (or folders) is created, but not read.
- **Read Folder**: The file display will automatically navigate into the new folder once it is created.
- **Read Dual**: The new folder will be opened in the other file display (the Lister will be put into dual-display mode if needed). If you are creating multiple folders, only the first folder will be read.
- **Read New Tab**: The new folder will be opened in a new folder tab. If you are creating multiple folder a new tab will be created for each new one.
- **Read New Tab (Dual)**: The new folder will be opened in a new folder tab in the other file display.

You can also hold the appropriate qualifier key when clicking the **OK** button, rather than dropping down the menu.
