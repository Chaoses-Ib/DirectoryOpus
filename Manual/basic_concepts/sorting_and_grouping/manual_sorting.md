# Manual Sorting

Manual sorting refers to being able to control the sort order of files and folders arbitrarily. Although for most purposes the automatic sorting methods (e.g. sorting files alphabetically by name) are all you need, many people have use cases where being able to control the sort order exactly would be useful.

### Activating manual sort mode

Manual sort mode needs to be activated in a file display before files can be arbitrarily arranged. Right-click the column header and use the **'Sort By / Manual Sorting** options to activate manual sorting mode.

![](/Manual/images/media/13/manual_sort_menu.png)

You can also turn on the **Manual sorting** option on the *Sorting* tab in the [Folder Format](../folder_options/README.md) dialog. Manual sort mode can be made permanent by saving the folder format.

### No immediate effect is normal

If a manual sort order had previously been defined (and saved) for the current folder, the file list will resort automatically when manual sorting is turned on. Otherwise, turning on manual sorting will have no immediate effect on the file list.

### Repositioning items

Once manual sort mode is active, you can reposition a file using drag-and-drop, or from the keyboard using **Shift + Alt** in conjunction with the cursor keys.

![](/Manual/images/media/13/manual_sort_repos.png)

### Control menu in header

In details or power mode, or when the column header is enabled in the other modes, a new button appears on the left of the column header when in manual sort mode. Clicking this button displays a control menu with a few commands in it relating to manual sort mode:

![](/Manual/images/media/13/manual_sort_control.png) 

### Persistent sort order

By default, your manual sort order will be persistent (saved automatically), whenever possible (see below for current limitations on manual sorting). If you want the freedom to change the sort order temporarily without making it permanent, you can turn off the **Automatically save manual sort order where possible** option on the [Filtering and Sorting / Sorting](/Manual/preferences/preferences_categories/filtering_and_sorting/sorting.md) page in Preferences.

If automatic saving is turned off, the control menu button turns red whenever the sort order has changed, and you need to use the **Save Sort Order** command in the control menu to save your sort order.

### Resetting the sort order

At any time, you can reset the sort order to the current automatic order (e.g. alphabetical by name) using the **Reset Sort Order** command in the control menu.

### Multiple manual sort orders

By default you’re limited to just a single manual sort order per folder but if you need to be able to define more than one, you can add “named orders” with the **manual_sort_names** option on the [Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md) Preferences page.

When named orders are defined they appear in the column header’s control menu, letting you switch between them at will.

The Folder Format dialog also displays a drop-down (on the *Sorting* tab) showing all the named sort orders, which lets you select the default sort name for a folder if desired.

### Sort order can't always be saved

Manual sort orders cant be saved at all for some types of folders:

- Non-NTFS disk folders (e.g. FAT/FAT32, some non-Windows NAS devices)
- Archives
- FTP

By default, manual sorting is disabled completely in folders that the order can’t be saved for. If you turn on the **Allow manual sorting even when the order can't be saved** option on the [Filtering and Sorting / Sorting](/Manual/preferences/preferences_categories/filtering_and_sorting/sorting.md) page in Preferences then manual sorting will be available everywhere, but changes to the sort order in those types of folders will only be temporary.

### Manual sort order in cloud folders

Cloud storage folders on local drives generally *do* allow sort orders to be saved, but be aware that the sorting metadata is unlikely to be synched to the cloud and other computers.

### Not supported in some modes

Manual sorting is currently not supported in Flat View or when the file display is grouped.
