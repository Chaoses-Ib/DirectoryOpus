# Folder Sizes

Normally on Windows, only the size of files is easily visible - the (total) size of folders is not usually displayed. This is mainly because the file system does not keep track of the total size of a folder. Instead, displaying a size for a folder involves reading the contents of that folder (and all its sub-folders, recursively) and adding up the total size.

##### Folder size calculation

Opus can calculate the size of folders and display it in the file list just like it does for file sizes.

> [!NOTE]
> If you have [Everything by voidtools](https://voidtools.com) installed, Opus can use its search index to perform this calculation significantly faster for indexed locations.

There are two ways you can trigger this behaviour in Directory Opus - manually and automatically.

##### Triggering manual calculation

To manually calculate the size of one or more folders, the simplest method is to select the folders in question, and then choose the **Calculate Folder Sizes** command from the **Edit** menu (or press <kbd>Ctrl+K</kbd>). If you execute this command with no folders selected, the size of all sub-folders in the current file display will be calculated.

Another way to trigger manual calculation of a single folder is to hover over it with the mouse until its tooltip appears. The default tooltip for folders contains the `{foldersize}` code, and so displaying a folder's tooltip triggers the counting of its contents. Using this method you have to keep the mouse over the folder (and thus keep the tooltip visible) until the counting is complete. This method may not work, however, if the [info tip](/Manual/file_types/filetype_editor/info_tip.md) for folders has been modified to remove this code.

##### Automatic calculation

Opus can also be configured to automatically calculate the size of sub-folders whenever a folder (or certain folders) is read. The options on the [Folders / Folder Sizes](/Manual/preferences/preferences_categories/folders/folder_sizes/README.md) Preferences page control this.

##### Folder sizes can be inaccurate

You should look at folder sizes as a guide, rather than an exact size like you do for a file. Folder permissions can mean Opus isn't able to access some folders to count them. Junctions and softlinks can also cause confusion - Opus lets you control whether they're counted or not, but neither way is "right" or "wrong" and the calculated size can vary significantly at times.

Sometimes you may see a folder size shown with a tilde (`~`) character in front of it. This indicates the displayed size is only approximate. This can happen for two reasons:

- While a folder's size is being calculated, the size field is progressively updated - the tilde indicates the calculation isn't complete
- The tilde is also used to indicate that a folder contained one or more sub-folders that could not be read (for example, due to permissions set to deny read access).

Note than when using Everything to calculate folder sizes, you usually won't see a tilde, again for two reasons:

- The calculation is almost instantaneous, so there's no progressive update
- The Everything index includes some folders that applications like Opus can't normally access, so permissions errors are much less likely

Because of this second reason you may get different results using Everything to calculate sizes versus Opus doing it the old-fashioned way.
