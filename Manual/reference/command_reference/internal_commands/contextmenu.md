# ContextMenu

The **ContextMenu** command can be used to:

- Display a list of the context menu commands that are available for selected files, and
- Trigger a context menu command for selected files without needing to first display the context menu (so you can, for example, configure a button or hotkey to execute a command that is normally only available from the context menu)

The first step in using the **ContextMenu** command is to select the file (or a file of the type) in question and use the **SHOWCMDS** argument to view the available context menu commands. The easiest way to do this (unless you want to set up a button dedicated to this) is to use the **[find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md)** field in **Command** mode.

![](/Manual/images/media/contextmenu_via_fayt.png)

Opus will display a dialog containing a list of the available context menu commands. Context menu commands have an ID number and some may also have a "verb" - a plain text string that you can use to invoke the command. If a command has a verb displayed you should use this in preference to the ID, as it's possible for the ID number to change if additional context menu extensions are installed. You can also trigger a command by its label using the **LABEL** and **LABELRAW** arguments (and these can optionally use wildcards or regular expressions).

![](/Manual/images/media/contextmenucmds.png)

The *Context Menu Commands* dialog can automatically create a command line for you - right-click on the command in question, or click the **Copy Command** button to copy the command line to the clipboard.

You can see from this example that the list of commands has been filtered to show only those containing the string "sync" - this has returned two, which are Dropbox Smart Sync commands. The first one has a verb and the second one, for some reason, doesn't. Because the verb isn't consistent it might be better to use the label to trigger this command; for example, you could use **ContextMenu LABEL="Smart Sync\Local"** to run the first command and **ContextMenu LABEL="Smart Sync\Online Only"** to run the second.

Once you know what the verb, label or ID is for the command you want to automate, you can configure your button or hotkey with the appropriate **ContextMenu** command.

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| CTRL | /S | *(no value)* | When invoking a context menu command, tells the command handler to act as if the Ctrl key is held down. What difference this makes (if any) is up to the handler.<br /><br />*Example:* `ContextMenu CTRL VERB="delete"` |
| EXTENDEDVERBS | /S | *(no value)* | Enables support for *extended verbs*. These are context menu commands that are normally only displayed when the **Shift** key is held down.<br /><br />*Example:* `ContextMenu SHOWCMDS EXTENDEDVERBS`<br /><br />If you use this while invoking a command, you will probably also want to specify the **SHIFT** argument.<br /><br />*Example:* `ContextMenu EXTENDEDVERBS SHIFT VERB="delete"` |
| FILE | /K/M | *\<filename\>, ...* | Specify the file or files to operate on. If not specified the command will operate on all currently selected files.<br /><br />You can use this to execute commands on non-filesystem items, for example the Recycle Bin. To do this requires knowing the item's GUID, which unfortunately is beyond the scope of this help file - but as an example, the GUID for the Recycle Bin is **{645FF040-5081-101B-9F08-00AA002F954E}.** The following command will execute the "empty" verb on the Recycle Bin, causing it to empty.<br /><br />*Example:* `ContextMenu FILE=::{645FF040-5081-101B-9F08-00AA002F954E} VERB=empty` |
| ID | /K/N | *\<command ID\>* | Specify the ID of the context menu command to execute.<br /><br />You should use an item's verb or label (in that order, if it has either) in preference to its ID, because the ID may change (with the old ID potentially representing a completely different action) when you add or remove software, or even each time the menu is used.<br /><br />*Example:* `ContextMenu ID=79` |
| ITEMMENU | /O | *(no value =* **yes***)***  <br />no** | (Windows Vista and above. Has no effect on Windows XP.)<br /><br />Note that by default this option is *on* unless the command is being invoked from a background context menu. You can specify the argument yourself (with either **yes** or **no** parameters) if you wish but normally the default behaviour will be acceptable.<br /><br />**ITEMMENU** mode indicates that you wish to list or invoke context menu commands in the same way as when a file or folder is right-clicked. Without **ITEMMENU** mode you can usually only list or run commands which only appear when you right-click the background of a folder window.<br /><br />The exact difference (if any) that **ITEMMENU** makes is up to the individual command handlers. As with the **EXTENDEDVERBS** argument, some handlers will filter their menu items in or out depending on the mode.<br /><br />*Example:* `ContextMenu ITEMMENU=yes VERB="PreviousVersions"` |
| LABEL | /K | *\<label\>* | Specify the label of the context menu command to execute.<br /><br />It is better to specify the command's verb, using the **VERB** argument, instead of its label, but not all commands have verbs. (Not all commands have labels, either. Context menu handlers which draw their own items may not provide the labels in a form which Opus can read.) Labels, unlike verbs, are typically language-dependent and may change between versions of software or when different files are selected. Using the label is still preferable to using the ID, however.<br /><br />You can use the **REGEXP** or **WILD** arguments if you need to match the label using a pattern, which is most often needed when the label includes part of the selected filename.<br /><br />When searching for the label in a menu with sub-menus, Opus will check all of the top-level items first, then the items directly below the top-level sub-menus, then any items nested three levels deep, and so on.<br /><br />*Example:* `ContextMenu LABEL="Quarantine file"` |
| LABELRAW | /K/R | *\<label\>* | This is the same as the LABEL argument except that it is a "raw" argument which swallows the remainder of the command line. You can use this to specify labels which have embedded quotation marks.<br /><br />*Example:* `ContextMenu LABELRAW Add To "Zip" File...` |
| LOOKUP | /S | *(no value)* | Use in conjunction with the **VERB** argument to make Opus lookup the verb's ID on-the-fly instead of simply passing the verb name to the command handler. You should not normally have to do this but some context menu handlers have bugs that prevent them from doing the lookup themselves.<br /><br />*Example:* `ContextMenu WANTSYNC LOOKUP VERB="PickLinkSource" FILE "C:\Template Folder"` |
| REGEXP | /S | *(no value)* | Used in conjunction with the **LABEL** argument to specify that the label string is a regular expression.<br /><br />*Example:* `ContextMenu REGEXP LABEL="Add to .\*\\zip.\*"` |
| SHIFT | /S | *(no value)* | When invoking a context menu command, tells the command handler to act as if the Shift key is held down. What difference this makes (if any) is up to the handler. If you use this then you'll probably also want to use **EXTENDEDVERBS** as holding down the shift key also normally causes the extended verbs to be shown, and the menu handler may expect both to be used together.<br /><br />*Example:* `ContextMenu SHIFT EXTENDEDVERBS VERB="delete"` |
| SHOWCMDS | /S | *(no value)* | Displays a list of context menu commands for the selected files. Depending on the context menu handlers installed on your system, the list of commands you get back may differ based on the **EXTENDEDVERBS** and **ITEMMENU** arguments; if you use either of them when finding a command then you should do the same when running that command.<br /><br />*Example:* `ContextMenu SHOWCMDS` |
| VERB | *default* | *\<verb\>* | Specify the verb of the context menu command to execute. This is the default argument for the **ContextMenu** command, so the keyword **VERB** does not need to be specified.<br /><br />*Example:* `ContextMenu PreviousVersions`<br /><br />*Example:* `ContextMenu VERB="SevenZipCompressEmail"` |
| WANTSYNC | /S | *(no value)* | Requests that the context menu command be run synchronously. In other words, any other commands should wait until the context menu command has completed, instead of running in parallel. This is just a request and the context menu handler may ignore it. Similarly, context menu handlers may choose to run things synchronously even when this argument is not specified.<br /><br />*Example:* `ContextMenu WANTSYNC LOOKUP VERB="DropHardLinkClone" FILE {sourcepath\$}` |
| WILD | /S | *(no value)* | Used in conjunction with the **LABEL** argument to specify that the label string is a wildcard expression.<br /><br />*Example:* `ContextMenu WILD LABEL="Add to \*.zip\*"` |
