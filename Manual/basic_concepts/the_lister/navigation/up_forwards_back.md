# Up, Forward, Back

It's common to use a directional nomenclature when discussing navigation of the file system. As you would know, the file system is presented as a hierarchy of folders. For example, consider the following path:

    C:\FolderOne\FolderTwo\FolderThree

In this path, *C:\\* is the root folder, *FolderOne* is a child of C:\\ *FolderTwo* is a child of *FolderOne*, and *FolderThree* is a child of *FolderTwo*. Another way of representing this hierarchy would be:

    C:
    FolderOne
    FolderTwo 
    FolderThree

If you start in *C:* and then double-click on *FolderOne* to go into it, you can be said to have gone **down** in the folder hierarchy. It therefore follows that going from *FolderOne* to *C:* is moving **up** in the hierarchy. And in fact, that's what the **Up** function does - it navigates you from the current folder to the current folder's parent. From any folder you can go up repeatedly, until you reach the **Desktop**, which is the root of the Windows file system. There are no folders higher up in the hierarchy than the **Desktop** folder, and so the **Desktop** is the only [^1] place you can't go up from.

There are a number of ways in a Lister to go **Up**. The easiest is to click the **Up** button on the default location bar:

![](/Manual/images/media/13/go_up_button.png)

In the file displays, you can optionally choose to show a special \<ib:inline-code\>`..`\</ib:inline-code\> folder entry that corresponds to the parent folder. [If this is turned on](/Manual/preferences/preferences_categories/file_displays/navigation.md), double-clicking it will navigate up to the parent folder.

You can also go **Up** using the keyboard - pressing the <kbd>Backspace</kbd> key in a Lister will navigate you to the parent folder.

------------------------------------------------------------------------

As you move from folder to folder in a file display, a list of the locations you have visited is remembered. This is called the **[History](recent_and_history_lists.md)** list. A **History** list is kept for each file display (and if multiple tabs are open, for each tab in the file display). You can use the **Back** and **Forward** buttons to move within the **History** List:

![](/Manual/images/media/13/back_forward_button.png)

If you have a keyboard or mouse with a **Back** or **Forward** button on it, Opus will also recognise these and perform the appropriate action. Click the drop-down arrow to the right of the back and forward buttons displays the history list (the part of it that is either before or after your current location) in a drop-down menu.

[^1]: This is not strictly true in Opus; it is possible to have folder hierarchies that don't start under the Desktop. For example, File Collections and FTP can both be displayed in the tree with their own root items.
