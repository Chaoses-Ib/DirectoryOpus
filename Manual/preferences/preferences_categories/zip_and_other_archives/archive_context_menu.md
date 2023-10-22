# Context Menu

Opus can add items to the context menu for files and folders that lets you access its archiving capabilities. This page lets you choose whether such items are added, and which ones.

Use the **Enable Archive context menu** option at the top of the page to enable or disable the context menu support. The list of options below that is grouped into five sections:

- **Add to Archive**

The options in this section will add context menu items that invoke the [Add to Archive](/Manual/file_operations/creating_archives/adding_to_archives.md) dialog box for the selected files. The Add to Archive dialog lets you choose the archiving format to use, so you really only need one option from this section selected. The format you select here will be the default when the dialog box opens, so you can turn on multiple formats in order to have a quick way of invoking the dialog with the format already chosen.

![](/Manual/images/media/archive_context_-_add_menu.png)  
\* **Add to Named Archive**

The options in this section will add context menu items that immediately create archives in the specified format. The name of the new archive will be based on the first selected item. You won't have any way to control archiving options using these commands - the archives are created immediately.

**![](/Manual/images/media/archive_context_-_add_immediate.png)\\**

- **Archive and Email**

These options add context menu commands that archive the selected files and send them automatically as an email (using the settings on the [Email](../internet/email.md) page).  
\* **Extract**

These options add context menu commands that let you extract archive contents.

      * **Extract from archives**: When you right-click on a file in a format that Opus recognizes (or drag and drop such a file with the right mouse button), Opus will add context menu items to let you extract the archive contents to the current folder. 
      * **Convert to Self-Extracting Archive**: When you right-click on a Zip file, Opus will add a command that lets you convert the file to a [[:file_operations:creating_archives:zip_files:self-extracting_zip_files|self-extracting archive]]. This is only available for Zip archives.\\
    * **Options**

This section contains options that affect the archive context menus.  
\* **Add single folders as sub-folders of new archives**: Changes what happens when you right-click a single folder and choose one of the **Add to Named Archive** context menu commands. When on, the folder itself will be included in the archive, with the folder's contents below it. (e.g. *Folder.zip/Folder/File.txt*) When off, the *contents* of the folder, but not the folder itself, are added to the archive. (e.g. *Folder.zip/File.txt*) When zipping multiple folders, or when creating archives via something other than the **Add to Named Archive** context menu commands, any selected folders are always included at the top level of the archive. In particular, note that the **Add to Archive** context menu command is not affected by this option.

      * **Cascade context menu items**: If this option is turned on, the archive commands that Opus adds to context menus will be displayed in a sub-menu instead of on the top level of the menu. 
      * **Display context menus in Explorer as well as Opus**: If this is turned on then the context menu items added through this page will also be shown when you right-click on files in Explorer. If turned off, the context menus will only be shown in context menus within Opus. 
      * **Display icons in context menus**: Adds icons to each context menu item. 

  
