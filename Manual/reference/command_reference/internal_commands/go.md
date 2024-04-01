# Go

The **Go** internal command can be used to:

- [Navigate](/Manual/basic_concepts/the_lister/navigation/README.md) to a different folder in the Lister
- Move back and forward in the [history list](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.md), and display the contents of the history list
- Connect and disconnect network shares
- Display a list of drives on your toolbar
- Display the contents of a folder in a drop-down menu
- Display a list of sites in the [FTP address book](/Manual/ftp/ftp_address_book/README.md)
- Open new Listers
- Open and manipulate [folder tabs](/Manual/basic_concepts/the_lister/tabs/README.md) and [tab groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md).

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
BACK</td><td>
/S</td><td>

*(no value)*</td><td>

Navigate to the previous folder in the [history list](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.md). The history list preserves the file selection and scroll offset state of the folder. The **BACK** argument can be combined with the **UP** argument; in that case, if the previous folder in the history list is the current folder's parent, Opus will go back (preserving selections, etc) rather than **UP**.

You can combine this with arguments that change the target of the navigation, like **NEW**, **NEWTAB**, **OPENINDUAL** etc.

*Example:* `Go BACK`
</td></tr><tr><td>
BACKLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Display a list of all previous folders in the history list (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This is used on the drop-down menu attached to the Back button on the default toolbar.

*Example:* `Go BACKLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

Display only folder names, not full paths. Tooltips will show full paths when hovering over items.

*Example:* `Go BACKLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

Does not display icons on the generated history list.

*Example:* `Go BACKLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

Assigns the accelerator keys **0** through **9** to the first ten items displayed on the generated history list.

*Example:* `Go BACKLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

Sorts the history list alphabetically instead of in chronological order.

*Example:* `Go BACKLIST=sort`
</td></tr><tr><td>
COMPATIBILITYFILES</td><td>
/S</td><td>

*(no value)*</td><td>

Switch between a folder and its compatibility store. Not all folders have compatibility stores - this command will do nothing in that case. For example, from **C:\Program Files** you would be taken to **C:\Users\\..\VirtualStore\Program Files**, and vice versa.

The compatibility store concept was introduced in Windows Vista with the addition of UAC, to support older software that tried to save files in the program folder. These days the concept is hardly ever encountered.

*Example:* `Go COMPATIBILITYFILES`
</td></tr><tr><td>
CONNECT</td><td>
/O</td><td>

*(no value)*</td><td>

Display the system dialog that allows you to map a network share to a drive letter.

*Example:* `Go CONNECT`
</td></tr><tr><td>
</td><td>
</td><td>

*\<network path\>*</td><td>

Map the specified network path to a drive letter.

*Example:* `Go CONNECT \\server\share`
</td></tr><tr><td>
COPYARGS</td><td>
/K/R</td><td>

*(no value)*</td><td>

A command like `Go FOLDERCONTENT=copy` which generates a list of buttons, each of which copies or moves files to or from a different place. Each generated button runs the Opus **Copy** command, which takes different arguments to the **Go** command.

The **COPYARGS** argument allows you to specify one or more additional **Copy**-command arguments which are added to each of the generated buttons.

Since this is a "raw" argument, it should be the last thing on the line. All text after the word "COPYARGS" will be taken as-is, including any quote characters, and appended to the copy command of each generated button.

*Example:* `Go C:\ FOLDERCONTENT=copy COPYARGS COPYFILETIMES=no`
</td></tr><tr><td>
CURDIR</td><td>
/O</td><td>

*(no value)*</td><td>

Activates "current directory" mode for the **Go** command. When used with a drive letter for the **PATH** argument, this mode makes Opus navigate to the most recently accessed folder on the specified drive. Opus will remember the "current directory" for each drive in your system, even from one session to the next.

When used in conjunction with the **DRIVEBUTTONS** argument, the generated drive letter buttons will have the same behaviour, and will highlight to indicate the "current drive". In this way you can click around from one drive to another remembering the previously used folder on each drive.

*Example:* `Go D: CURDIR`  
*Example:* `Go DRIVEBUTTONS=fixed CURDIR`
</td></tr><tr><td>
</td><td>
</td><td>

**rootmode**</td><td>

Modifies "current directory" mode so that clicking the button for the drive you are already on takes you to the root of the drive (ordinarily it would do nothing).

*Example:* `Go DRIVEBUTTONS CURDIR=rootmode`
</td></tr><tr><td>
CURRENT</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates the current source folder. This argument is used to open the current folder in another tab, Lister or file display.

*Example:* `Go CURRENT OPENINDUAL`
</td></tr><tr><td>
DESTPATH</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates the current destination folder. This argument is used to open the destination folder in the source file display (or another Lister, or tab).

*Example:* `Go DESTPATH`
</td></tr><tr><td>
DISCONNECT</td><td>
/S</td><td>

*(no value)*</td><td>

Display the system dialog that allows you to disconnect (unmap) a network share.

*Example:* `Go DISCONNECT`
</td></tr><tr><td>
DRIVEBUTTONS</td><td>
/O</td><td>

*(no value)*</td><td>

Display a list of all the drives currently on your system (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Clicking a button navigates the source folder to that drive's root. The drive buttons can also be right-clicked to display the context menu for each drive.

The various values for this argument can be used to restrict the drives that are shown.

*Example:* `Go DRIVEBUTTONS`
</td></tr><tr><td>
</td><td>
</td><td>

**fixed**</td><td>

Only display the fixed drives (hard drives).

*Example:* `Go DRIVEBUTTONS=fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**network**</td><td>

Only display network (mapped) drives.

*Example:* `Go DRIVEBUTTONS=network`
</td></tr><tr><td>
</td><td>
</td><td>

**cdrom**</td><td>

Only display CD-ROM (and DVD) drives.

*Example:* `Go DRIVEBUTTONS=cdrom`
</td></tr><tr><td>
</td><td>
</td><td>

**removable**</td><td>

Only display removable drives (floppies, and some USB drives).

*Example:* `Go DRIVEBUTTONS=removable,cdrom`
</td></tr><tr><td>
</td><td>
</td><td>

**ramdisk**</td><td>

Only display RAM drives.

*Example:* `Go DRIVEBUTTONS=ramdisk`
</td></tr><tr><td>
</td><td>
</td><td>

**mtp**</td><td>

Only display MTP (portable) devices.

*Example:* `Go DRIVEBUTTONS=mtp`
</td></tr><tr><td>
</td><td>
</td><td>

**iconlettersoff**</td><td>

Disable the display of small drive letters as part of each drive's icon.

*Example:* `Go DRIVEBUTTONS=fixed,iconlettersoff`
</td></tr><tr><td>
</td><td>
</td><td>

**iconletterson**</td><td>

Enable the display of small drive letters as part of each drive's icon.

*Example:* `Go DRIVEBUTTONS=iconletterson`
</td></tr><tr><td>
</td><td>
</td><td>

**labels**</td><td>

Displays the label of each drive. By default only each drive's letter is shown.

*Example:* `Go DRIVEBUTTONS=fixed,labels`
</td></tr><tr><td>
</td><td>
</td><td>

**noletters**</td><td>

Prevents the display of each drive's letter, if labels are being shown using the **labels** keyword. Note that if you want to completely disable any text being displayed in the button you need to turn off the button's **Show Label** checkbox in the [button editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md).

*Example:* `Go DRIVEBUTTONS=labels,noletters`
</td></tr><tr><td>
</td><td>
</td><td>

**multifunc**</td><td>

The generated drive buttons will be [multiple function buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.md) (three-button buttons) - clicking them with the left mouse button will act as if **OPENINLEFT** were set, the right button will act as if **OPENINRIGHT** were set, and the middle mouse button will act as if **NEW** were set.

*Example:* `Go DRIVEBUTTONS=fixed,network,multifunc`
</td></tr><tr><td>
</td><td>
</td><td>

**multifunctabs**</td><td>

Similar to **multifunc**, except the left and right mouse button functions will open a new tab on the appropriate side of the Lister. You can control how new tabs are opened with the **NEWTAB** argument.

*Example:* `Go DRIVEBUTTONS=multifunctabs,labels,fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**lettersbeforelabels**</td><td>

When showing both drive letters and labels, the letters will be displayed first. Without this letters are shown following the labels.

*Example:* `Go DRIVEBUTTONS=fixed,labels,lettersbeforelabels`
</td></tr><tr><td>
</td><td>
</td><td>

**offline**</td><td>

When showing network drives, only offline drives will be shown (by default both connected and offline drives are shown).

*Example:* `Go DRIVEBUTTONS=network,offline`
</td></tr><tr><td>
</td><td>
</td><td>

**online**</td><td>

When showing network drives, only online (connected) drives will be shown.

*Example:* `Go DRIVEBUTTONS=network,online`
</td></tr><tr><td>
</td><td>
</td><td>

**hideempty**</td><td>

Hides the display of empty drives. Removable disks (floppies, card readers, DVDs) that have no media inserted in them will not be displayed.

*Example:* `Go DRIVEBUTTONS=cdrom,removable,hideempty`
</td></tr><tr><td>
</td><td>
</td><td>

**+***\<letters\>*</td><td>

Only display the specified drive letters. Any drives not specified will be hidden.

*Example:* `Go DRIVEBUTTONS=removable,+fhjm`
</td></tr><tr><td>
</td><td>
</td><td>

**-***\<letters\>*</td><td>

Do not display the specified drive letters.

*Example:* `Go DRIVEBUTTONS=-d`
</td></tr><tr><td>
DUALPATH</td><td>
/K</td><td>

*\<path to read\>*</td><td>

Specify a path to read into the destination file display of a dual-display Lister (the standard **PATH** argument reads into the source file display).

\`\`Go C:\ DUALPATH D:\\\`
</td></tr><tr><td>
EJECT</td><td>
/S</td><td>

*(no value)*</td><td>

Trigger an eject of the media in the drive specified by the **PATH** argument. This command has no effect if the drive does not have an eject mechanism.

*Example:* `Go D: EJECT`
</td></tr><tr><td>
EXISTINGLISTER</td><td>
/O</td><td>

*(no value)*</td><td>

If the specified folder is already open in an existing lister (including inactive folder tabs in other windows) then the command will activate that lister and the appropriate tab within it and do nothing else. If another window is found then the rest of the command's arguments are ignored. If the specified path is not already open in another window then the command continues as if the **EXISTINGLISTER** argument had not been given.

*Example:* `Go "C:\Program Files" NEW EXISTINGLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**seltabsonly**</td><td>

Only selected folder tabs will be considered. If the specified folder is open in an existing lister, but in a folder tab which is not currently selected, then that tab will be ignored.

*Example:* `Go "C:\Program Files" NEW EXISTINGLISTER=seltabsonly`
</td></tr><tr><td>
EXPANDBRANCH</td><td>
/O</td><td>

*(no value)*</td><td>

When [Folder Expansion](/Manual/preferences/preferences_categories/file_displays/folder_expansion.md) is turned on in Preferences, this command lets you programmatically expand folders in the current file display.

When used with no value, all currently selected folders will be expanded. You can combine this with the **PATH** argument to specify the item to expand by path - or in conjunction with the **wild** or **regexp** keywords, by pattern matching.

*Example:* `Go EXPANDBRANCH`
</td></tr><tr><td>
</td><td>
</td><td>

**case**</td><td>

Use with `regexp` or `wild` to make the wildcard operation case sensitive.

*Example:* `Go EXPANDBRANCH=toggle,regexp,case PATH \[a-z\]+`
</td></tr><tr><td>
</td><td>
</td><td>

**clearselect**</td><td>

Use with `collapse` to automatically clear the selection of any files or folders inside the folders being collapsed.

*Example:* `Go EXPANDBRANCH=collapse,clearselect`
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

Collapses currently selected folders if they're currently expanded. Additionally, if a single file or unexpanded folder is selected and it's inside an expanded parent folder, the parent folder will be collapsed.

*Example:* `Go EXPANDBRANCH=collapse`
</td></tr><tr><td>
</td><td>
</td><td>

**noparent**</td><td>

When used with `Go EXPANDBRANCH=collapse` this prevents it collapsing the parent folder of a selected file or unexpanded folder.

*Example:* `Go EXPANDBRANCH=collapse,noparent`
</td></tr><tr><td>
</td><td>
</td><td>

**regexp**</td><td>

The **PATH** argument will be interpreted as a [regular expression](../../wildcard_reference/regular_expression_syntax.md).

*Example:* `Go EXPANDBRANCH=toggle,regexp PATH \[a-z\]+`
</td></tr><tr><td>
</td><td>
</td><td>

**script**</td><td>

When run from a script, uses the folders added to the [Command](/Manual/reference/scripting_reference/scripting_objects/command.md) object to expand/collapse rather than selected folders.

*Example:* `Go EXPANDBRANCH=script,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the expansion state of currently selected folers.

*Example:* `Go EXPANDBRANCH=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggleall**</td><td>

Toggles the expansion state of selected folders as a group. If any are not expanded, all will be expanded. If all are expanded, all will be collapsed.

*Example:* `Go EXPANDBRANCH=toggleall`
</td></tr><tr><td>
</td><td>
</td><td>

**top**</td><td>

Restricts the command to expanding/collapsing items at the top level, ignoring nested items. (Has no effect if the **PATH** argument is used to specify the item).

*Example:* `Go EXPANDBRANCH=toggleall,top`
</td></tr><tr><td>
</td><td>
</td><td>

**wild**</td><td>

The **PATH** argument will be interpreted as a [wildcard](../../wildcard_reference/pattern_matching_syntax.md). Note the wildcard is tested against names only, not complete paths. Any folders matching the wildcard will be expanded or collapsed, whether they are currently selected or not.

*Example:* `Go EXPANDBRANCH=toggleall,top,wild PATH *_backup`
</td></tr><tr><td>
FDBBUTTONS</td><td>
/O</td><td>

*(no value)*</td><td>

This command acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md). It lets you add buttons to a toolbar that mimic the standard File Display Border buttons. The command is designed to be used on the File Display toolbar as an alternative to the standard buttons.

By default the command will add *Back*, *Forward*, *Up*, *Copy*, *Swap* and *Toggle Layout* buttons. You can use the various keywords to control exactly which buttons are added.

*Example:* `Go FDBBUTTONS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<button keywords\>*</td><td>

Use combinations of the keywords **back**, **forward**, **up**, **copy**, **swap** and **layout** to control exactly which buttons are added.

*Example:* `Go FDBBUTTONS back,forward` - show *Back* and *Forward* buttons  
*Example:* `Go FDBBUTTONS -layout` - show all but the *Toggle Layout* button
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

Do not display icons for the generated buttons.

*Example:* `Go FDBBUTTONS -layout,noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**nolabels**</td><td>

Do not display labels for the generated buttons.

*Example:* `Go FDBBUTTONS swap,layout,nolabels`
</td></tr><tr><td>
</td><td>
</td><td>

**dropdowns**</td><td>

Make the generated buttons drop-down buttons where applicable.

*Example:* `Go FDBBUTTONS back,forward,up,dropdowns`
</td></tr><tr><td>
FINDTITLE</td><td>
/K</td><td>

*\<title string\>*</td><td>

Finds all currently open Listers with titles that match the specified string, and brings them to the front. The string to search for can be a specific title or a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md).

*Example:* `Go FINDTITLE *Projects`\*
</td></tr><tr><td>
FOLDERCONTENT</td><td>
/O</td><td>

*(no value)*</td><td>

Display the contents of the path specified by the **PATH** argument in drop-down menus (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Sub-folders in the generated list can be selected to navigate to that location, and files in the generated list can be selected to open that file. You can also right-click on items to display their context menus, and drag-and-drop files to folders (to copy or move them) or over other files (to open them). If you hover the mouse over a sub-folder it will expand to display another menu showing the contents of the sub-folder.

When used with **FOLDERCONTENT** only, the **PATH** argument supports multiple paths separated with a vertical bar (**\|**). For example, this would let you reproduce (to some extent anyway) the Windows start menu in a drop-down menu in a Lister, by showing both the current user's start folder and the common (all users) start folder.

*Example:* `Go /start|/commonstartmenu FOLDERCONTENT`
</td></tr><tr><td>
</td><td>
</td><td>

**button**</td><td>

Sub-folders in the generated **FOLDERCONTENT** list will appear as menu-buttons. Clicking the button part will read the sub-folder, expanding the drop-down will display its contents.

*Example:* `Go C: FOLDERCONTENT=button`
</td></tr><tr><td>
</td><td>
</td><td>

**nomenusel**</td><td>

Hovering over a sub-folder will expand it, while single-clicking will navigate to it. Also forces empty folders to be hidden, even if **showempty** is also specified.

*Example:* `Go C: FOLDERCONTENT=nomenusel`
</td></tr><tr><td>
</td><td>
</td><td>

**dblclickmenu**</td><td>

For folders with sub-items, both hovering and single-clicking will expand their sub-menus, while double-clicking will navigate to them. For folders without sub-items, a single-click will be enough to navigate to them.

*Example:* `Go C: FOLDERCONTENT=dblclickmenu`
</td></tr><tr><td>
</td><td>
</td><td>

**norecurse**</td><td>

Prevents sub-folders in the generated list from being expanded; the list will be limited to a single folder level (although sub-folders will still be displayed, you will not be able to expand them).

*Example:* `Go C: FOLDERCONTENT=norecurse`
</td></tr><tr><td>
</td><td>
</td><td>

**noparselinks**</td><td>

Prevents shortcuts from being resolved. Without this, a shortcut to a folder will be expandable just like a normal sub-folder.

*Example:* `Go /profile FOLDERCONTENT=noparselinks`
</td></tr><tr><td>
</td><td>
</td><td>

**nodirs**</td><td>

Excludes sub-folders from the generated list - only files will be shown.

*Example:* `Go /temp FOLDERCONTENT=nodirs`
</td></tr><tr><td>
</td><td>
</td><td>

**nofiles**</td><td>

Excludes files from the generated list - only folders will be shown.

*Example:* `Go C: FOLDERCONTENT=nofiles`
</td></tr><tr><td>
</td><td>
</td><td>

**showhidden**</td><td>

Includes hidden files and folders in the list - without this, items with the **H** attribute set will be excluded.

*Example:* `Go C: FOLDERCONTENT=nofiles,showhidden`
</td></tr><tr><td>
</td><td>
</td><td>

**showempty**</td><td>

Empty sub-folders will be included in the generated list. Without this, empty sub-folders are excluded.

*Example:* `Go CURRENT FOLDERCONTENT=showempty`
</td></tr><tr><td>
</td><td>
</td><td>

**filefilter=***\<pattern\>*</td><td>

Specifies a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) that the names of files must match to be included in the generated list (without this, all files are included).

Because this keyword requires an embedded equals sign, you must enclose the entire argument value in quotes to avoid confusing the command parser.

*Example:* `Go C: FOLDERCONTENT="filefilter=*.exe"`

If you need a comma (,) character within the pattern, put embedded quotes around the pattern as well. The examples below both specify **\*,**\* as the pattern:

*Example:* `Go C: FOLDERCONTENT="filefilter=""*"*"""`  
*Example:* `Go C: FOLDERCONTENT="filefilter=""*"*"",nodirs"`
</td></tr><tr><td>
</td><td>
</td><td>

**dirfilter=***\<pattern\>*</td><td>

Specifies a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) that folder names must match to be included in the generated list (without this, all folders are included).

Because this keyword requires an embedded equals sign, you must enclose the entire argument value in quotes to avoid confusing the command parser.

*Example:* `Go C:\Work FOLDERCONTENT="dirfilter=~(.svn)"`

If you need a comma (,) character within the pattern, put embedded quotes around the pattern, similar to the **filefilter** examples above.
</td></tr><tr><td>
</td><td>
</td><td>

**maxfiles=***\<num\>*</td><td>

Specify the maximum number of files to list at each level. If menus for sub-folders are generated, each menu is limited in a similar way.

Because this keyword requires an embedded equals sign, you must enclose the entire argument value in quotes to avoid confusing the command parser.

*Example:* `Go C: FOLDERCONTENT="maxfiles=5,sortdate"`

If you wish to exclude files entirely, it is more efficient to use **nofiles** rather than **maxfiles=0**.
</td></tr><tr><td>
</td><td>
</td><td>

**maxdirs=***\<num\>*</td><td>

Specify the maximum number of directories to list at each level. If menus for sub-folders are generated, each menu is limited in a similar way.

Because this keyword requires an embedded equals sign, you must enclose the entire argument value in quotes to avoid confusing the command parser.

*Example:* `Go C: FOLDERCONTENT="maxdirs=10"`

If you wish to exclude directories entirely, it is more efficient to use **nodirs** rather than **maxdirs=0**.
</td></tr><tr><td>
</td><td>
</td><td>

**maxdepth=***\<levels\>*</td><td>

Specify the maximum number of levels deep that sub-folders can be expanded in the generated list.

Because this keyword requires an embedded equals sign, you must enclose the entire argument value in quotes to avoid confusing the command parser.

*Example:* `Go C: FOLDERCONTENT="maxdepth=10"`
</td></tr><tr><td>
</td><td>
</td><td>

**hideext**</td><td>

Do not show the filename extensions for files in the generated list.

*Example:* `Go /mydocuments FOLDERCONTENT=hideext`
</td></tr><tr><td>
</td><td>
</td><td>

**sortext**</td><td>

Sorts files in the generated list by file extension.

*Example:* `Go /temp FOLDERCONTENT=nodirs,sortext`
</td></tr><tr><td>
</td><td>
</td><td>

**sortsize**</td><td>

Sorts files in the generated list by size.

*Example:* `Go "C:\Program Files" FOLDERCONTENT=sortsize`
</td></tr><tr><td>
</td><td>
</td><td>

**sortdate**</td><td>

Sorts files in the generated list by timestamp.

*Example:* `Go /downloads FOLDERCONTENT=sortdate`
</td></tr><tr><td>
</td><td>
</td><td>

**sortnone**</td><td>

Do not sort the list at all. Files and folders will still be grouped but, within each group, they will be displayed in the order the operating system returned them. Often be the same as sorting by name, but can result in special or random orders in some folders.

Useful with the *Quick Access* folder (renamed *Home* in later versions of Windows 11), where the order is something you define and usually want preserved anywhere the items are displayed.

*Example:* `Go /quickaccess FOLDERCONTENT=norecurse,nofiles,sortnone`
</td></tr><tr><td>
</td><td>
</td><td>

**sortreverse**</td><td>

Reverse the normal sort order of items in the generated list.

*Example:* `Go /downloads FOLDERCONTENT=sortdate,sortreverse`
</td></tr><tr><td>
</td><td>
</td><td>

**copy**</td><td>

The generated list is dedicated to copying selected files to the folders shown in the list. This modifies the standard behaviour when you select a sub-folder from the drop-down menu. For example, if you select some files in the current folder, and then choose a sub-folder from the drop-down `Go FOLDERCONTENT` menu, the files would be copied to that folder.

Each generated button will run the **Copy** command. You can use the separate **COPYARGS** argument to specify additional **Copy**-command arguments which are included in each generated button.

*Example:* `Go \\NAS\Music FOLDERCONTENT=nofiles,copy`
</td></tr><tr><td>
</td><td>
</td><td>

**move**</td><td>

Selecting a sub-folder from the generated list will move selected files to that folder.

*Example:* `Go D:\Archive\Documents FOLDERCONTENT=nofiles,move`
</td></tr><tr><td>
</td><td>
</td><td>

**copytosource**</td><td>

Clicking a file or folder in the generated list will copy it into the current folder. (Note that this copy is in the opposite direction to the **copy** and **move** modes discussed just above.)

This could be useful if you have a folder containing template items which you frequently need to copy into different folders as you move around. To update the list of template items, you would just need to add or remove things (or softlinks to them) to the folder.

*Example:* `Go "C:\My Templates" FOLDERCONTENT=copytosource`

Each generated button will run the **Copy** command. You can use the separate **COPYARGS** argument to specify additional **Copy**-command arguments which are included in each generated button.

*Example:* `Go C:\ FOLDERCONTENT=copy COPYARGS COPYFILETIMES=no\*\*`

There are no separate "move" versions of the "copyto..." keywords, since it seems unlikely they'd be needed, but you can achieve the same thing via the **COPYARGS** argument:

*Example:* `Go C:\ FOLDERCONTENT=copy COPYARGS MOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**copytodest**</td><td>

Similar to **copytosource**, except the item you click will be copied to the destination folder rather than the current (source) folder.

*Example:* `Go "C:\Templates" FOLDERCONTENT=copytodest,nodirs`
</td></tr><tr><td>
</td><td>
</td><td>

**copytoleft**</td><td>

Similar to **copytosource**, except the item you click will always be copied to the left folder (assuming a dual-display window).

*Example:* `Go "C:\Templates" FOLDERCONTENT=copytoleft`
</td></tr><tr><td>
</td><td>
</td><td>

**copytoright**</td><td>

Similar to **copytosource**, except the item you click will always be copied to the right folder (assuming a dual-display window).

*Example:* `Go "C:\Templates" FOLDERCONTENT=copytoright`
</td></tr><tr><td>
</td><td>
</td><td>

**useshell**</td><td>

Normally folder paths like **C:\\** are enumerated using the native Windows API functions. If you specify the **useshell** keyword, they'll instead be enumerated using the shell (i.e. Explorer). This may give you localized names in some cases, as well as different ordering and different contents.

*Example:* `Go C: FOLDERCONTENT=useshell`
</td></tr><tr><td>
FORWARD</td><td>
/S</td><td>

*(no value)*</td><td>

Navigate to the next folder in the [history list](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.md).

You can combine this with arguments that change the target of the navigation, like **NEW**, **NEWTAB**, **OPENINDUAL** etc.

*Example:* `Go FORWARD`
</td></tr><tr><td>
FORWARDLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Display a list of all subsequent folders in the history list (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This is used on the drop-down menu attached to the Forward button on the default toolbar.

*Example:* `Go FORWARDLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

Display only folder names, not full paths. Tooltips will show full paths when hovering over items.

*Example:* `Go FORWARDLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

Does not display icons on the generated history list.

*Example:* `Go FORWARDLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

Assigns the accelerator keys **0** through **9** to the first ten items displayed on the generated history list.

*Example:* `Go FORWARDLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

Sorts the history list alphabetically instead of in chronological order.

*Example:* `Go FORWARDLIST=sort`
</td></tr><tr><td>
FROMSEL</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates the first selected folder in the source file display. This argument is used to open the selected folder (in the current file display, another tab, a new Lister, etc).

*Example:* `Go FROMSEL NEW`
</td></tr><tr><td>
FTP</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **[FTP Connect](/Manual/ftp/ftp_connect.md)** dialog, allowing you to make an ad-hoc connection to an FTP site.

*Example:* `Go FTP`
</td></tr><tr><td>
FTPCMD</td><td>
/K/R</td><td>

*\<command\>*</td><td>

Sends a raw command to the remote FTP server (when currently viewing an FTP directory). If no FTP site is currently connected the command has no effect. The effects of the command, if any, can be viewed in the [FTP log](/Manual/ftp/ftp_log.md).

*Example:* `Go FTPCMD chmod * 755`
</td></tr><tr><td>
FTPSITE</td><td>
/K</td><td>

*\<site name\>*</td><td>

Connect to an FTP site listed in the [FTP address book](/Manual/ftp/ftp_address_book/README.md). The site must be specified by name, and if the site is in a sub-folder of the address book you must include the complete path of the entry. The **FTPSITE** argument is the equivalent of prefixing the site entry name with **@** in the **PATH** argument.

*Example:* `Go FTPSITE "Work Servers\Dallas\Production"`
</td></tr><tr><td>
FTPSITEICONS</td><td>
/S</td><td>

*(no value)*</td><td>

In conjunction with the **FTPSITELIST** argument, displays icons for all sites in the list generated by the command.

*Example:* `Go FTPSITELIST FTPSITEICONS`
</td></tr><tr><td>
FTPSITELIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a list of the sites in the [FTP address book](/Manual/ftp/ftp_address_book/README.md)(acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)).

*Example:* `Go FTPSITELIST`
</td></tr><tr><td>
</td><td>
</td><td>

*\<site prefix\>*</td><td>

Displays the FTP site list starting from a specified sub-folder of the address book.

*Example:* `Go FTPSITELIST "Work Servers"`
</td></tr><tr><td>
GROUPCOLLAPSE</td><td>
/K</td><td>

*\<group name\>*</td><td>

When the file display is [grouped](/Manual/basic_concepts/sorting_and_grouping/README.md), this command can be used to collapse a specified group. The group name must match exactly, but you can also use a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to collapse all groups matching that pattern.

*Example:* `Go GROUPCOLLAPSE` \*
</td></tr><tr><td>
GROUPEXPAND</td><td>
/K</td><td>

*\<group name\>*</td><td>

Expand a specified file group. The group name must match exactly, but you can also use a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to expand all groups matching that pattern.

*Example:* `Go GROUPEXPAND` \*
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Go DRIVEBUTTONS HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Go DRIVEBUTTONS HEADING="List of Drive Buttons"`
</td></tr><tr><td>
HISTORYLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Display the contents of the history list (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This is a combination of the previous (**BACKLIST**) and subsequent (**FORWARDLIST**) folders.

*Example:* `Go HISTORYLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

Display only folder names, not full paths. Tooltips will show full paths when hovering over items.

*Example:* `Go HISTORYLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

Does not display icons on the generated history list.

*Example:* `Go HISTORYLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

Assigns the accelerator keys **0** through **9** to the first ten items displayed on the generated history list.

*Example:* `Go HISTORYLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

Sorts the history list alphabetically instead of in chronological order.

*Example:* `Go HISTORYLIST=sort`
</td></tr><tr><td>
INITIALDIR</td><td>
/S</td><td>

*(no value)*</td><td>

Returns the file display to the very first folder that it read.

*Example:* `Go INITIALDIR`
</td></tr><tr><td>
KEYARGS</td><td>
/K/M</td><td>

*\<qualifier:arguments\> ...*</td><td>

Provides an alternate way to modify the behaviour of the **Go** command depending on which qualifier keys are held down (instead of using the **@keydown** [command modifier](/Manual/customize/creating_your_own_buttons/command_modifiers.md)). This is a multiple value argument - for each qualifier key combination listed, you can define a separate set of arguments that will be used when command is run and that key combination is held.

For example, you could configure a **Go** button to open a folder in a new tab by default, but in a new Lister if the **Control** key were held down.

The qualifier part of the value consists of one or more keywords that represent the qualifier keys - **ctrl**, **shift** and **alt**. These can be combined, for example **ctrlshift** means that both the **Control** and **Shift** keys must be held down. You can also use the keyword **none** to indicate arguments that are applied when no qualifiers are held.

*Example:* `Go FROMSEL KEYARGS "ctrl:NEW" "none:NEWTAB=findexisting"`
</td></tr><tr><td>
LASTACTIVELISTER</td><td>
/S</td><td>

*(no value)*</td><td>

Brings the most recently active Lister to the front. If there is no valid Lister currently open, any other arguments provided to the command are used instead. So for example, you could have a global hotkey that brings the previous Lister to the front, or opens a new one if no Lister is open.

*Example:* `Go LASTACTIVELISTER NEW`
</td></tr><tr><td>
LASTCRUMB</td><td>
/S</td><td>

*(no value)*</td><td>

If the file display has a [breadcrumbs location field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) associated with it, and a ghost path is currently shown, this command will go to the last "crumb" in the ghost path.

*Example:* `Go LASTCRUMB`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

*\<layout name\>*</td><td>

Opens the folder in a new Lister loaded from the specified [layout](/Manual/basic_concepts/the_lister/layouts/README.md). If the layout contains more than one Lister, only the first Lister is used. The other arguments of the **Go** command can be used to override the settings in the layout.

*Example:* `Go FROMSEL LAYOUT=Pictures VIEW=details`
</td></tr><tr><td>
NAME</td><td>
/K</td><td>

*\<name\>*</td><td>

Specifies a name to save or load the folder tree expansion. Use with **REMEMBERTREEEXPANSION** and **RESTORETREEEXPANSION**.

*Example:* `Go REMEMBERTREEEXPANSION NAME=CurrentJob`
</td></tr><tr><td>
NEW</td><td>
/O</td><td>

*(no value)*</td><td>

Opens a new Lister. The [Default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md) settings are used for the newly opened Lister, although the various other arguments for the **Go** command can be used to override the settings of the Default Lister.

*Example:* `Go C:\ NEW`
</td></tr><tr><td>
</td><td>
</td><td>

*\<x\>,\<y\>,\<w\>,\<h\>*</td><td>

Specify the position and size of the new Lister window. *\<x\>* and *\<y\>* represent the left and top edge coordinates of the window, and *\<w\>* and *\<h\>* the width and height.

*Example:* `Go NEW 240,300,640,480`
</td></tr><tr><td>
</td><td>
</td><td>

**max**</td><td>

Maximize the new Lister window. You can use the *\<x\>* and *\<y\>* parameters to control which monitor the window appears maximized on.

*Example:* `Go NEW -1024,0,max`
</td></tr><tr><td>
</td><td>
</td><td>

**min**</td><td>

Minimize the new Lister window. If a size and position is specified as well, it will represent the restored position once you un-minimize (restore) the Lister.

*Example:* `Go NEW 1800,50,1024,768,min`
</td></tr><tr><td>
</td><td>
</td><td>

**norm**</td><td>

The new Lister window is to be neither minimized nor maximized. Use this to override if the Default Lister is maximized, for example.

*Example:* `Go NEW norm`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Set the new Lister to be the current source.

*Example:* `Go FROMSEL NEW=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Set the new Lister to be the destination.

*Example:* `Go C:\Backup NEW=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**lockoff**</td><td>

The new Lister will be set as "off" - neither [source nor destination](/Manual/basic_concepts/source_and_destination.md).

*Example:* `Go NEW=off`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

Opens the folder tree in the new Lister.

*Example:* `Go C:\Windows NEW=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**notree**</td><td>

Does not open the folder tree in the new Lister.

*Example:* `Go NEW=0,0,640,480,notree`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

Open the new Lister in [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode, taking the vertical or horizontal layout from the Default Lister.

\`\`Go NEW=dual C:\ DUALPATH D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**dualhoriz**</td><td>

Opens the new Lister in dual-display mode, laid out horizontally.

*Example:* `Go NEW=dualhoriz FROMSEL`
</td></tr><tr><td>
</td><td>
</td><td>

**dualvert**</td><td>

Open the new Lister in [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode, laid out vertically.

\`\`Go NEW=dualvert C:\ DUALPATH D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**nodual**</td><td>

Opens the new Lister in single-display mode.

*Example:* `Go NEW=nodual`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

Displays the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md) in the new Lister.

*Example:* `Go NEW=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**noviewpane**</td><td>

Does not display the viewer pane in the new Lister.

*Example:* `Go NEW=noviewpane,notree`
</td></tr><tr><td>
</td><td>
</td><td>

**findpanel**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in Find Files mode in the new Lister. The panel will open in its Simple or Advanced state, depending on which was used the last time the panel was closed.

*Example:* `Go CURRENT NEW=findpanel`
</td></tr><tr><td>
</td><td>
</td><td>

**findsimple**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in Find Files (Simple) mode in the new Lister.

*Example:* `Go CURRENT NEW=findsimple`
</td></tr><tr><td>
</td><td>
</td><td>

**findadvanced**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in Find Files (Advanced) mode in the new Lister.

*Example:* `Go CURRENT NEW=findadvanced`
</td></tr><tr><td>
</td><td>
</td><td>

**syncpanel**</td><td>

Displays the utility panel in Synchronize mode in the new Lister.

*Example:* `Go {sourcepath} DUALPATH {destpath} NEW=syncpanel`
</td></tr><tr><td>
</td><td>
</td><td>

**dupepanel**</td><td>

Displays the utility panel in Duplicate File Finder mode in the new Lister.

*Example:* `Go {sourcepath} NEW=dupepanel`
</td></tr><tr><td>
</td><td>
</td><td>

**noutilitypanel**</td><td>

Do not display the utility panel in the new Lister.

*Example:* `Go NEW=noutilitypanel`
</td></tr><tr><td>
</td><td>
</td><td>

**metapane**</td><td>

Displays the [metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md) in the new Lister.

*Example:* `Go NEW=metapane`
</td></tr><tr><td>
</td><td>
</td><td>

**nometapane**</td><td>

Does not display the metadata pane.

*Example:* `Go NEW=nometapane,noutilitypanel,noviewpane,notree,nodual`
</td></tr><tr><td>
NEWTAB</td><td>
/O</td><td>

*(no value)*</td><td>

Opens a new [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md). If no path is specified (e.g. via the **PATH** argument) then an empty tab is opened, otherwise the specified path will be loaded into the new tab. You can use the **TABPOS** argument to control where the newly-opened tab is positioned.

*Example:* `Go C:\ NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**deflister**</td><td>

If the command is run without a Lister then the Default Lister will open along with a new tab for the specified folder. If a Lister already exists then a new tab for the specified folder will open normally in the existing Lister.

*Example:* `Go C:\ NEWTAB=deflister,findexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**findexisting**</td><td>

Look for the specified path in existing tabs. If found, the existing tab will be brought to the front; otherwise a new tab will be opened. The active tab is checked first, and nothing will happen if the active tab already displays the specified path.

*Example:* `Go CURRENT NEWTAB=findexisting OPENINDUAL`

In some situations, **findexisting** is the default behavior, and **nofindexisting** can be used to suppress it.
</td></tr><tr><td>
</td><td>
</td><td>

**findinactive**</td><td>

Like **findexisting**, except that if the active tab already has the specified path then a new tab will be opened. Intended for buttons which switch to existing tabs to reduce clutter while retaining the ability to open a second tab for the same folder when needed.

*Example:* `Go "C:\Program Files" NEWTAB=findinactive`
</td></tr><tr><td>
</td><td>
</td><td>

**nofindexisting**</td><td>

Explicitly suppresses the **findexisting** behavior described above. The default for most commands it to not look for existing tabs, but some (e.g. <nobr>`Go OPENCONTAINER NEWTAB`</nobr>) will look for existing tabs unless explicitly told not to.

*Example:* `Go OPENCONTAINER NEWTAB=nofindexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

The new tab will not be made active.

*Example:* `Go CURRENT NEWTAB=nofocus`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

Brings the Lister to the front. This is useful when opening a tab in another window.

*Example:* `Go CURRENT NEWTAB=tofront OPENINDEST`
</td></tr><tr><td>
NEXTCRUMB</td><td>
/S</td><td>

*(no value)*</td><td>

If the file display has a [breadcrumbs location field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) associated with it, and a ghost path is currently shown, this command will go to the next "crumb" in the ghost path.

*Example:* `Go NEXTCRUMB`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(no value)*</td><td>

Allows a [script](/Manual/scripting/README.md) to run **Go** commands without triggering other scripts (or itself). Adding the **NOSCRIPT** argument disables the **[OnBeforeFolderChange](../../scripting_reference/scripting_events/onbeforefolderchange.md)**, **[OnAfterFolderChange](../../scripting_reference/scripting_events/onafterfolderchange.md)**, **[OnOpenTab](../../scripting_reference/scripting_events/onopentab.md)** and **[OnOpenLister](../../scripting_reference/scripting_events/onopenlister.md)** events that would otherwise be triggered by the command.
</td></tr><tr><td>
OPENCONTAINER</td><td>
/O</td><td>

*(no value)*</td><td>

Opens the container (parent folder) of the selected item. In normal folders this is not that useful (since the parent of the selected item is the folder you're already in), but in [file collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md) and [flat view](/Manual/basic_concepts/flat_view.md) it lets you quickly go to the actual folder where a file is located.

This command also works when multiple items are selected and may cause multiple windows or tabs to open if the selected items come from multiple containers.

This command is used on the default collection item context menu.

*Example:* `Go OPENCONTAINER`

When combined with the **NEWTAB** argument, existing tabs are searched for automatically, without having to explicitly use **NEWTAB=findexisting**. If you want a new tab to open all the time, ignoring any existing tabs for the same folder, then you can use **NEWTAB=nofindexisting**.

*Example:* `Go OPENCONTAINER NEWTAB=nofindexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**target**</td><td>

Dereferences a shortcut or junction. This is similar to the *Find Target* button in the system Properties dialog for shortcuts. When you run this command with a shortcut selected, the folder containing the target of the shortcut will be loaded and the target itself will be automatically selected (unless **noselect** is also given; see below). Similarly, if a junction is selected, you'll be taken the parent of its target and its target will be selected. If the selected item is neither a shortcut nor a junction then the command functions the same as if **target** had not been specified.

*Example:* `Go OPENCONTAINER=target NEW`
</td></tr><tr><td>
</td><td>
</td><td>

**noselect**</td><td>

Normally, the item or items in question are selected and made visible in the containing folder. Specifying this argument prevents the selection and just opens the containing folder.

*Example:* `Go OPENCONTAINER=target,noselect NEWTAB`
</td></tr><tr><td>
OPENINDEST</td><td>
/S</td><td>

*(no value)*</td><td>

The specified folder will be read into the destination file display. If the current Lister is not in dual-display mode, then it could mean the folder is read into another Lister altogether. You can combine this with **NEWTAB** to open tabs in the destination.

*Example:* `Go CURRENT OPENINDEST`
</td></tr><tr><td>
OPENINDUAL</td><td>
/O</td><td>

*(no value)*</td><td>

The specified folder will be read into the destination file display in a dual-display Lister. The difference between this argument and **OPENINDEST** is that this will force a single-display Lister into dual-display mode if it is not in that mode already. The default layout (horizontal or vertical) will be used in this case.

*Example:* `Go CURRENT OPENINDUAL`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

Force the layout of the dual-display Lister to horizontal (one display above the other).

*Example:* `Go C:\Windows OPENINDUAL=horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

Force the layout to vertical (side-by-side displays).

*Example:* `Go CURRENT NEWTAB OPENINDUAL=vert`
</td></tr><tr><td>
OPENINLEFT</td><td>
/S</td><td>

*(no value)*</td><td>

Reads the specified folder into the left-hand (or top) file display in a dual-display Lister. In a single-display Lister, this argument has no effect (the folder will be read into the single display as normal).

*Example:* `Go {rightpath} OPENINLEFT`
</td></tr><tr><td>
OPENINRIGHT</td><td>
/O</td><td>

*(no value)*</td><td>

Reads the specified folder into the right-hand (or bottom) file display in a dual-display Lister. If the current Lister is not already in dual-display mode it will be set to that mode automatically. The default layout (horizontal or vertical) will be used in this case.

*Example:* `Go {leftpath} OPENINRIGHT`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

Force the layout of the dual-display Lister to horizontal (one display above the other).

*Example:* `Go C:\Windows OPENINRIGHT=horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

Force the layout to vertical (side-by-side displays).

*Example:* `Go {leftpath} NEWTAB OPENINRIGHT=vert`
</td></tr><tr><td>
PATH</td><td>
</td><td>

*(no value)*</td><td>

Specify the path to read (or in conjunction with the **FOLDERCONTENT** argument, the path to display the contents of).

Opus supports paths in many formats, for example:

- An absolute path like *C:\Windows*
- A relative path like ..\\. (goes up two levels from the current folder)
- A virtual filesystem [URL-style path](/Manual/basic_concepts/virtual_file_system/README.md) (e.g. *ftp://ftp.microsoft.com* or *lib://Documents*)
- An FTP [address-book shortcut](/Manual/ftp/ftp_paths.md) (e.g. *@MyFtpSite*)
- A [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md) like */mydocuments*
- An environment variable like *%USERPROFILE%*
- An [external control code](../external_control_codes/README.md) like **{sourcepath}**
- A file URI like **[file:///C:/Temp](file:///C:/Temp)**. This is the default argument for the **Go** command and so you do not need to specify the **PATH** keyword. Remember that if the path contains spaces it needs to be enclosed in quotes.

*Example:* `Go "C:\Program Files\GPSoftware\Directory Opus"`
</td></tr><tr><td>
PATHENTRY</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in a special mode ("go" mode) that lets you navigate to another folder in the current file display. This command is equivalent to **[CLI](cli.md) QUICKGO**.

*Example:* `Go PATHENTRY`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

The "Go" field will act on the destination file display rather than the source. Note that it will still appear at the bottom of the source file display, but once you press **Enter** the folder will be read into the destination.

*Example:* `Go PATHENTRY=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

The "Go" field will act on the left-hand file display, whether it is the source or destination.

*Example:* `Go PATHENTRY=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

The "Go" field will act on the right-hand file display.

*Example:* `Go PATHENTRY=right`
</td></tr><tr><td>
REBUILDTREE</td><td>
/O</td><td>

*(no value)*</td><td>

Rebuilds the contents of the folder tree attached to the source file display. This is the equivalent of turning the tree off and then back on again.

*Example:* `Go REBUILDTREE`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Rebuilds the folder tree attached to the destination file display (when dual trees are enabled).

*Example:* `Go REBUILDTREE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Rebuilds the folder tree attached to the left/top file display.

*Example:* `Go REBUILDTREE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Rebuilds the folder tree attached to the right/bottom file display (when dual trees are enabled).

*Example:* `Go REBUILDTREE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Rebuilds both folder trees (or the single tree, whichever is applicable).

*Example:* `Go REBUILDTREE=both`
</td></tr><tr><td>
REFRESH</td><td>
/O</td><td>

*(no value)*</td><td>

Refresh the display of the current folder in the source file display.

*Example:* `Go REFRESH`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

Refresh the folder tree.

*Example:* `Go REFRESH=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Refresh both file displays in a dual-display Lister.

*Example:* `Go REFRESH=both`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Refresh both file displays and folder trees.

*Example:* `Go REFRESH=all`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Refresh the source file display and its tree.

*Example:* `Go REFRESH=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Refresh the destination file display and its tree.

*Example:* `Go REFRESH=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

Refresh the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md). The image or file currently displayed in the pane will be reloaded.

*Example:* `Go REFRESH=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Refresh the left-hand file display.

*Example:* `Go REFRESH=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Refresh the right-hand file display.

*Example:* `Go REFRESH=right`
</td></tr><tr><td>
REFRESHTHUMBS</td><td>
/O</td><td>

*(no value)*</td><td>

Refreshes thumbnails displayed in the current folder. If thumbnail caching is enabled the cache for the current folder is cleared, forcing thumbnails to be regenerated.

*Example:* `Go REFRESHTHUMBS`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

Refreshes thumbnails only if the **Shift** key is held down. This lets you combine a normal folder refresh with a thumbnail refresh on the one command - it could perform an ordinary folder refresh by default, and also force the regeneration of thumbnails with the **Shift** key held down.

*Example:* `Go REFRESH REFRESHTHUMBS=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

Refresh thumbnails only if the **Alt** key is held down.

*Example:* `Go REFRESHTHUMBS=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

Refresh thumbnails only if the **Control** key is held down.

*Example:* `Go REFRESHTHUMBS=ctrl REFRESH=all`
</td></tr><tr><td>
REMEMBERTREEEXPANSION</td><td>
/O</td><td>

*(no value)*</td><td>

Remembers the current expansion state of the source folder tree. Once the state has been remembered, you can restore it later on with **RESTORETREEEXPANSION**.

By default the expansion state is just remembered for the lifetime of the Lister. If used with the **NAME** argument the expansion will be saved under that name and can be restored at any time in the future.

*Example:* `Go REMEMBERTREEEXPANSION`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Remembers the expansion state of the folder tree attached to the destination file display (when dual trees are enabled).

*Example:* `Go REMEMBERTREEEXPANSION=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Remembers the expansion state of the folder tree attached to the left/top file display.

*Example:* `Go REMEMBERTREEEXPANSION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Remembers the expansion state of the folder tree attached to the right/bottom file display (when dual trees are enabled).

*Example:* `Go REMEMBERTREEEXPANSION=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Remembers the expansion state of both folder trees (or the single tree, whichever is applicable).

*Example:* `Go REMEMBERTREEEXPANSION=both`
</td></tr><tr><td>
RESTORETREEEXPANSION</td><td>
/O</td><td>

*(no value)*</td><td>

Restores the expansion state of the source folder tree that was previously remembered with **REMEMBERTREEEXPANSION**.

Combine with the **NAME** argument to restore a saved expansion.

*Example:* `Go RESTORETREEEXPANSION NAME=CurrentJob`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Restores the expansion state of the folder tree attached to the destination file display (when dual trees are enabled).

*Example:* `Go RESTORETREEEXPANSION=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Restores the expansion state of the folder tree attached to the left/top file display.

*Example:* `Go RESTORETREEEXPANSION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Restores the expansion state of the folder tree attached to the right/bottom file display (when dual trees are enabled).

*Example:* `Go RESTORETREEEXPANSION=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Restores the expansion state of both folder trees (or the single tree, whichever is applicable).

*Example:* `Go RESTORETREEEXPANSION=both`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the expansion of the tree to its initial state. Can be combined with the above keywords.

*Example:* `Go RESTORETREEEXPANSION=both,reset`
</td></tr><tr><td>
ROOT</td><td>
/O</td><td>

*(no value)*</td><td>

Navigate to the root of the current folder. For example, the root of *C:\Program Files\GPSoftware\Directory Opus* is *C:*.

*Example:* `Go ROOT`
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

Collapses the current drive's branch in the folder tree at the same time as navigating to the root folder.

*Example:* `Go ROOT=collapse`
</td></tr><tr><td>
RUNEMBEDDEDIFNOTFOUND</td><td>
/S</td><td>

*(no value)*</td><td>

This argument is used when [embedding a function](/Manual/customize/creating_your_own_buttons/embedded_functions.md) in the **Go FINDTITLE** command. Normally the embedded function will not be run if no Listers exist that match the supplied string. If the **RUNEMBEDDEDIFNOTFOUND** argument is specified, the embedded command will be run in the current Lister if a matching Lister is not found.

*Example:*  
`Go FINDTITLE PhotoWork RUNEMBEDDEDIFNOTFOUND
[Set VIEW=Thumbnails]
`
</td></tr><tr><td>
SWAP</td><td>
/S</td><td>

*(no value)*</td><td>

Swaps the folders displayed in the source and destination file displays.

*Example:* `Go SWAP`
</td></tr><tr><td>
SWITCHPATH</td><td>
/K/M</td><td>

*\<alternate path\> ...*</td><td>

Switches between (or cycles through) two or more paths. The **PATH** argument is used to provide the first path in the sequence, and then the **SWITCHPATH** argument provides the second and subsequent paths. When you run this command, Opus looks at the current path shown in the source file display. If it matches one of the provided paths, the next path in the sequence is read (and then the next, and then the next, and so on). If the current path does not match one of the provided ones the first path in the sequence is read.

\`\`Go C:\ SWITCHPATH D:\ E:\ F:\ G:\\\`
</td></tr><tr><td>
TABCLOSE</td><td>
/O</td><td>

*(no value)*</td><td>

Close the current [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md) in the source file display.

You can combine this with the **PATH** argument to specify the path of a tab that should be closed. When used in this context the **PATH** argument can accept wildcards - all tabs matching the supplied pattern will be closed.

The **TABPOS** argument can be used to specify the index (starting from 0) of a specific tab to close, or position relative to the current tab, or the position of the first or last tab. (The **PATH** argument can also be given a specific tab index, but this usage is deprecated in favor of **TABPOS**.)

*Examples:* Close the current tab: `Go TABCLOSE`  
Close all tabs showing a drive on C: `Go TABCLOSE PATH=C:*`  
Close the first tab: `Go TABCLOSE TABPOS=first`  
Close the last tab: `Go TABCLOSE TABPOS=last`  
Close the tab after the current tab: `Go TABCLOSE TABPOS=+1`  
Close the tab before the current tab: `Go TABCLOSE TABPOS=-1`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to close.

*Example:* `Go TABCLOSE=\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Close a folder tab in the left (or top) file display, irrespective of whether it is the source or not.

*Example:* `Go TABCLOSE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Close a folder tab in the right (or bottom) file display.

*Example:* `Go TABCLOSE=right TABPOS=-2`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Close a folder tab in the destination file display.

\`\`Go TABCLOSE=dest PATH=C:\\\`\*
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

Close the folder tab even if it is locked and closing individual locked tabs is disabled in Preferences.

*Example:* `Go TABCLOSE=force`

*Example:* `Go TABCLOSE=dest,force`
</td></tr><tr><td>
TABCLOSEALL</td><td>
/O</td><td>

*(no value)*</td><td>

Close all folder tabs except the current one.

When combined with the **TABGROUPLOAD** command, this overrides the tab group's *Close existing Folder Tabs* setting, and forces existing tabs to be closed.

*Example:* `Go TABCLOSEALL`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Close all folder tabs to the left of the current tab.

*Example:* `Go TABCLOSEALL=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Close all folder tabs to the right of the current tab.

*Example:* `Go TABCLOSEALL=right`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Lets you close tabs in the destination file display in a dual-display Lister.

*Example:* `Go TABCLOSEALL=dest,right`
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

Forces locked tabs to be closed. Normally locked tabs are not closed by this command.

*Example:* `Go TABCLOSEALL=right,force`
</td></tr><tr><td>
</td><td>
</td><td>

**expand**</td><td>

Expands tabs to Listers. The tabs will be closed in the current Lister, and each folder opened as a new Lister.

*Example:* `Go TABCLOSEALL=right,expand`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

When combined with the **TABGROUPLOAD** command, this overrides the tab group's *Close existing Folder Tabs* setting, and forces existing tabs to be retained.

This value has no meaning when not used in conjunction with **TABGROUPLOAD**.

*Example:* `Go TABGROUPLOAD=MyTabs TABCLOSEALL=no`
</td></tr><tr><td>
TABCOLOR</td><td>
/K</td><td>

*\<color\>*</td><td>

Assigns a custom color to the current tab. You can specify the color in the decimal form R,G,B (e.g. 127,192,55) or the hex form \#RRGGBB (e.g. \#ff0033).

*Example:* `Go TABCOLOR \#ff8000`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the current tab's color.

*Example:* `Go TABCOLOR=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**edit**</td><td>

Initiates editing of the current tab's color. You can use the **PATH** argument to specify the index of a tab to edit (with the left-most being index \#0).

*Example:* `Go TABCOLOR=edit`
</td></tr><tr><td>
TABDUPLICATE</td><td>
/O</td><td>

*(no value)*</td><td>

Duplicates the current folder tab.

*Example:* `Go TABDUPLICATE`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

Creates a duplicate of the current folder tab in the other file display of a dual-display Lister.

*Example:* `Go TABDUPLICATE=dual`
</td></tr><tr><td>
TABFINDEXISTING</td><td>
/S</td><td>

*(no value)*</td><td>

If the specified folder is open in another tab Opus will switch to that tab, otherwise the folder will be read into the current tab. Enables similar behavior to the **NEWTAB=findexisting** argument, except that a new tab is not opened if the path is not found.

*Example:* `Go /mydocuments TABFINDEXISTING`
</td></tr><tr><td>
TABGROUPFORCE</td><td>
/S</td><td>

*(no value)*</td><td>

Use in conjunction with the **TABGROUPLOAD** or **TABGROUPLIST** arguments to force folders in the loaded tabs to load immediately even if they would normally be blocked by the Auto-Loading settings on the [Automatic Reading](/Manual/preferences/preferences_categories/folders/automatic_reading.md) page in Preferences.

*Example:* `Go TABGROUPLOAD "My Tab Group" TABGROUPFORCE`
</td></tr><tr><td>
TABGROUPLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a list of your saved [Folder Tab Groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md) (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting a group from the list will open those tabs in the current file display.

This argument works when used in conjunction with the **USEQUALKEYS**, **TABGROUPFORCE** and **KEYARGS** arguments.

*Example:* `Go TABGROUPLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

Assigns the accelerator keys **0** through **9** to the first ten items displayed on the generated tab group list.

*Example:* `Go TABGROUPLIST=keys USEQUALKEYS`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

Displays icons for items on the generated tab group list.

*Example:* `Go TABGROUPLIST=keys,icons`
</td></tr><tr><td>
</td><td>
</td><td>

**nohighlight**</td><td>

Prevents the active tab group from being highlighted.

*Example:* `Go TABGROUPLIST=icons,nohighlight`
</td></tr><tr><td>
</td><td>
</td><td>

**savecurrent**</td><td>

Saves the current folder tab group (if any) before loading a new one. Without this, any changes to a tab group will be lost when loading another one, unless you explicitly save them.

As a special case, clicking the button for the current tab group will reload that group without first saving over it, giving you a way to reset to the group's last saved state.

If no tab group is currently loaded, nothing will be saved before loading the new tab group.

*Example:* `Go TABGROUPLIST=savecurrent`

Note that if you want Opus to save tab groups automatically in this way, you may also want to add something to trigger **Go TABGROUPSAVE=!current,!quiet** when listers close, or on other events such as opening/closing tabs or changing folders, depending on when you want the tab group to be updated. This probably also only makes sense if you only use one lister, since multiple listers may have differnet views of the currently open groups and save over each other. But if you want auto-saving tab groups, you're probably already using a single window all the time, as other people would use separate windows for separate tab groups and switch between windows instead of switching groups in a single window.
</td></tr><tr><td>
TABGROUPLOAD</td><td>
/K</td><td>

*\<group name\>*</td><td>

Loads the named folder tab group. This can be combined with **OPENINDUAL** etc. to open the tab group in another file display. You can also combine the **TABCLOSEALL** argument to override the tab group's *Close existing Folder Tabs* setting.

*Example:* `Go TABGROUPLOAD "My Tab Group" TABCLOSEALL=no`
</td></tr><tr><td>
TABGROUPSAVE</td><td>
/O</td><td>

*(no value)*</td><td>

Save the current set of folder tabs as a new tab group. You will be prompted to provide a name for the group.

*Example:* `Go TABGROUPSAVE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<group name\>*</td><td>

Save the current set of folder tabs using the specified group name.

*Example:* `Go TABGROUPSAVE "My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!both**</td><td>

In a dual-display Lister, this will save the tabs from both file displays to a single group using the "specific sides" option. You can also specify a group name by following the keyword with a comma. (The group name, if any, must come after the keyword and not before.)

*Example:* `Go TABGROUPSAVE="!both,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!closeall**</td><td>

Saves the tab group such that it will close all existing tabs when it is loaded (unless overridden at the time of loading). If neither **!closeall** nor **!nocloseall** are specified, saving over an existing group will preserved its mode, new groups created non-interactively will close existing tabs by default, and new groups created interactively will default to the mode used the last time the interactive dialog was displayed. (The group name, if any, must come after the keyword and not before.)

*Example:* `Go TABGROUPSAVE="!both,!closeall,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!nocloseall**</td><td>

Saves the tab group such that it will not close any existing tabs when it is loaded (unless overridden at the time of loading). See **!closeall**, above, for more information. (The group name, if any, must come after the keyword and not before.)

*Example:* `Go TABGROUPSAVE="!both,!nocloseall,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!current**</td><td>

Saves over the folder tab group which was last loaded. The **!both** keyword is ignored, and instead the mode is inherited from the existing group. Add the **!quiet** keyword to make the command do nothing if there is no current tab group to save over; otherwise you will be prompted for the name of a new group in that situation.

*Example:* `Go TABGROUPSAVE="!current"`
</td></tr><tr><td>
</td><td>
</td><td>

**!quiet**</td><td>

Combine **!quiet** with **!current** to prevent being asked to name a new tab group if there isn't one to save over.

*Example:* `Go TABGROUPSAVE="!current,!quiet"`
</td></tr><tr><td>
</td><td>
</td><td>

**!unless**</td><td>

Combine **!unless** with **!current** to tell the command to save the current group unless it has a particular name. You probably won't need to use this directly, but it is how the **Go TABGROUPLIST=savecurrent** command avoids saving over the current group if you click its button to reload it.

*Example:* `Go TABGROUPSAVE="!current,!quiet,!unless,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!forget**</td><td>

Tells the file display to forget the name of the last tab group it loaded. Combine with **!both** to make both sides of a dual-display lister forget. You may wish to use this if you load a tab group and then modify it to the point that it no longer has any connection to the original group, and you do not want it to remain selected in any tab group lists.

*Example:* `Go TABGROUPSAVE="!forget"`
</td></tr><tr><td>
TABLINK</td><td>
/K</td><td>

**on**</td><td>

In a dual-display Lister, links the current active tab in the source file display with the current active tab in the destination file display.

*Example:* `Go TABLINK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

If the currently active tab is linked, this will unlink it.

*Example:* `Go TABLINK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles tab linking on or off for the currently active tabs in both left and right file displays.

*Example:* `Go TABLINK=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**navlock**</td><td>

Use in conjunction with **on** or **toggle** to specify that the tab is to be linked in [navigation lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) mode (so that it follows the other tab whenever the folder is changed).

*Example:* `Go TABLINK=toggle,navlock`
</td></tr><tr><td>
</td><td>
</td><td>
reset</td><td>

When two tabs are linked in navigation lock mode, the reset keyword lets you reset the sync position to the current locations (for recovering when they get out of sync).

*Example:* `Go TABLINK=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**unlinkall**</td><td>

Unlinks all linked tabs in the current Lister.

*Example:* `Go TABLINK=unlinkall`
</td></tr><tr><td>
</td><td>
</td><td>

*\<tab1\>,\<tab2\>*</td><td>

When used from a [script](/Manual/scripting/README.md), you can pass the default value of two **[Tab](../../scripting_reference/scripting_objects/tab.md)** objects to specify the precise tabs you wish to link. The two values must be comma-separated. If only one **[Tab](../../scripting_reference/scripting_objects/tab.md)** object is specified, it will be unlinked if it is currently linked.

*Example:* `Go TABLINK=\<tab1\>,\<tab2\>,navlock`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

Generates the standard tab link menu. This is included on the default folder tab [context menu](/Manual/customize/the_customize_dialog/context_menus.md).

*Example:* `Go TABLINK=menu`
</td></tr><tr><td>
TABLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a list of the currently open folder tabs (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting a tab from the list will switch to that tab. You can also drag and drop files to the items in the list to copy them to that tab's folder.

By default the tabs shown are those from the current source file display, but you can combine with the **OPENINLEFT**, **OPENINRIGHT** and **OPENINDEST** arguments to display tabs from other file displays.

*Example:* `Go TABLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

Assigns the accelerator keys **0** through **9** to the first ten items displayed on the generated tab list.

*Example:* `Go TABLIST=keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

Sorts the tab list alphabetically (without this, the items in the list are listed in the same order as the physical tabs). The sort order is based on the folder name (or tab label).

*Example:* `Go TABLIST=sort,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sortpath**</td><td>

Sorts the tab list alphabetically, based on the full path of each folder.

*Example:* `Go TABLIST=sortpath`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

Displays folder icons for each tab in the list.

*Example:* `Go TABLIST=sortpath,icons`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

Only displays the folder name for each tab rather than the full path. Does not affect tabs which use custom labels; custom labels are always displayed as-is.

*Example:* `Go TABLIST=sort,namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**maxwidth=***\<width\>*</td><td>

Specifies a maximum width (in characters) for each item in the list. When showing the full path of each tab, you may want to use this to stop the tab list from being too wide. If not specified, a maximum width of 50 is used by default - you can disable this (and have no maximum width at all) by specifying **maxwidth=0**.

Note that because this parameter requires an equals sign, you must enclose the whole value of the **TABLIST** argument in quotes.

*Example:* `Go TABLIST="keys,maxwidth=70"`
</td></tr><tr><td>
TABLOCK</td><td>
/K</td><td>

**lock**</td><td>

Lock the current [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md) to prevent any folder changes. Attempts to change the folder will result in a new tab being created.

*Example:* `Go TABLOCK=lock`
</td></tr><tr><td>
</td><td>
</td><td>

**lockchanges**</td><td>

Lock the current tab. Folder changes will be allowed, but the tab will revert to its original (locked) directory if it is clicked, or if the focus is moved to another tab and then back to this one. You can also use the command **Go TABLOCKDIR** to revert to the original directory.

*Example:* `Go TABLOCK=lockchanges`
</td></tr><tr><td>
</td><td>
</td><td>

**lockreuse**</td><td>

Lock the current tab. Attempts to change folder will result in the first already existing, unlocked tab being used to read the new directory. A new tab will be opened if there are no unlocked tabs that can be used.

*Example:* `Go TABLOCK=lockreuse`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Unlock the current folder tab.

*Example:* `Go TABLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Combine with the various **lock** keywords to toggle that lock mode on or off.

*Example:* `Go TABLOCK=lockchanges,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Lock or unlock all folder tabs.

*Example:* `Go TABLOCK=lock,all`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Lock or unlock all tabs to the left of the current tab.

*Example:* `Go TABLOCK=lockchanges,toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Lock or unlock all tabs to the right of the current tab.

*Example:* `Go TABLOCK=off,right`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

Generates the standard tab lock menu. This is included on the default folder tab [context menu](/Manual/customize/the_customize_dialog/context_menus.md).

*Example:* `Go TABLOCK=menu`
</td></tr><tr><td>
TABLOCKDIR</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates the original (locked) directory of the current folder tab. This is the directory that was shown in the tab when it was set to 'Lock Allow Changes' mode. You can use this to return to the locked folder, or open it in another tab or Lister. If the current tab is not locked this argument behaves the same as the **CURRENT** argument.

*Example:* `Go TABLOCKDIR`
</td></tr><tr><td>
TABMOVE</td><td>
/O</td><td>

*(no value)*</td><td>

Move the current folder tab to the other file display. (See **TABPOS** for repositioning tabs without changing sides.) The Lister will be set to dual-display mode if it's not in that mode already.

*Example:* `Go TABMOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**split**</td><td>

Splits the folder tabs currently open in a single-display Lister. The Lister will be set to dual-display mode, and all tabs from the current tab onwards will be moved to the other display. If the Lister is already in dual-display mode this command has no effect.

*Example:* `Go TABMOVE=split`
</td></tr><tr><td>
</td><td>
</td><td>

**splitlister**</td><td>

Splits the folder tabs in the current file display to a new Lister. All tabs from the current tab onwards will be closed in the current display, and reopened in a new Lister.

*Example:* `Go TABMOVE=splitlister`
</td></tr><tr><td>
</td><td>
</td><td>

*\<new position\>*</td><td>

Specify the new position for the moved tab. You can specify an absolute position, **-1** to indicate the same relative position, and **-2** to position the moved tab to the right of the currently active tab. If not specified, the moved tab will be positioned at the end of all existing tabs.

*Example:* `Go TABMOVE=-2`
</td></tr><tr><td>
</td><td>
</td><td>

**active**</td><td>

If specified, the moved tab will be made active. Otherwise the previously active tab in the other file display remains active.

*Example:* `Go TABMOVE=active,-2`
</td></tr><tr><td>
TABNAME</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the name of the current tab if one has been assigned. This will reset the tab label back to the default which is to show the name of the current folder.

*Example:* `Go TABNAME`
</td></tr><tr><td>
</td><td>
</td><td>

\<*tab name*\></td><td>

Assigns the specified name to the current tab. If combined with the **NEWTAB** argument the name will be assigned to the newly created tab.

*Example:* `Go C:\Work NEWTAB TABNAME "My Work Dir"`

You can use several special "tokens" in the tab name to insert various pieces of information:

|        |                                           |
|--------|-------------------------------------------|
| **%P** | full path of the current (source) folder  |
| **%N** | name of the current (source) folder       |
| **%R** | drive root of the current (source) folder |
| **%!** | hide section                              |

*Example:* `Go TABNAME "%R - %N"`

The **%!** code lets you hide sections in the string where all other tokens inside the section are empty.

*Example:* `Go TABNAME "%!Drive %R : %!%N"`

That means that if the **%R** token expands to an empty string, the result will be just "%N" (the name of the folder).
</td></tr><tr><td>
</td><td>
</td><td>

**!edit**</td><td>

Initiates editing of the current tab's name. You can use the **PATH** argument to specify the index of a tab to edit (with the left-most being index \#0).

*Example:* `Go TABNAME=!edit`
</td></tr><tr><td>
TABPOS</td><td>
/K</td><td>

**first**</td><td>

When used with the **NEWTAB** argument, causes the newly created tab to appear as the first on the tab bar. When used with **TABCLOSE**, closes the first tab. When used on its own, repositions the active folder tab so it is first on the tab bar.

*Example:* `Go C:\ NEWTAB TABPOS=first`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to reposition as the second parameter.

*Example:* `Go TABPOS=first,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**last**</td><td>

When used with the **NEWTAB** argument, causes the newly created tab to appear as the last on the tab bar. When used with **TABCLOSE**, closes the last tab. When used on its own, repositions the active folder tab so it is last on the tab bar.

*Example:* `Go TABPOS=last`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to reposition as the second parameter.

*Example:* `Go TABPOS=last,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**+1**</td><td>

When used with the **NEWTAB** argument, causes the newly created tab to appear as to the right of the currently active tab. When used with **TABCLOSE**, closes the tab to the right of the active tab. When used on its own, repositions the active folder tab to the right of its current position on the tab bar. You can also use +2 for two positions to the right, and so on.

*Example:* `Go TABPOS=+1`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to reposition as the second parameter.

*Example:* `Go TABPOS=+3,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**-1**</td><td>

When used with the **NEWTAB** argument, causes the newly created tab to appear to the left of the currently active tab. When used with **TABCLOSE**, closes the tab to the left of the active tab. When used on its own, repositions the active folder tab to the left of its current position on the tab bar. You can also use -2 for two positions to the left, and so on.

*Example:* `Go TABPOS=-1`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to reposition as the second parameter.

*Example:* `Go TABPOS=-2,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

*\<index\>*</td><td>

When used with the **NEWTAB** argument, specifies the position for the newly created tab. When used with **TABCLOSE**, specifies the position of the tab to close. When used on its own, repositions the active folder tab to a specific place on the tab bar. 0 is the first tab (you can also use "first"), 1 the second, 2 the third, and so on.

*Example:* `Go D:\ NEWTAB TABPOS=2`

When used from a [script](/Manual/scripting/README.md), you can pass the default value of a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object to specify the tab you wish to reposition as the second parameter.

*Example:* `Go TABPOS=3,\<tab\>`
</td></tr><tr><td>
TABSCROLL</td><td>
/O</td><td>

*(no value)*</td><td>

If there are more tabs open than will fit in the display, this command displays the tab overflow menu (useful if you want to bind this to a hotkey). You can combine this with the **OPENINDEST**, **OPENINLEFT** and **OPENINRIGHT** arguments to display the overflow menu in other file displays.

*Example:* `Go TABSCROLL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<delta\>*</td><td>

Scroll the folder tabs left or right if there are more tabs open than will fit in the display.

*Example:* `Go TABSCROLL=-1`
</td></tr><tr><td>
TABSELECT</td><td>
/K</td><td>

**first**</td><td>

Select (make active) the first folder tab in the current file display.

*Example:* `Go TABSELECT=first`
</td></tr><tr><td>
</td><td>
</td><td>

**last**</td><td>

Select the last folder tab in the current file display.

*Example:* `Go TABSELECT=last`
</td></tr><tr><td>
</td><td>
</td><td>

**prev**</td><td>

Reselect the previously selected folder tab.

*Example:* `Go TABSELECT=prev`
</td></tr><tr><td>
</td><td>
</td><td>

**+1**</td><td>

Select the next folder tab.

*Example:* `Go TABSELECT +1`
</td></tr><tr><td>
</td><td>
</td><td>

**-1**</td><td>

Select the previous folder tab.

*Example:* `Go TABSELECT -1`
</td></tr><tr><td>
</td><td>
</td><td>

**home**</td><td>

Resets a locked tab to its "home" directory. This is equivalent to **Go TABLOCKDIR**. If the current tab is not set to 'Locked Allow Changes' mode this command has no effect.

*Example:* `Go TABSELECT home`
</td></tr><tr><td>
</td><td>
</td><td>

*\<index\>*</td><td>

Select a specific folder tab. The index is 0 relative (so **Go TABSELECT 0** is equivalent to **Go TABSELECT first**).

*Example:* `Go TABSELECT=5`
</td></tr><tr><td>
</td><td>
</td><td>

\$*\<tab\>*</td><td>

Select a specific folder tab from a script. If you have a **[Tab](../../scripting_reference/scripting_objects/tab.md)** object and want to activate it, add it to the command string prefixed by a **\$** character.

*Example:* `cmd.RunCommand("Go TABSELECT=\$" + tab)`
</td></tr><tr><td>
TABSWAP</td><td>
/O</td><td>

*(no value)*</td><td>

Swaps the active tab in the left file display with the active tab in the right file display.

*Example:* `Go TABSWAP`
</td></tr><tr><td>
</td><td>
</td><td>

*\<index1\>*,*\<index2\>*</td><td>

Specify indices to swap a specific tab from the left file display with a specific tab in the right file display.

*Example:* `Go TABSWAP=0,0`
</td></tr><tr><td>
TABSWITCHER</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the "tab switcher", a popup list of tabs open in the current Lister. You can use it to switch to another tab in the same way Alt+Tab in Windows lets you switch to another window.

By default the tab switcher is bound to the Ctrl+Tab key; you can use this command to bind it to a different key or trigger it via a mouse button, etc.

*Example:* `Go TABSWITCHER`
</td></tr><tr><td>
TABUNDOCLOSE</td><td>
/S</td><td>

*(no value)*</td><td>

Undoes the last action that resulted in one or more tabs being closed.

*Example:* `Go TABUNDOCLOSE`
</td></tr><tr><td>
TITLE</td><td>
/K</td><td>

*\<custom title\>*</td><td>

Specifies a custom title when opening a new Lister using the **NEW** argument. You can use several special "tokens" in the title string to insert various pieces of information:

|        |                                                                       |
|--------|-----------------------------------------------------------------------|
| **%P** | full path of the current (source) folder                              |
| **%N** | name of the current (source) folder                                   |
| **%R** | drive root of the current (source) folder                             |
| **%D** | full path of the destination folder                                   |
| **%M** | name of the destination folder                                        |
| **%G** | target if the folder is a junction or softlink                        |
| **%1** | full path in the left file display                                    |
| **%2** | full path in the right file display                                   |
| **%3** | folder name in the left file display                                  |
| **%4** | folder name in the right file display                                 |
| **%L** | name of the Layout the Lister came from (if any)                      |
| **%S** | name of the current Style selected in the Lister (if any)             |
| **%T** | complete original title (useful for simply adding a prefix or suffix) |
| **%!** | hide section                                                          |

*Example:* `Go NEW TITLE "Directory Opus - %N"`

The **%!** code lets you hide sections in the string where all other tokens inside the section are empty.

*Example:* `Go NEW TITLE "%!%T - %!Directory Opus"`

That means that if the **%T** token expands to an empty string, the result will be just "Directory Opus" rather than " - Directory Opus".
</td></tr><tr><td>
TOFRONT</td><td>
/S</td><td>

*(no value)*</td><td>

Makes the Lister the active window and brings it to the front. Typically used when sending commands from outside of Opus, to make sure the window that reads the folder is visible.

*Example:* `Go C:\ TOFRONT`
</td></tr><tr><td>
TREECOLLAPSE</td><td>
/O</td><td>

*(no value)*</td><td>

Collapses the selected branch in the tree belonging to the source file display.

*Example:* `Go TREECOLLAPSE`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Collapses the selected branch in the tree belonging to the destination file display (when dual trees are enabled).

*Example:* `Go TREECOLLAPSE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Collapses the selected branch in the left/top file display.

*Example:* `Go TREECOLLAPSE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Collapses the selected branch in the right/bottom file display (when dual trees are enabled).

*Example:* `Go TREECOLLAPSE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Collapses the selected branches in both source and destination trees.

*Example:* `Go TREECOLLAPSE=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Collapses the selected branches in the tree which currently has input focus (or the tree belonging to the file display with input focus).

*Example:* `Go TREECOLLAPSE=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Collapse all folders (and all their child folders, and so on) below the selected folder, not just the selected folder.

*Example:* `Go TREECOLLAPSE=all,both`
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

Collapse just the first level of descendants below the selected folder.

*Example:* `Go TREECOLLAPSE=left,first`
</td></tr><tr><td>
</td><td>
</td><td>

**second**</td><td>

Collapse the first and second levels of descendants below the selected folder.

*Example:* `Go TREECOLLAPSE=second`
</td></tr><tr><td>
TREEEXPAND</td><td>
/O</td><td>

*(no value)*</td><td>

When used in conjunction with reading a folder, this command automatically expands the folder tree to display the contents of the new folder. This is only of use if the **Automatically expand to current folder** option on the **[Folder Tree / Expand / Collapse](/Manual/preferences/preferences_categories/folder_tree/expand_collapse/README.md)** Preferences page is turned off.

You can also use this command by itself, to expand the currently selected folder.

*Example:* `Go "C:\Program Files\GPSoftware\Directory Opus" NEW TREEEXPAND`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Expands the selected branch in the tree belonging to the destination file display (when dual trees are enabled).

*Example:* `Go TREEEXPAND=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Expands the selected branch in the left/top file display.

*Example:* `Go TREEEXPAND=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Expands the selected branch in the right/bottom file display (when dual trees are enabled).

*Example:* `Go TREEEXPAND=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Expands the selected branches in both source and destination trees.

*Example:* `Go TREEEXPAND=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Expands the selected branches in the tree which currently has input focus (or the tree belonging to the file display with input focus).

*Example:* `Go TREEEXPAND=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Expand all folders (and all their child folders, and so on) below the selected folder, not just the selected folder.

*Example:* `Go TREEEXPAND=all,both`
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

Expand just the first level of descendants below the selected folder.

*Example:* `Go TREEEXPAND=left,first`
</td></tr><tr><td>
</td><td>
</td><td>

**second**</td><td>

Expand the first and second levels of descendants below the selected folder.

*Example:* `Go TREEEXPAND=second`
</td></tr><tr><td>
TREESETPINSTATE</td><td>
/O</td><td>

*(no value)*</td><td>

Toggles the "pin" state of the currently selected folder in the [folder tree](/Manual/basic_concepts/the_lister/navigation/folder_tree.md). Pinned folders always stay expanded - they can't be collapsed. Note that folder pinning needs to be enabled from the [pins](/Manual/preferences/preferences_categories/folder_tree/expand_collapse/pins.md) page in Preferences for this command to have any effect.

*Example:* `Go TREESETPINSTATE`
</td></tr><tr><td>
</td><td>
</td><td>

**on**</td><td>

Turns on the "pin" state of the currently selected folder.

*Example:* `Go TREESETPINSTATE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the "pin" state of the currently selected folder.

*Example:* `Go TREESETPINSTATE=off`
</td></tr><tr><td>
UNDOCLOSELISTER</td><td>
/O</td><td>

*(no value)*</td><td>

Reopens the last Lister that was closed (so if, for example, you accidentally close the Lister you're working with, this command would bring it back).

*Example:* `Go UNDOCLOSELISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**closeexisting**</td><td>

Reopens the last Lister that was closed, and closes all other open Listers.

*Example:* `Go UNDOCLOSELISTER=closeexisting`
</td></tr><tr><td>
UP</td><td>
/S</td><td>

*(no value)*</td><td>

Navigate [up](/Manual/basic_concepts/the_lister/navigation/up_forwards_back.md) to the parent of the current folder. You can combine this with **OPENINDUAL** etc. to open the parent of the current folder in another file display or Lister. This can also be combined with the **BACK** argument - in that case, if the parent of the current folder is also the previous folder in the history list, Opus will move back rather than up - preserving the file selection and other state of the previous folder.

*Example:* `Go UP`
</td></tr><tr><td>
USEQUALKEYS</td><td>
/S</td><td>

*(no value)*</td><td>

Activates pre-configured behaviour for the main qualifier keys - **Control** will open the folder in the dual-display, **Shift** in a new Lister and **Alt** in a new tab.

This is equivalent to **KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB**.

*Example:* `Go C:\ USEQUALKEYS`
</td></tr><tr><td>
USER</td><td>
/K</td><td>

*\<user name\>*</td><td>

Can be used when certain folder aliases are supplied for the **PATH** argument. This lets you specify an alternative user name, to access a specific user's instance of a system folder (providing you have the appropriate permissions, of course). If the specified alias doesn't support multiple users this argument has no effect.

*Example:* `Go /desktopdir USER="Leo Nudelson"`
</td></tr><tr><td>
VIEW</td><td>
/K</td><td>

**largeicons**</td><td>

Changes the [view mode](/Manual/basic_concepts/the_lister/view_modes.md) of the new folder to *Large Icons* mode.

*Example:* `Go CURRENT NEWTAB VIEW=largeicons`
</td></tr><tr><td>
</td><td>
</td><td>

**smallicons**</td><td>

Changes the view mode of the new folder to *Small Icons* mode.

*Example:* `Go C:\ VIEW smallicons`
</td></tr><tr><td>
</td><td>
</td><td>

**list**</td><td>

Changes the view mode to *List* mode.

*Example:* `Go {destpath} VIEW list`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

Changes the view mode to *Details* mode.

*Example:* `Go CURRENT LAYOUT=PhotoLayout VIEW=details`
</td></tr><tr><td>
</td><td>
</td><td>

**power**</td><td>

Changes the view mode to *Power* mode.

*Example:* `Go NEW VIEW=power`
</td></tr><tr><td>
</td><td>
</td><td>

**thumbnails**</td><td>

Changes the view mode to *Thumbnails* mode.

*Example:* `Go /desktop VIEW=thumbnails`
</td></tr><tr><td>
</td><td>
</td><td>

**tiles**</td><td>

Changes the view mode to *Tiles* mode.

*Example:* `Go @WorkFTP NEWTAB VIEW tiles`
</td></tr><tr><td>
WHENDUAL</td><td>
/K</td><td>

**checkmouse**</td><td>

This works in conjunction with the **BACK**, **FORWARD** and **UP** arguments and is designed to be used with "app command" hotkeys like the Back button on a mouse. It lets you make navigation commands triggered from the mouse act on the file display underneath the mouse pointer in a dual display Lister, rather than, as is the default, the source file display.

*Example:* `Go BACK WHENDUAL=checkmouse`
</td></tr><tr><td>
</td><td>
r</td><td>

**anydevice**</td><td>

Use with the **checkmouse** argument to cause the **WHENDUAL** argument to activate when the command is run from a non-mouse device (e.g. when the command is bound to a **Back** button on a keyboard).

*Example:* `Go BACK WHENDUAL=checkmouse,anydevice`
</td></tr><tr><td>
</td><td>
</td><td>

**deffocus**</td><td>

Add the deffocus argument to cause the command to fall back to the original behavior if the mouse pointer isn't currently over either of the file displays.

*Example:* `Go BACK WHENDUAL=checkmouse,deffocus`
</td></tr></tbody>
</table>

