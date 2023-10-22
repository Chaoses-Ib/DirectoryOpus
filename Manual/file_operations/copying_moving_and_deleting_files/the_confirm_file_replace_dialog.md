# The Confirm File Replace Dialog

When copying files around, you'll often encounter the case where the file you're copying already exists in the target folder. In this case Opus normally displays the **Confirm File Replace** dialog, asking you what to do.

![](/Manual/images/media/file_replace.png)

The goal of this dialog is to show you enough information about the existing file (the one that already exists in the target folder) and the new file (the one you are copying) to help you decide what action to take.

The basic information that's presented for the two files is **Name**, **Location**, **Size**, **Date** (the last modified date) and **Desc** (the file's description). When this information is different between the two files it is displayed in **bold**, making it easier to see at a glance how the two files differ (except for the locations, since they are almost always different and highlighting them would make the more important differences harder to notice). The dialog also uses two little icons to indicate which file is larger (![](/Manual/images/media/replace_-_larger.png)) and which is newer (![](/Manual/images/media/replace_-_newer.png)).

If possible, thumbnail images are also displayed for the two files - if not, the file's icon will be displayed. The thumbnails (or icons) have some additional functionality:

- If a thumbnail is displayed for the file, hovering the mouse over the top of it will display a larger preview image.
- You can right-click the thumbnail or icon to display the context menu for the file.
- You can double-click the thumbnail or icon to open the file. When the **Confirm File Replace** dialog has been displayed, there are several actions you can take. Fundamentally, you need to decide if you still want to copy the file or not.

If you **do** still want to copy the file, your available choices are:

![](/Manual/images/media/replace_-_replace.png)

- **Replace:** Copy the incoming file over the top of the existing one. You can click the main part of the button to do this. Alternatively, click the arrow on the right of the button to open the menu, then choose the first option.
- **Replace All:** Replace the current file, and automatically replace any subsequent clashing files for the remainder of the operation. You can use the menu to choose this or, as a shortcut, hold the **Shift** key while clicking the **Replace** button.
- **Rename New:** Automatically choose an alternative name for the incoming file, so both it and the existing file will exist side-by-side. (To manually specify the new name, see below.) As a shortcut, the menu item can be accessed by holding **Ctrl** while clicking the button.
- **Rename New (All):** Automatically choose an alternative name for the incoming file, and all subsequent clashing files. As a shortcut, hold **Ctrl+Shift**.
- **Rename Old:** Automatically choose an alternative name for the existing file, so both it and the incoming file will exist side-by-side. As a shortcut, hold **Alt+Ctrl**.
- **Rename Old (All):** Automatically choose an alternative name for the existing file, and all subsequent clashing files. As a shortcut, hold **Alt+Shift**.
- **Keep Newer:** Copy the incoming file over the top of the existing file, but only if the incoming file was modified more recently than the existing one. Otherwise, leaving the existing file alone and do not copy the incoming file at all. (This is done by comparing the **modified** timestamps of the two files. In the case of a tie, where both timestamps are identical, the incoming file is skipped.)
- **Keep Newer (All):** For this and all subsequent clashes, copy the incoming file over the top of the existing file if the incoming file was modified more recently, and skip it otherwise.

In addition to the automatic rename options discussed above, you can also manually edit the incoming file's name. The **Replace** button changes to a **Rename** button if the name has been edited, and clicking the button will copy the incoming file with the specified name and leave the existing file as it was.

![](/Manual/images/media/replace_-_rename.png)

The new file's **Name** is an edit field and, similar to the [Inline Rename](../renaming_files/inline_rename.md) function, this edit field responds to a few control keys that let you quickly select parts of the filename: **Ctrl+A** (select all), **Ctrl+F** or **Ctrl+N** (select file stem) and **Ctrl+E** (select file extension). You can also transform the selected text with **Ctrl+L** (lower-case all), **Ctrl+U** (upper-case all), **Ctrl+W** (capitalize all words), **Ctrl+P** (capitalize first word), or **Ctrl+.** (replace dots and underscores with spaces; dots with numbers on both sides are left alone; use the key on the main keyboard, not the numeric keypad).

If you decide you **do not** want to copy the file after all, the available choices are:

![](/Manual/images/media/replace_-_skip.png)

- **Skip:** Skip over this file. The incoming file is not copied and the existing file is left alone. You can click the main part of the button to do this. Alternatively, click the arrow on the right of the button to open the menu, then choose the first option.
- **Skip All:** Skip over this file, and skip all subsequent clashing files for the remainder of the operation. You can use the menu to choose this or, as a shortcut, hold the **Shift** key while clicking the **Skip** button.
- **Skip Identical:** Skip over this file, and any subsequent files, if the incoming and existing files have identical **size** and **modified** timestamp. *Note that the actual file contents are not compared!* You will still be prompted for subsequent clashes where the two files have different sizes or Modified timestamps. You can hold **Ctrl** and click the button as a shortcut.

You can also abort the whole operation by clicking the **Abort** button or closing the dialog.

The context menu displayed when right-clicking a file's thumbnail (or icon) can be customized using the [File Types](/Manual/file_types/RAEDME.md) system. For example, you could add a command to compare the two files using an external comparison tool.

If you are copying a file to or from an [FTP site](/Manual/ftp/RAEDME.md), and the remote FTP server supports *resume*, you will also have the choice to **Resume** the copy (as well as a drop-down for **Resume All**). If you select the **Resume** option Opus will attempt to resume the file transfer where it was (presumably) interrupted previously. For example, if the file you are copying is 100 KB and the existing file is only 50 KB, Opus would start transferring data from the 50 KB mark. This option will only be available if the existing file is smaller than the new one. You need to be sure of what you're doing when you select this option, as it would be very easy to wind up with a corrupted file if you accidentally resume copying the wrong file.
