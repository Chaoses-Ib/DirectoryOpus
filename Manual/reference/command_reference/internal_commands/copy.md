# Copy

The **Copy** internal command can be used to:

- Copy and move files and folders
- Create and add files to archives
- Extract files from archives
- Perform simple one-way file synchronization
- Create links, shortcuts and junctions
- Install fonts
- Send files via email
- Add items to [file collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), and include folders in [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md)

  
**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ADDTOARCHIVE</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **[Add to Archive](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.md)** dialog, to create an archive from the selected files. The dialog will default to creating a Zip file.

*Example:* `Copy ADDTOARCHIVE`

The **CREATEFOLDER** argument can be used to change the default archive name.

*Example:* `Copy ADDTOARCHIVE CREATEFOLDER="Backup"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<archive format\>*</td><td>

Displays the **[Add to Archive](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.md)** dialog with the archive type set to the specified format (given as the file extension of the desired format).

*Example:* `Copy ADDTOARCHIVE=.rar`

The archive format can be optionally followed by parameters that are specific to the selected format. Currently the only format that defines optional parameters is Zip, those are listed below.

*Example:* `Copy ADDTOARCHIVE=.zip,fullpaths`

You can also use this command to create a self-extracting archive from the selected files, with the following arguments:

*Example:* `Copy ADDTOARCHIVE=.zip+sfx`
</td></tr><tr><td>
</td><td>
</td><td>

**fullpaths**</td><td>

When creating Zip archives, this turns on the *Save full file paths* option by default.

*Example:* `Copy ADDTOARCHIVE=.zip,fullpaths`
</td></tr><tr><td>
</td><td>
</td><td>

**nofullpaths**</td><td>

When creating Zip archives, this disables the *Save full file paths* option.

*Example:* `Copy ADDTOARCHIVE=.zip,nofullpaths`
</td></tr><tr><td>
</td><td>
</td><td>

**keepfolder**</td><td>

Modifies the behaviour when only a single folder is selected - instead of the items within the folder being added, the folder itself will be added to the archive.

*Example:* `Copy ADDTOARCHIVE=.zip,keepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeepfolder**</td><td>

Adds the contents of the folder when only a single folder is selected.

*Example:* `Copy ADDTOARCHIVE=.zip,nokeepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**comp:***\<compression\>*</td><td>

Specifies the compression level when creating Zip archives. You can use one of the keywords **store**, **fastest**, **fast**, **normal**, **good** and **best**, or provide a number from 0 to 19. Numbers 10 and above enable enhanced compression; otherwise the **enhanced** or **noenhanced** keywords can also be used to override the default.

*Example:* `Copy ADDTOARCHIVE=.zip,comp:best,enhanced`
</td></tr><tr><td>
</td><td>
</td><td>

**split:***\<size\>*</td><td>

When creating Zip archives, this sets the default value for the *Split archive* option.

*Example:* `Copy ADDTOARCHIVE=.zip,fullpaths,split:2.5MB`
</td></tr><tr><td>
</td><td>
</td><td>

**nosplit**</td><td>

When creating Zip archives, this disables the *Split archive* option.

*Example:* `Copy ADDTOARCHIVE=.zip,nosplit,nofullpaths`
</td></tr><tr><td>
ARCHIVE</td><td>
/O</td><td>

*(no value)*</td><td>

Adds all selected files and folders to a Zip file named after the first selected item. Note that if only a single folder is selected, the items *within* that folder are added rather than the folder itself - this prevents you from ending up with a Zip file containing an unnecessary sub-folder.

*Example:* `Copy ARCHIVE`

The **CREATEFOLDER** argument can be used to change the default archive name.

*Example:* `Copy ARCHIVE CREATEFOLDER="Backup"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<archive format\>*</td><td>

Adds all selected files and folders to an archive of the specified format. The archive format can be optionally followed by parameters that are specific to the selected format - see **ADDTOARCHIVE** above for a list of these.

*Example:* `Copy ARCHIVE=.rar`
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

Each selected item will be added to its own archive, rather than all items being added to the one archive.

*Example:* `Copy ARCHIVE=single`
</td></tr><tr><td>
</td><td>
</td><td>

**keepfolder**</td><td>

Modifies the behaviour when only a single folder is selected - instead of the items within the folder being added, the folder itself will be added to the archive.

*Example:* `Copy ARCHIVE=keepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeepfolder**</td><td>

Adds the contents of the folder when only a single folder is selected.

*Example:* `Copy ARCHIVE=nokeepfolder`
</td></tr><tr><td>
AS</td><td>
/O</td><td>

*(no value)*</td><td>

When copying or moving files, you will be prompted to enter a new name for each file.

*Example:* `Copy MOVE AS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<new name\>*</td><td>

Specifies the new name or [wildcard pattern](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for the copied or moved files. This only changes the names; if you want to specify the destination path, use the **TO** argument.

*Example:* `Copy AS *.bak HERE`
</td></tr><tr><td>
AUTOSELECT</td><td>
/K</td><td>

**yes**</td><td>

Overrides the state of the *Automatically select newly copied files* option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** Preferences page. Newly copied files will always be selected.

*Example:* `Copy DUPLICATE AUTOSELECT=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Newly copied files will not be selected, no matter what the *Automatically select newly copied files* option is set to.

*Example:* `Copy AUTOSELECT=no`
</td></tr><tr><td>
BUFSIZE</td><td>
/K/N</td><td>

*\<size in bytes\>*</td><td>

Overrides the **copy_buffer_size** setting on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences. The buffer size is specified in bytes, if no units are specified, and you can also use KB, MB and GB to specify larger sizes.

This buffer is in addition to any buffering provided by the filesystem, hardware, and so on; it is not connected to the non-buffered IO mode controlled by the **NONBUFIO** argument and **copy_nonbufferio_threshold** Preferences option.

*Example:* `Copy BUFSIZE 128KB`

This has no effect when doing simple file-to-file copies and delegating to the very-high-level Windows file-copy API, since that API performs its own buffering. See the **DELEGATE** argument for more detail.
</td></tr><tr><td>
BURNCD</td><td>
/S</td><td>

*(no value)*</td><td>

Invokes the system CD Burning Wizard, which initiates burning of any files you have previously copied to the CD staging area.

*Example:* `Copy BURNCD`
</td></tr><tr><td>
CLEARREADONLY</td><td>
/K</td><td>

**yes**</td><td>

Clear the read-only attribute. When copying files from a CD this overrides the **Clear read-only flag when copying from CDs** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy CLEARREADONLY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not clear the read-only flag when copying files.

*Example:* `Copy CLEARREADONLY=no`
</td></tr><tr><td>
COLLLIST</td><td>
/S</td><td>

*(no value)*</td><td>

Displays a dynamically generated list of [file collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) - you can add selected files and folders to a file collection simply by selecting it from this list. Acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md). Most useful when used in a drop-down menu or on a [context menu](/Manual/file_types/filetype_editor/context_menu.md).

*Example:* `Copy COLLLIST`
</td></tr><tr><td>
COPYATTR</td><td>
/K</td><td>

**yes**</td><td>

Preserves file attributes when copying files or folders.

Overrides the **Copy file attributes** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy COPYATTR=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not preserve file attributes (the newly copied file will have the default file attributes for a newly created file).

*Example:* `Copy COPYATTR=no`
</td></tr><tr><td>
COPYDESC</td><td>
/K</td><td>

**yes**</td><td>

Preserves file descriptions when copying files or folders, when the descriptions are not stored within NTFS ADS or when NTFS ADS is not otherwise being copied.

Overrides the **Copy file descriptions (if not in ADS, or not already copying ADS)** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page, where the option and NTFS ADS are described in detail.

*Example:* `Copy COPYDESC=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not preserve file descriptions beyond what may be done if NTFS ADS are being copied.

*Example:* `Copy COPYDESC=no`
</td></tr><tr><td>
COPYDIRTIMES</td><td>
/K</td><td>

**all**</td><td>

Preserves the Modified and Created timestamps of copied folders.

Overrides the **Copy timestamps** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page and the **no_copy_dir_dates** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** Preferences page.

*Example:* `Copy COPYDIRTIMES=all`

In all cases, the Accessed timestamp is handled the same as the Modified timestamp. Accessed timestamps are not mentioned explicitly because they are a legacy feature of Windows that are not usually worth thinking about.
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Prevents preservation of the Modified and Created timestamps of copied folders; instead, the timestamps will be reset to the date and time the copy is made.

*Example:* `Copy COPYDIRTIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

Preserves the Modified timestamps while preventing preservation of the Created timestamps of copied folders.

*Example:* `Copy COPYDIRTIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

Preserves the Created timestamps while preventing preservation of the Modified timestamps of copied folders.

*Example:* `Copy COPYDIRTIMES=onlycreated`
</td></tr><tr><td>
COPYFILETIMES</td><td>
/K</td><td>

**all**</td><td>

Preserves the Modified and Created timestamps of copied files.

Overrides the **Copy timestamps** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy COPYFILETIMES=all`

In all cases, the Accessed timestamp is handled the same as the Modified timestamp. Accessed timestamps are not mentioned explicitly because they are a legacy feature of Windows that are not usually worth thinking about.
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Prevents preservation of the Modified and Created timestamps of copied files; instead, the timestamps will be reset to the date and time the copy is made.

*Example:* `Copy COPYFILETIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

Preserves the Modified timestamps while preventing preservation of the Created timestamps of copied files.

*Example:* `Copy COPYFILETIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

Preserves the Created timestamps while preventing preservation of the Modified timestamps of copied files.

*Example:* `Copy COPYFILETIMES=onlycreated`
</td></tr><tr><td>
COPYOWNER</td><td>
/K</td><td>

**local**</td><td>

Copy file owner information, when the copy takes place between local drives only.

Overrides the **Copy owner** and subordinate **Local drives only** options on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

Note that setting the file owner requires elevation and may produce a UAC prompt.

*Example:* `Copy COPYOWNER=local`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Copy file owner information for all drives, not just local ones.

*Example:* `Copy COPYOWNER=all`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not copy file owner information.

*Example:* `Copy COPYOWNER=no`
</td></tr><tr><td>
COPYPROPERTIES</td><td>
/K</td><td>

**yes**</td><td>

Always copy NTFS ADS properties/metadata when copying files and folders.

Overrides the **Copy NTFS ADS** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page, where the three options are explained in detail.

*Example:* `Copy COPYPROPERTIES=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Always remove NTFS ADS metadata when copying files.

*Example:* `Copy COPYPROPERTIES=no`
</td></tr><tr><td>
</td><td>
</td><td>

**fastest**</td><td>

Copy NTFS ADS metadata when copying files, unless it is slower to do so.

*Example:* `Copy COPYPROPERTIES=fastest`
</td></tr><tr><td>
COPYSECURITY</td><td>
/K</td><td>

**yes**</td><td>

Copy security permissions when copying files between NTFS drives.

Overrides the **Copy security permissions** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy COPYSECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not copy security permissions. Newly copied files will inherit the default security permissions of the destination folders.

*Example:* `Copy COPYSECURITY=no`
</td></tr><tr><td>
COPYSPARSE</td><td>
/K</td><td>

**yes**</td><td>

Recreate sparse regions in the copied file (when the source file is sparse).

Overrides the **Copy sparse files as sparse** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy COPYSPARSE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not recreate sparse regions in the copied file. Newly copied files will occupy their full size on disk.

*Example:* `Copy COPYSPARSE=no`
</td></tr><tr><td>
COPYTOCOLL</td><td>
/K</td><td>

**member**</td><td>

When copying (adding) folders to a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), add them as members of the collection (overrides the **When copying folders to a Collection** option on the **[Copying Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.md)** Preferences page).

*Example:* `Copy COPYTOCOLL=member`
</td></tr><tr><td>
</td><td>
</td><td>

**sub**</td><td>

Copy folders to collections as sub-collections (the contents of the folder will be added as member items to the newly created sub-collection).

*Example:* `Copy COPYTOCOLL=sub`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

Ask how to copy folders to collections.

*Example:* `Copy COPYTOCOLL=ask`
</td></tr><tr><td>
CREATEFOLDER</td><td>
/O</td><td>

*(no value)*</td><td>

Prompts for the name of a new folder and copies the selected files and folders into that folder.

*Example:* `Copy CREATEFOLDER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<folder name\>*</td><td>

Creates a new folder with the specified name and copies selected items into that folder. You can specify an absolute path, or just a name - if only a name is provided the folder is created in the destination (or source if the **HERE** argument is also specified). You can also use the [external control codes](../external_control_codes/README.md) to (for example) automatically create a folder based on the current date.

*Example:* `Copy CREATEFOLDER "Backup-{date|yyyyMMdd}"`

When archiving files, this specifies the name of the archive to create or update. (If you don't specify an archive name it will default to the name of the first selected file, without its extension, or the name of the current folder if no file selection is used.). The example below adds the selected files to an archive called "Cat Photos.zip" below the current folder:

*Example:* `Copy HERE ARCHIVE=.zip CREATEFOLDER="Cat Photos"`
</td></tr><tr><td>
DELEGATE</td><td>
/K</td><td>

**yes**</td><td>

Overrides the **copy_allow_delegation** setting on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences. Delegation to the very-high-level Windows file-copying API will be allowed, and custom file-copying code will only be used when required. (This is the normal behavior. Specifying **DELEGATE=yes** is redundant unless you have changed the default Preferences setting and want a particular command to revert back to normal.)
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Overrides the **copy_allow_delegation** setting the opposite way: Custom file-copying code will always be used, even when it is not required. (Not recommended outside of very special cases.)

*Example:* `Copy DELEGATE=no`
</td></tr><tr><td>
DUPLICATE</td><td>
/S</td><td>

*(no value)*</td><td>

Create duplicates of the selected items in the same folder. You will be prompted to enter new names (or a [wildcard pattern](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md)) for the duplicated files.

*Example:* `Copy DUPLICATE`
</td></tr><tr><td>
EXTRACT</td><td>
/O</td><td>

*(no value)*</td><td>

Extracts the contents of selected archives to the destination folder. You can also use this with folders to copy their contents without copying the folder itself.

*Example:* `Copy EXTRACT`
</td></tr><tr><td>
</td><td>
</td><td>

**sub**</td><td>

Creates a sub-folder in the destination named after the archive, and extracts the archive contents to that folder.

*Example:* `Copy EXTRACT=sub`
</td></tr><tr><td>
</td><td>
</td><td>

**checkout**</td><td>

Extracts the contents of an archive to a temporary folder and automatically opens that folder in a new Lister. You can use this to "check out" the files in an archive before you decide if and where you want to extract them to. Note that this command only works when you are inside the archive itself (e.g. double-click a .zip file to enter it, and then run the "checkout" command to extract it).

*Example:* `Copy EXTRACT=checkout`
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

Specifies the name of the file or files to copy. If you don't provide this argument the command operates on all selected items in the source Lister. This is the default argument for the **Copy** command - you don't need to specify the **FILE** keyword.

If you only specify the filename instead of the full path of the file or files, Opus will look in the current source folder. You can also specify a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Remember that if the filename contains spaces you need to enclose it in quotes.

*Example:* `Copy "C:\Data Directory\\.xls" TO /desktop`
</td></tr><tr><td>
FILTER</td><td>
/O</td><td>

*(no value)*</td><td>

Copies with filtering enabled (without having to activate the [copy filter](/Manual/file_operations/filtered_operations/README.md) in the Lister first). Opus will prompt you to define the filter.

*Example:* `Copy FILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter\>*</td><td>

Copies using the specified filter. This must have previously been created from the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences. You can also directly specify a [simple wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md)

*Example:* `Copy FILTER *.(jpg|png)`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

Copies with filtering enabled if the **Shift** key is held down. Opus will prompt you to define the filter.

*Example:* `Copy FILTER=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

Copies with filtering enabled if the **Alt** key is held down.

*Example:* `Copy FILTER=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

Copies with filtering enabled if the **Ctrl** key is held down.

*Example:* `Copy FILTER=ctrl`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to filter the contents of copied folders. This is similar to the **FILTER** argument, however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `Copy FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FLATVIEWCOPY</td><td>
/K</td><td>

**single**</td><td>

When copying items in different directories from a [flat view](/Manual/basic_concepts/flat_view.md) file display, the files will all be copied to the same target directory. This overrides the **When copying nested items** option on the **[Copying Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.md)** Preferences page.

*Example:* `Copy FLATVIEWCOPY=single`
</td></tr><tr><td>
</td><td>
</td><td>

**recreate**</td><td>

Recreates the source folder structure when copying items in different directories out of a [flat view](/Manual/basic_concepts/flat_view.md) file display.

*Example:* `Copy FLATVIEWCOPY=recreate`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

Opus will ask you what to do when copying items out of a flat view file display.

*Example:* `Copy FLATVIEWCOPY=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**autosingle**</td><td>

When used with **ask** or **recreate** this specifies what to do when the items being copied come from multiple folders. If the items being copied all come from the same folder, it will act as if **single** was specified instead.

*Example:* `Copy FLATVIEWCOPY=autosingle,recreate`
</td></tr><tr><td>
FORCE</td><td>
/S</td><td>

*(no value)*</td><td>

Automatically replace existing files without prompting. In-use files that cannot be replaced will be automatically scheduled for replacement next reboot.

*Example:* `Copy FORCE`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(no value)*</td><td>

Use the source folder as the destination folder (for example, archives can be extracted to the same folder instead of the destination).

*Example:* `Copy EXTRACT HERE`

**Important:** The **HERE** argument can complicate buttons which run more than one command, as it can affect the destination folder used by subsequent commands in the same button. It is recommended to use **TO={sourcepath\$}** instead if the button runs multiple commands.

**Scripting:** The **HERE** argument does not work when running commands via the scripting Command object. Instead, use *cmd.SetDestTab(cmd.sourcetab)* on the Command object, or use an explicit **TO** argument in the command string.
</td></tr><tr><td>
IGNOREEXT</td><td>
/S</td><td>

*(no value)*</td><td>

Makes the copy function ignore file extensions when copying with a wildcard rename (for example, so a button can work on both files and folders using the same wildcard pattern).

*Example:* `Copy * AS *.bak IGNOREEXT`
</td></tr><tr><td>
INCLUDEINLIBRARY</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a dynamically generated list of [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md) - you can include a selected folder in a library simply by selecting it from this list. Acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md). Most useful when used in a drop-down menu or on a [context menu](/Manual/file_types/filetype_editor/context_menu.md).

Opus will automatically navigate to show the contents of the library with the newly included folder.

*Example:* `Copy INCLUDEINLIBRARY`
</td></tr><tr><td>
</td><td>
</td><td>

**noread**</td><td>

Prevents Opus from automatically navigating to the library when you include a folder in it via the generated list.

*Example:* `Copy INCLUDEINLIBRARY noread`
</td></tr><tr><td>
</td><td>
</td><td>

**\$new**</td><td>

Include selected folders in a new library. The new library will be given the name of the first selected folder. Opus will automatically navigate to the new library unless you include the **noread:** prefix.

*Example:* `Copy INCLUDEINLIBRARY noread:\$new`
</td></tr><tr><td>
</td><td>
</td><td>

*\<library name\>*</td><td>

Include selected folders in the named library. Opus will automatically navigate to the new library unless you include the **noread:** prefix.

*Example:* `Copy INCLUDEINLIBRARY "noread:Movie Files"`
</td></tr><tr><td>
INSTALLFONT</td><td>
/O</td><td>

*(no value)*</td><td>

Installs new fonts in your system fonts folder. You do not need to specify the destination folder when using this command - the fonts will be copied to your fonts folder and registered automatically. This command has no effect if non-font files are selected. Fonts will be installed for all users (and so elevation will be required if UAC is enabled).

*Example:* `Copy INSTALLFONT`
</td></tr><tr><td>
</td><td>
</td><td>

**user**</td><td>

Installs the new fonts for the current user only. Does not require elevation under UAC.

*Example:* `Copy INSTALLFONT=user`
</td></tr><tr><td>
MAKELINK</td><td>
/O</td><td>

*(no value)*</td><td>

Creates shortcuts to all selected files and folders. Shortcuts do not require NTFS. Shortcuts may point to things on different drives to themselves.

*Example:* `Copy MAKELINK TO /desktop`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

Creates junctions to all selected folders. Junctions are only supported on NTFS drives. Junctions only work with folders (not with files). Junctions may point to folders on different drives to themselves.

*Example:* `Copy MAKELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

Creates hardlinks to all selected files. Hardlinks are only supported on NTFS drives. Hardlinks only work with files (not folders). Hardlinks *cannot* point to files on different drives to themselves.

*Example:* `Copy MAKELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

Creates softlinks to all selected files or folders, using absolute paths. Softlinks require Windows Vista or above and are only supported on NTFS drives. Softlinks work with both files and folders. Softlinks may point to things on different drives to themselves. Creating softlinks requires administrator access and will trigger a UAC prompt if necessary.

*Example:* `Copy MAKELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

Creates softlinks to any selected files or folders, using relative paths where possible. A regular absolute link will be created if the target can not be expressed relative to the link. (See **softlink** for more information on softlinks.)

*Example:* `Copy MAKELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

Automatically determines the most suitable type of link to create. On Vista and above, it will usually create softlinks (for both files and folders). On Windows XP, it will usually create junctions (for folders) and hardlinks (for files). Shortcuts will be created instead in cases where the desired link type is not applicable. For example, a shortcut will be created if the drives are not NTFS or if a hardlink is desired but the source and destination are on different drives.

*Example:* `Copy MAKELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

Does the same as **auto** except that it will not try to create softlinks. It will usually create junctions (for folders) and hardlinks (for files). Shortcuts will be created instead in cases where the desired link type is not applicable. For example, a shortcut will be created if the drives are not NTFS or for files where the source and destination are on different drives.

*Example:* `Copy MAKELINK=autonosoft`
</td></tr><tr><td>
MAKESFX</td><td>
/O</td><td>

*(no value)*</td><td>

Creates a [self-extracting Zip file](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.md) from selected files and folders. If you select a .zip file then it will be converted directly to self-extracting format; otherwise, the selected items will be zipped first.

*Example:* `Copy MAKESFX`
</td></tr><tr><td>
MARKDESTARCHIVE</td><td>
/K</td><td>

**yes**</td><td>

Clears the **A** ("ready for archiving") attribute on newly copied files. You can use this if your backup solution uses the **A** attribute to indicate a file has changes which need backing up, and you don't want the new copy to be backed up (until something modifies it and sets its **A** attribute again).

Overrides the \*\*Mark copied files as archived (clear the A flag) \*\*option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

This does nothing if not preserving file attributes on copied files.

*Example:* `Copy MARKDESTARCHIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not clear the **A** attribute on newly copied files.

*Example:* `Copy MARKDESTARCHIVE=no`
</td></tr><tr><td>
MARKSOURCEARCHIVE</td><td>
/K</td><td>

**yes**</td><td>

Clear the **A** ("ready for archiving") attribute on the original files after they have been copied. You can use this if your backup solution uses the **A** attribute to indicate a file has changes which need backing up, and you don't want the original files to be backed up.

Overrides the **Mark original files as archived after being copied (clear the A flag)** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

*Example:* `Copy MARKSOURCEARCHIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not clear the **A** attribute on the original files after they are copied.

*Example:* `Copy MARKSOURCEARCHIVE=no`
</td></tr><tr><td>
MOVE</td><td>
/S</td><td>

*(no value)*</td><td>

Move selected files and folders to the destination (a.k.a. cut-and-paste). If the destination folder is on the same drive as the source then generally items can be moved through a simple rename operation, which is very quick. When moving files between devices Opus first copies them to the destination, and then deletes them from the source.

*Example:* `Copy MOVE`
</td></tr><tr><td>
MOVEWHENSAME</td><td>
/S</td><td>

*(no value)*</td><td>

If the destination folder is on the same drive as the source then selected items will be moved, otherwise they will be copied. This command is used in the default [drag-and-drop file type event](/Manual/file_types/filetype_editor/events.md) (which mimics the standard Explorer drag-and-drop behaviour where files are moved if you drag them to a different folder on the same drive, and copied otherwise).

*Example:* `Copy MOVEWHENSAME`
</td></tr><tr><td>
MOVEWITHSHIFT</td><td>
/S</td><td>

*(no value)*</td><td>

Selected items will be moved if the **Shift** key is held down when the command is executed, otherwise they will be copied.

*Example:* `Copy MOVEWITHSHIFT`
</td></tr><tr><td>
NONBUFIO</td><td>
/K</td><td>

**yes**</td><td>

Changes when the copy operation uses non-buffered mode, where the filesystem buffers provided by Windows are bypassed.

For very large files, copying in non-buffered mode can increase the memory efficiency, copy speed and UI responsiveness. On the other hand, non-buffered mode may slow things down for smaller files or certain devices. In rare cases, non-buffered mode may not work at all (e.g. if you have a device which mis-reports its sector size).

Use of this argument overrides the default file size threshold for non-buffered copies set via the **copy_nonbufferio_threshold** [Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md) Preferences setting.

You can specify "yes" or "no" to force non-buffered mode on or off for all files, or specify the file size above which non-buffered mode should be used.

*Example:* `Copy NONBUFIO=yes`

This has no effect when doing simple file-to-file copies and delegating to the very-high-level Windows file-copy API, since that API performs its own buffering. See the **DELEGATE** argument for more detail.
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Forces the copy operation to be buffered, even if the file being copied exceeds the threshold size set via the **copy_nonbuffer_threshold** [Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md) Preferences setting.

*Example:* `Copy NONBUFIO=no`
</td></tr><tr><td>
</td><td>
</td><td>

*\<threshold size\>*</td><td>

The copy operation will be non-buffered if the file size exceeds the specified size, and buffered otherwise. When specifying a size, units can be KB, MB or GB. If no units are specified, MB is used by default.

*Example:* `Copy NONBUFIO=64MB`
</td></tr><tr><td>
NOQUEUEWHENSAME</td><td>
/S</td><td>

*(no value)*</td><td>

Disables the use of the copy queue when the source and destination paths are on the same drive partition. You would normally only use this argument when moving files, because moves on the same drive can be done without actually copying any data.

*Example:* `Copy MOVE NOQUEUEWHENSAME`
</td></tr><tr><td>
PATTERN</td><td>
/K</td><td>

*\<old name pattern\>*</td><td>

Specifies the "old name" or "from" [wildcard pattern](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.md) for the copied or moved files. Use this in conjunction with **AS** to control wildcard renaming of copied or moved files.

*Example:* `Copy DUPLICATE PATTERN * * AS *_{date|yyyy-MM-dd}.`\*
</td></tr><tr><td>
QUEUE</td><td>
/O</td><td>

*(no value)*</td><td>

Enables automatic [copy queuing](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.md). File copies will be queued automatically if required (based on the source and destination drives). This can override the **Automatically manage file copy queues** option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** Preferences page.

*Example:* `Copy QUEUE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<queue name\>*</td><td>

When you specify a queue name as the value for this argument, it enables manual copy queuing when copying files. That is, with a name specified, file copies will always be queued to the specified queue - if no name is specified for the argument, copies will only be queued if needed. The specified name will be shown in the progress dialog's title bar.

*Example:* `Copy QUEUE=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Used to disable copy queuing - whether enabled in Preferences, or otherwise enabled by the **shift** keyword.

*Example:* `Copy QUEUE=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

Lets you specify two alternate parameters for the **QUEUE** argument. The value specified before the **shift** keyword is used if the **Shift** key is not held down - the value after it is used if it is. For example, you could configure a copy button to queue files to a specific queue if the **Shift** key were held down, and to disable queuing otherwise.

*Example:* `Copy QUEUE=none,shift,MyQueue TO \\NAS1\Storage`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Specify the **quiet** keyword to suppress the prompt that normally indicates a copy operation has been queued.

*Example:* `Copy QUEUE=MyQueue,quiet`
</td></tr><tr><td>
RENAMEWHENSAME</td><td>
/S</td><td>

*(no value)*</td><td>

If the source and destination are the same folder, the newly copied file will be automatically renamed to avoid a clash.

*Example:* `Copy RENAMEWHENSAME`
</td></tr><tr><td>
SENDMAIL</td><td>
/O</td><td>

*(no value)*</td><td>

Send selected files as email attachments. Email settings must be configured on the **[Internet / Email](/Manual/preferences/preferences_categories/internet/email.md)** Preferences page.

*Example:* `Copy SENDMAIL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<email address\>*</td><td>

Send selected files to the specified email recipient. This only works if email sending is set to use the **MAPI client** on the **[Internet / Email](/Manual/preferences/preferences_categories/internet/email.md)** Preferences page.

*Example:* `Copy SENDMAIL=f.bloggs@company.com`
</td></tr><tr><td>
SENDTO</td><td>
/K</td><td>

*\<send-to target\>*</td><td>

Send selected files to the specified "send to" target. This can be any item that appears in the system *Send To* context menu, and lets you perform the same action without actually displaying the context menu. The value given for the target must be the name of the actual file in the *SendTo* folder (to find the *SendTo* folder and see what's in there, use the **/sendto** [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md)).

*Example:* `Copy SENDTO "Web Publishing Wizard"`
</td></tr><tr><td>
SYNC</td><td>
/S</td><td>

*(no value)*</td><td>

Performs the copy stage of a [synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) operation. You must first have used the **[Find](find.md) SYNC** command to perform the comparison stage.

//<Example://> See the `Find SYNC` [command](find.md#SYNC) for an example
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<target path\>*</td><td>

Specify the target path for the command. By default Copy functions that require a destination folder will use the current destination file display or Lister - this argument allows you to override that. Also see the HERE argument for a way to override the destination path. You can use [folder aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md)and [@ftp shortcuts](/Manual/ftp/ftp_paths.md), URL-style paths for [virtual filesystems](/Manual/basic_concepts/virtual_file_system/README.md) ([collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), [libraries](/Manual/basic_concepts/virtual_file_system/libraries.md), etc.) as well as standard file system paths. Remember that if the specified path contains a space you must enclose the whole path in quotes. This only sets the destination folder; if you want to change the names of the copied files as well, use the **AS** argument.

Note that specifying the target path in this way disables automatic [copy queues](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.md). You can use the **QUEUE** argument to place these operations in a queue.

*Example:* `Copy TO "lib://Backups/Daily Backup Folder"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

Normally if no destination path is specified, and there is no current destination file display or Lister, Opus will prompt for a destination path via a popup dialog. You can use the **ask** value to force Opus to always prompt for a destination path, even if there already is one.

You can also specify a default destination path, by appending a colon and the path. Remember to use quotes if the path contains spaces.

*Example:* `Copy TO=ask`  
*Example:* `Copy TO="ask:c:\My Documents"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask\$**</td><td>

Force Opus to ask for a destination path. If you have a function that combines multiple **Copy** commands, you can use **ask\$** to make Opus only prompt for a destination path once for the whole function, rather than prompting separately for each **Copy** command.

You can also specify a default destination path, by appending a colon and the path.

*Example:* `Copy TO=ask\$`  
\`\`Copy TO=ask\$:D:\\\`
</td></tr><tr><td>
UNATTENDED</td><td>
/K</td><td>

**yes**</td><td>

Enables [unattended copy](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/unattended_operation.md) mode. In this mode, Opus will not display any confirmation prompts or error dialogs - the copy will proceed until the end, and any errors will be summarised upon completion. Use the other arguments like **WHENEXISTS** to control what happens in certain situations.

*Example:* `Copy UNATTENDED=yes TO=@myftpsite WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Disables unattended copy mode.

*Example:* `Copy UNATTENDED=no`
</td></tr><tr><td>
UPDATEALL</td><td>
/S</td><td>

*(no value)*</td><td>

Update files in the destination folder ([a simple form of one-way synchronization](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.md)). Only files that either do not exist in the destination, or do exist but are different from the source files, will be copied - other files will be skipped.

(Compare this with **UPDATEEXISTING** which only updates files that already exist.)

A file is defined as different if either its timestamp is newer or its size has changed - the contents of the file are not compared.

*Example:* `Copy UPDATEALL FORCE`
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

Update existing files whose timestamp is different (ignore file size).

*Example:* `Copy UPDATEALL=date`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

Update existing files whose size is different (ignore timestamp).

*Example:* `Copy UPDATEALL=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

When used with **size**, only updates files whose size is smaller (rather than just different).

*Example:* `Copy UPDATEALL=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

When used with **size**, only updates files whose size is larger..

*Example:* `Copy UPDATEALL=size,larger`
</td></tr><tr><td>
UPDATEEXISTING</td><td>
/O</td><td>

*(no value)*</td><td>

Update existing files in the destination folder ([a simple form of one-way synchronization](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.md)). Only files that already exist in the destination, but are different from the source files, will be copied. Files that do not already exist, as well as files that have not changed, will be skipped.

(Compare this with **UPDATEALL** which also copies files that don't already exist.)

A file is defined as different if either its timestamp is newer or its size has changed.

*Example:* `Copy UPDATEEXISTING`
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

Update existing files whose timestamp is different (ignore file size).

*Example:* `Copy UPDATEEXISTING=date`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

Update existing files whose size is different (ignore timestamp).

*Example:* `Copy UPDATEEXISTING=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

When used with **size**, only updates files whose size is smaller (rather than just different).

*Example:* `Copy UPDATEEXISTING=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

When used with **size**, only updates files whose size is larger..

*Example:* `Copy UPDATEEXISTING=size,larger`
</td></tr><tr><td>
UPDATESECURITY</td><td>
/K</td><td>

**yes**</td><td>

Update security permissions and encryption settings for moved\* files to match their destination folders.

Overrides the **Update permissions/encryption to match the destination when moving files** option on the **[Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md)** Preferences page.

For example, if a folder has the **E** attribute set, files moved into that folder will be automatically encrypted.

This only applies to files moved between folders on the same logical drive. For files that are moved between drives, the operation is done via a copy-then-delete and the newly copied files will usually inherit the permissions of the destination folder by default (unless overridden by the separate **COPYSECURITY** argument or related Preferences setting).

*Example:* `Copy UPDATESECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Do not update security permissions or encryption settings for files moved between folders on the same logical drive. Such files will instead retain the permissions they had in their original folders.

*Example:* `Copy UPDATESECURITY=no`
</td></tr><tr><td>
UPDATETOLERANCE</td><td>
/K/N</td><td>

*\<tolerance seconds\>*</td><td>

Sets the maximum number of seconds an existing file's timestamp can vary before it will be considered "different" by the **UPDATEALL** or **UPDATEEXISTING** functions. The default is two seconds (that is, a file will be considered different if its timestamp is two or more seconds different to the source file). You can use this to make allowances for daylight-savings time, or for file systems that don't preserve file dates to a high enough resolution.

*Example:* `Copy UPDATEEXISTING UPDATETOLERANCE=3600`
</td></tr><tr><td>
WHENEXISTS</td><td>
/K</td><td>

**ask**</td><td>

If a file that is being copied already exists in the destination, ask what to do. This overrides the option **Ask for confirmation before overwriting existing files** on the **[Copying Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.md)** page in Preferences.

*Example:* `Copy WHENEXISTS=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**skip**</td><td>

If a file that is being copied already exists in the destination, skip over it (leaving existing file intact).

*Example:* `Copy WHENEXISTS=skip`
</td></tr><tr><td>
</td><td>
</td><td>

**recycle**</td><td>

When replacing a file, delete the original to the recycle bin if possible. You can combine this flag with the other options.

Note that **Undo** can not be used to restore these files automatically, however you will be able to retrieve them from the recycle bin manually.

*Example:* `Copy WHENEXISTS=replace,recycle`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

Replace any existing files without prompting.

*Example:* `Copy WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**rename**</td><td>

If a file with the same name already exists in the destination, the newly copied file will be renamed automatically to avoid a clash.

*Example:* `Copy WHENEXISTS=rename`
</td></tr><tr><td>
</td><td>
</td><td>

**renameold**</td><td>

The old file (the one that already exists in the destination directory) will be renamed before the new file is copied.

*Example:* `Copy WHENEXISTS=renameold`
</td></tr><tr><td>
</td><td>
</td><td>

**resume**</td><td>

When copying to FTP sites, a previous incomplete file transfer will be automatically resumed (only applies if the server supports FTP, and the existing file is smaller than the one being copied).

*Example:* `Copy WHENEXISTS=resume`
</td></tr><tr><td>
</td><td>
</td><td>

**merge**</td><td>

Automatically merge the contents of an existing folder with that of the folder being copied. This overrides the **Ask for confirmation before merging existing folders** option on the **[Copying Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.md)** page in Preferences. You can use this value in addition to another value to specify the 'when exists' behaviour for files as well as folders.

*Example:* `Copy WHENEXISTS=replace,merge`
</td></tr><tr><td>
</td><td>
</td><td>

**keepnewer**</td><td>

Replace any existing files if the files being copied are newer. If the timestamps are the same or older, the already-existing files will be skipped.

*Example:* `Copy WHENEXISTS=keepnewer`
</td></tr></tbody>
</table>

