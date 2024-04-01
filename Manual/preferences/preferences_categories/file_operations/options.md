# Options

This page contains miscellaneous options relating to file operations.

- **Deselect files used in functions**: Normally when you select one or more files and then invoke some sort of function on them (e.g. copy them to another folder), Opus deselects the files involved in the function automatically. If you turn this option off, the files will remain selected so that you can perform additional operations on them without having to reselect them.          
  - **Postpone file deselection until end of function**: In conjunction with the above option - the files will not be deselected until the function has finished. With this option off, the files would be deselected as soon as the function is invoked. When this option is on, the function only maintains a "weak" connection to the files involved - as soon as you click in the Lister or do anything else that involves selecting or deselecting files, the link is broken and the files will no longer be automatically deselected.
- **Detect external file changes on network drives**: This option causes Opus to monitor network folders for changes made by other programs. For example, if you use a third-party archiving tool in a network folder, Opus would not detect any files it created in a network share unless this option was on. Monitoring network drives like this can result in reduced network performance (some file systems are worse than others) and so you may want to turn this off - you can always manually refresh a file display by pressing <kbd>F5</kbd>.
- **Shutdown Directory Opus when all functions finish**: Opus will shutdown automatically once you close the last Lister and no functions are running in the background. This makes Opus behave more like a traditional application that you run, use and then exit when finished with. We recommend that you keep Opus running in the background even when you're not using it as it makes it much quicker to open Listers, and means things like [system-wide hotkeys](/Manual/additional_functionality/system-wide_hotkeys.md) and [floating toolbars](/Manual/additional_functionality/floating_toolbars/README.md) can work, but if you don't want to use it like this you can turn this option on.
- **Maximum undo entries**: The maximum number of operations that will be shown in the [undo list](/Manual/file_operations/tracking_and_undoing_file_operations.md).

### Use template when creating shortcuts

This template is used to define the new name of a shortcut to an existing file or folder (for example, when you drag & drop a file with the right button and choose *Create Shortcut Here* from the context menu). You can use two codes in the template string to insert information:

- **%1**: Inserts the original file name.
- **%2**: Inserts the shortcut count in brackets (if greater than one).

For example, the default template is `%1 - Shortcut %2`. Say you pick a file "Document.txt" and make a shortcut to it.

The first shortcut in that location has a "shortcut count" of 1, which is not shown - so `%2` will expand to nothing. The first shortcut's name would be <nobr>`Document - Shortcut.lnk`</nobr>.

If you make a second shortcut, the count would be 2, and the new filename would be <nobr>`Document - Shortcut (2).lnk`</nobr>.
