# Creating Folders

There are two ways to create a new folder using Opus. The first way is the same as in Explorer - right-click on the background of the file display (or on a folder in the tree) and choose **New / Folder**.

The second way is to use the **Create Folder** dialog, which as well as letting you make a new folder also offers some additional functionality:

- You can make multiple folders simultaneously
- You can make a whole sub-tree of folders at once (so a folder, a sub-folder, a sub-sub-folder, and so on, all with the one command)
- You can make multiple sub-folders under the same parent folder at once
- You can automatically navigate to the newly created folder or folders

![](/Manual/images/media/create_folder.png) 

The two numbers displayed in the bottom-left corner of the dialog (as shown above) indicate the length of the name you have entered and the total length of the path once the folder is created. This can be useful to ensure that your path length doesn't grow beyond the normal maximum of 259 characters - although Opus has no problems dealing with longer paths than that, many other programs (including Explorer) will fail.

To create a folder using the **Create Folder** dialog, click the **New Folder** button on the toolbar and enter the name of the folder to create. You can create a whole tree of sub-folders at once by entering the folder names separated by slashes. For example:

![](/Manual/images/media/create_sub_folders.png) 

This would create a folder called *One* in the current location, then a sub-folder in *One* called *Two*, a sub-folder in *Two* called *Three*, and so on, all in the one operation.

If you turn on the **Create multiple folders** dialog you can create multiple folders simultaneously in the current location. If this is turned on the name field changes to a multi-line text box that lets you enter as many names as you like (one per line):

![](/Manual/images/media/create_folder_multi.png)

The folders will all be created relative to the current folder. You can also create multiple child-folders at the same sub-folder level using the vertical bar character (**\|**) to separate the child folder names.

![](/Manual/images/media/makedir_multi.png)

The above example will create two child folders, *2016* and *2017*, and below those create 12 sub-folders (one for each month of the year).

In **Create multiple folders** mode, the **Return** key moves to a new line in the text box, but you can still quickly *OK* the dialog by pushing **Return** twice on the last line, or by pushing **Shift+Return** on any line. Since double-tapping **Return** at the end is only one extra keystroke, even when only creating a single folder, you may find it convenient to leave the dialog in this mode all the time.

The drop-down menu attached to the **OK** button lets you choose what to do with the new folder once it's been created.

![](/Manual/images/media/new_arc_-_tristate.png)

- **Create Folder**: The new folder (or folders) is created, but not read.
- **Read Folder**: The file display will automatically navigate into the new folder once it is created.
- **Read Dual**: The new folder will be opened in the other file display (the Lister will be put into dual-display mode if needed). If you are creating multiple folders, only the first folder will be read.
- **Read New Tab**: The new folder will be opened in a new folder tab. If you are creating multiple folder a new tab will be created for each new one.
- **Read New Tab (Dual)**: The new folder will be opened in a new folder tab in the other file display.

You can also hold the appropriate qualifier key when clicking the **OK** button, rather than dropping down the menu.
