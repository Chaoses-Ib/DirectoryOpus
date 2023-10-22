# Manual Sorting # Manual Sorting

Manual sorting refers to being able to control the display order of files and folders arbitrarily. Although for most purposes the automatic sorting methods (e.g. sorting files alphabetically by name) are all you need, many people have use cases where being able to control the sort order exactly would be useful.

Manual sort mode needs to be activated in a Lister before files can be arbitrarily arranged. Right-click the column header and use the Manual Sorting options to activate manual sorting mode.

![](/Manual/images/media/manual_sort_menu.png)

  
You can also turn on the *Sorting Options / Manual sorting* option on the *Display* tab in the Folder Options dialog. Obviously as a folder options setting, this mode can also be made permanent by saving the folder format.

If a manual sort order had previously been defined (and saved) for the current folder, the file list will resort automatically when manual sorting is turned on. Otherwise, turning on manual sorting will have no immediate effect on the file list.

In details or power mode, or when the column header is enabled in the other modes, a new button ( ![](/Manual/images/media/image024.png) ) appears on the left of the column header when in manual sort mode. Clicking this button displays a control menu with a few commands in it relating to manual sort mode:

![](/Manual/images/media/image025.png) 

# Manual Sorting # Manual Sorting

Once manual sort mode is active, you can reposition a file using drag-and-drop, or from the keyboard using **Shift + Alt** in conjunction with the cursor keys.

![](/Manual/images/media/image027.png)

By default, your manual sort order will be persistent (saved automatically), whenever possible (see below for current limitations on manual sorting). If you want the freedom to change the sort order temporarily without making it permanent, you can turn off the *Folders / Folder Behaviour / Automatically save manual sort order where possible* option in Preferences. With that option turned off, you need to use the **Save Sort Order** command in the control menu.

At any time, you can reset the sort order to the current automatic order (e.g. alphabetical by name) using the **Reset Sort Order** command in the control menu (shown above).

# Manual Sorting

By default you’re limited to just a single manual sort order per folder but if you need to be able to define more than one, you can add “named orders” through the *Miscellaneous / Advanced / manual_sort_names* option in Preferences.

![](/Manual/images/media/image028.png)

When named orders are defined they appear in the column header’s control menu, letting you switch between them at will.

![](/Manual/images/media/image030.png)

The Folder Options dialog also displays a drop-down (on the *Display* tab) showing all the named sort orders, which lets you select the default for a folder if desired. # Manual Sorting # Manual Sorting

Cloud Storage folders on local drives generally *do* allow sort orders to be saved, but be aware that the sorting metadata is unlikely to be synched to the cloud and other computers.

Manual sort orders cannot be saved at all for some types of folders:

- Non-NTFS disk folders (e.g. FAT/FAT32, some non-Windows NAS devices)

- Archives

- FTP

By default, manual sorting is disabled completely in folders that the order can’t be saved for. If you turn on the *Folders / Folder Behaviour / Allow manual sorting in all folders* Preferences option then manual sorting will be available everywhere, but changes to the sort order in those types of folders will only be temporary.

Manual sorting is currently not supported in Flat View or when the file display is grouped. It will also not work correctly in a folder when compatibility files are displayed and there are two files with the same name.
