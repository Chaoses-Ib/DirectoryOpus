# Calculating Folder Sizes

Normally on Windows, only the size of files is easily visible - the (total) size of folders is not usually displayed. This is mainly because the file system does not keep track of the total size of a folder. Instead, displaying a size for a folder involves reading the contents of that folder (and all its sub-folders, recursively) and adding up the total size. There are two ways you can trigger this behaviour in Directory Opus - manually and automatically. Either way, whenever the size of a folder is calculated, Opus displays it in the normal size column along with file sizes.

![](/Manual/images/media/folder_sizes.png) 

To manually calculate the size of one or more folders, the simplest method is to select the folders in question, and then choose the **Calculate Folder Sizes** command from the **Edit** menu (or press **Ctrl+K**, or **Ctrl+L** if your toolbars date from an older version). If you execute this command with no folders selected, the size of all sub-folders in the current file display will be calculated.

Another way to calculate the size of a single folder is to hover over it with the mouse until its tooltip appears. The default tooltip for folders contains the **{foldersize}** code, and so displaying a folder's tooltip triggers the counting of its contents. Using this method you have to keep the mouse over the folder (and thus keep the tooltip visible) until the counting is complete. This method may not work, however, if the [info tip](/Manual/file_types/filetype_editor/info_tip.md) for folders has been modified to remove this code.

Opus can also be configured to automatically calculate the size of sub-folders whenever a folder (or certain folders) is read. The **[Folders / Folder Behaviour / Calculate folder sizes automatically](/Manual/preferences/preferences_categories/folders/folder_behaviour.md)** option controls this globally - through this Preferences option you can enable automatic folder size calculation for certain types of drives. You can also control automatic calculation on a per-folder basis using the [Folder Formats](../folder_options/folder_formats.md) system - the **Get folder sizes **switch on the **Options** tab of the **[Folder Options](../folder_options/RAEDME.md)** dialog lets you turn counting on or off for any folder.

While a folder's size is being calculated, the size field is progressively updated - you will see a tilde character in front of the size to indicate that the displayed size is only approximate.

![](/Manual/images/media/folder_sizes_2.png) 

The tilde is also used to indicate that a folder contained one or more sub-folders that could not be read (for example, due to permissions set to deny read access).
