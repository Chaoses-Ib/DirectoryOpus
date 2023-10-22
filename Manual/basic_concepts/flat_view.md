# Flat View

Flat View is a mode you can turn on in a Lister that enables you to view all the contents of a folder's sub-folders at once. In effect it collapses, or flattens, the display of a nested hierarchy of folders and files into a single folder.

You can turn Flat View on using the ![](/Manual/images/media/flatviewbutton.png) button on the default toolbar - this enables *Grouped* mode. The **Folder** menu has a *Flat View* sub-menu that gives you access to the other modes. You can also configure **[Lister Styles](the_lister/styles.md)** that automatically switch Flat View on when you switch to them.

The three different types of Flat View mode are:

- **Mixed**: Displays the contents of the current folder and all its sub-folders (and all their sub-folders, and so on recursively) as if they were all in the one location.
- **Mixed (No Folders)**: Displays all the files in the current folder and all sub-folders as if they were all in the one location. Sub-folders themselves are hidden from the display.
- **Grouped**: Displays the contents of all sub-folders as a tree hierarchy.

The following screenshots illustrate the differences between the modes.

![](/Manual/images/media/flat_1.png) 

In the starting folder, with Flat View off, all we can see is that there are three sub-folders. We have no idea what the contents of those folders might be.

![](/Manual/images/media/flat_2.png) 

Turning on **Flat View - Mixed** causes Opus to read the contents of all sub-folders (recursively) and add them to the list. Instantly we can see that below the top-level, there are three additional sub-folders, and that somewhere in the hierarchy there are also three image files. The **Location** column, which is displayed in Flat View mode by the default settings in the [Folder Formats](folder_options/folder_formats.md) system, displays the location of each item, relative to the base folder.

![](/Manual/images/media/flat_3.png) 

**Flat View - Mixed (No Folders)** removes all folders from the display, leaving only the files behind. This can be very useful if you want to quickly see what files are contained in a directory structure but don't care so much about the which folders the files are in (although the **Location** column does still display this information).

![](/Manual/images/media/flat_4.png) 

Finally, **Flat View - Grouped** mode displays a representation of the actual directory structure. The indenting makes the relative location of items immediately obvious - you can see instantly that the **Argentina_0004.jpg** file is in the folder **four**, which is itself inside the folder **one**.

For the most part you don't have to treat a Lister that's in Flat View mode any differently to any other - you can double-click, drag-and-drop, view, copy, and delete files in the same way you normally do. You can use drag-and-drop to move or copy files into nested sub-folders - you can even move files from one sub-folder to another in this way. One thing to keep in mind is that if you drop a file into the file display - but **not** onto a sub-folder - then the base folder will be used as the target. Normally when you drag a file you can't drop it in the source folder - as this would be a no-op - but in Flat View you can do this, and one effect of this is that it can be easy to accidentally move a file from a nested sub-folder to the base folder without necessarily meaning to. You can always undo such operations, but it's worth remembering this is a possibility.

The only real difference in file operations in Flat View mode comes when you copy files from within sub-folders (via drag-and-drop, copy-and-paste or using the **Copy Files** command). For example, say you select the three image files in the above screenshot, and drag them to another Lister. Opus will display a dialog asking how you want to perform the copy:

![](/Manual/images/media/flat_copy.png) 

If you choose the **Recreate** option, Opus will recreate the source folder structure (relative to the base folder) in the destination. In the above example, this means in the destination it would create a folder called **one**, a sub-folder inside that called **four**, and then copy the **Argentina_0004.jpg** file into it. The **Same Folder** option discards the source folder structure - all files would be copied directly into the target folder. One complication that can arise with this is if you have selected files with the same name from multiple sub-folders. In the source directory structure this would be no problem, as they would all be in separate folders, but if you try to copy them all to the same target folder the names would clash. In this case Opus will prompt you to rename or skip over the clashing files.
