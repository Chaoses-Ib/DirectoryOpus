# File Operations Options

This page contains miscellaneous options relating to file operations.

- **Append " - Shortcut" when creating shortcuts**: Lets you control whether a suffix is automatically added to the names of shortcuts that Opus creates using the **Copy MAKELINK** command (e.g. when you drag & drop a file with the right button and choose *Create Shortcut Here* from the context menu).  
  \* **Deselect files used in functions**: Normally when you select one or more files and then invoke some sort of function on them (e.g. copy them to another folder), Opus deselects the files involved in the function automatically. If you turn this option off, the files will remain selected so that you can perform additional operations on them without having to reselect them.          

- **Postpone file deselection until end of function**: In conjunction with the above option - the files will not be deselected until the function has finished. With this option off, the files would be deselected as soon as the function is invoked. When this option is on, the function only maintains a "weak" connection to the files involved - as soon as you click in the Lister or do anything else that involves selecting or deselecting files, the link is broken and the files will no longer be automatically deselected.

- **Detect external file changes on network drives**: This option causes Opus to monitor network folders for changes made by other programs. For example, if you use a third-party archiving tool in a network folder, Opus would not detect any files it created in a network share unless this option was on. Monitoring network drives like this can result in reduced network performance (some file systems are worse than others) and so you may want to turn this off - you can always manually refresh a file display by pressing **F5**.  

�
