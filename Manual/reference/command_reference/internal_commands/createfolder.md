# CreateFolder

The **CreateFolder** internal command is used to:

- [Create new folders](/Manual/file_operations/creating_folders.md) (either via a dialog, an inline rename field in the file display, or with a pre-determined name)
- [Create new archive files](/Manual/file_operations/creating_archives/README.md)
- Create new [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md), [collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) and [stored query collections](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.md)

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ARCHIVE</td><td>
/O</td><td>

*(no value)*</td><td>

Create a new archive file. The archive format will default to .zip but can be changed via the dialog.

*Example:* `CreateFolder ARCHIVE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<archive format\>*</td><td>

Create a new archive file of the specified format.

*Example:* `CreateFolder ARCHIVE=.7z`
</td></tr><tr><td>
ARCHIVEARGS</td><td>
/K</td><td>

*\<archive arguments\>*</td><td>

Used to pass format-specific arguments when creating an archive. The format these arguments take is defined by the plugin and archive type in question - currently, none of the standard archive formats Opus supports make use of this.

*Example:* `CreateFolder ARCHIVE=.moo ARCHIVEARGS="/compression=1"`
</td></tr><tr><td>
ASK</td><td>
/S</td><td>

*(no value)*</td><td>

If you specify a name with the **NAME** argument the *Create Folder* dialog does not normally display; instead the folder is created immediately. You can add the **ASK** argument to force the dialog to display, pre-populated with the specified name.

*Example:* `CreateFolder "My New Folder" ASK`

If the specified name already exists before the prompt is displayed, it will have a number appended to it automatically so that is unique, similar to the way **CreateFolder** without any arguments will prompt to create *New Folder* and then *New Folder (2)*, *New Folder (3)*, and so on.
</td></tr><tr><td>
COLLQUERY</td><td>
/S</td><td>

*(no value)*</td><td>

Creates a stored query collection rather than a regular file collection. This only has effect when actually creating a collection (because, for example, you are in the File Collections root folder at the time).

*Example:* `CreateFolder COLLQUERY`
</td></tr><tr><td>
FROMCLIPBOARD</td><td>
/O</td><td>

*(no value)*</td><td>

Uses the text currently on the clipboard for the name of the new folder. Equivalent to <nobr>`CreateFolder "{clip}"`</nobr>.

*Example:* `CreateFolder FROMCLIPBOARD`
</td></tr><tr><td>
</td><td>
</td><td>

**multi**</td><td>

Creates multiple folders from the clipboard contents, assuming the clipboard contains multiple lines of CR/LF separated text. Without this keyword only the first line would be used.

*Example:* `CreateFolder FROMCLIPBOARD=multi`
</td></tr><tr><td>
INLINE</td><td>
/S</td><td>

*(no value)*</td><td>

Creates a new folder and lets you edit its name inline (in the file display) - equivalent to selecting *New -\> Folder* from the context or File menu.

*Example:* `CreateFolder INLINE`
</td></tr><tr><td>
NAME</td><td>
/M</td><td>

*\<folder name\> ...*</td><td>

Specify the name of the folder or archive to create. If this argument is supplied Opus will not prompt for a name (unless **ASK** is also specified). You can specify a full path, or just the folder name to create the folder in the current source directory. You can also specify multiple names to create more than one folder at once.

This is the default argument for the **CreateFolder** command, so the keyword **NAME** does not need to be specified. However, if you need to create a folder whose name is one of the other argument names, you must use the more explicit **NAME="xyz"** form to avoid the *xyz* part being interpreted as an argument name instead of a folder name. If you need this while creating multiple folders, you can specify the **NAME** argument multiple times.

*Example:* `CreateFolder "Folder 1" "Folder 2" "Folder 3"`  
*Example:* `CreateFolder "C:\Program Files\My New Program"`  
*Example:* `CreateFolder NAME="Apple" NAME="Ask" NAME="Inline" ASK`
</td></tr><tr><td>
NOSEL</td><td>
/S</td><td>

*(no value)*</td><td>

Normally when a folder is created in the currently displayed directory it is selected, and the display scrolled if necessary to make it visible. The **NOSEL** argument prevents this.

*Example:* `CreateFolder "New Folder" NOSEL`
</td></tr><tr><td>
NOUPDATESETTINGS</td><td>
/S</td><td>

*(no value)*</td><td>

Prevents settings made by this command from becoming the new defaults. For example, if you specify the **READAUTO** argument, the value you provide will become the new default setting for the CreateFolder command unless you also specify **NOUPDATESETTINGS**.

*Example:* `CreateFolder "{date\|yyyyMMdd}" READAUTO NOUPDATESETTINGS`
</td></tr><tr><td>
MULTI</td><td>
/O</td><td>

*(no value)*</td><td>

Ensures the *Create Folder* is in multiple-folder mode if it opens.

If **MULTI** is not specified at all, the dialog remembers its previous mode (subject to **NOUPDATESETTINGS**) when no folder names are specified on the command line, uses single-folder mode when one name is specified, and uses multi-folder mode when multiple names are specified.

*Example:* `CreateFolder "Backup on {date\|yyyy_MM_dd}" ASK MULTI`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Ensures the *Create Folder* dialog is in single-folder mode if it opens.

*Example:* `CreateFolder MULTI=no`
</td></tr><tr><td>
READAUTO</td><td>
/O</td><td>

*(no value)*</td><td>

Automatically read the newly created folder into the current source file display.

*Example:* `CreateFolder "New Folder" READAUTO`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not automatically read the newly created folder.

*Example:* `CreateFolder "New Folder" READAUTO=no`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

Read the newly created folder into the other file display. If the Lister is not currently in [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode it will be placed in this mode first. You can combine this value with **tab** to open a new tab in the other file display.

*Example:* `CreateFolder "New Folder" READAUTO=dual`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Read the newly created folder into the left (or top) file display, regardless of which side is active. You can combine this value with **tab** to open a new tab.

*Example:* `CreateFolder "Stuff" READAUTO=left,tab`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Read the newly created folder into the right (or bottom) file display, regardless of which side is active. If the Lister is not currently in [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode it will be placed in this mode first. You can combine this value with **tab** to open a new tab in the other file display.

*Example:* `CreateFolder "My Dir" READAUTO=right`
</td></tr><tr><td>
</td><td>
</td><td>

**tab**</td><td>

Create a new tab for the newly created folder. The tab will be opened in the source file display unless **dual**, **left**, or **right** is also specified.

*Example:* `CreateFolder "New Folder" READAUTO=dual,tab`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

When opening a new tab, prevents that tab from being made the active one.

*Example:* `CreateFolder "New Folder" READAUTO=tab,nofocus`
</td></tr><tr><td>
ZIP</td><td>
/S</td><td>

*(no value)*</td><td>

Create a new Zip file (equivalent to `CreateFolder ARCHIVE=.zip`).

*Example:* `CreateFolder ZIP`
</td></tr></tbody>
</table>

