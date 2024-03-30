# Prefs

The **Prefs** internal command can be used to:

- Display the [Preferences](/Manual/preferences/README.md) dialog which lets you change most configuration options
- Display the [Customize](/Manual/customize/README.md) dialog to edit toolbars, menus and hotkeys
- Display the [File Types](/Manual/file_types/README.md) dialog to configure context menus, double-click actions and other file-type specific settings
- Display and edit the [FTP Address Book](/Manual/ftp/ftp_address_book/README.md)
- [Backup and restore](/Manual/preferences/backing_up_and_restoring_preferences.md) your configuration
- Load and save [Lister layouts](/Manual/basic_concepts/the_lister/layouts/README.md)
- Update the [Default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md) settings
- Load and save [Lister styles](/Manual/basic_concepts/the_lister/styles.md)
- Load and save [Lister themes](/Manual/basic_concepts/the_lister/themes/README.md)
- Manage [VFS plugins](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.md)
- Install, manage and edit [Script Add-ins](/Manual/scripting/script_add-ins/README.md).

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Displays the **[Preferences](/Manual/preferences/README.md)** dialog.

*Example:* `Prefs`
</td></tr><tr><td>
ADDFTPSITE</td><td>
/S</td><td>

*(no value)*</td><td>

Adds the currently connected FTP site as a new entry in the [FTP Address Book](/Manual/ftp/ftp_address_book/README.md). If you are not currently viewing an FTP directory this command has no effect.

*Example:* `Prefs ADDFTPSITE`
</td></tr><tr><td>
BACKUP</td><td>
/O</td><td>

*(no value)*</td><td>

Automates the configuration backup process. By default all your configuration settings, toolbars, menus and hotkeys are included in the backup, but extra data like images and sounds are not. The optional values for this argument can be used to control which extra data is included in the backup. Use the **TO** argument to specify the name of the backup file, and the **PASSWORD**, **DESC** and **QUIET** arguments provide additional control.

*Example:* `Prefs BACKUP TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**images**</td><td>

When automating a configuration backup, includes image files in your backup (corresponds to the **Backup images** option in the *[Backup and Restore Configuration](/Manual/preferences/backing_up_and_restoring_preferences.md)* wizard).

*Example:* `Prefs BACKUP=images TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**sounds**</td><td>

Includes sound files in the backup (corresponds to the **Backup sounds** option).

*Example:* `Prefs BACKUP=sounds TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**data**</td><td>

Include miscellaneous data in the backup (corresponds to the **Backup miscellaneous data** option).

*Example:* `Prefs BACKUP=data TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**localstate**</td><td>

Include local state data (corresponds to the **Backup local state data** option).

*Example:* `Prefs BACKUP=data,localstate TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Backup everything (equivalent to **BACKUP=images,sounds,data,localstate**).

*Example:* `Prefs BACKUP=all TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**notabs**</td><td>

(Opus 13.3.1 and above.) Exclude currently open windows and tabs from the backup. (Only relevant if local state is being backed up.)

*Example:* `Prefs BACKUP=all,notabs TO="/desktop/PrefsBackup"`
</td></tr><tr><td>
BACKUPRESTORE</td><td>
/S</td><td>

*(no value)*</td><td>

Initiates the *[Backup and Restore Configuration](/Manual/preferences/backing_up_and_restoring_preferences.md)* wizard, which lets you backup and restore your configuration, as well as export Opus to a USB drive. You can use the **TO** argument to override the default backup name, and the **PASSWORD** or **DESC** arguments to pre-supply a default password or descriptions when creating a backup.

*Example:* `Prefs BACKUPRESTORE`  
*Example:* `Prefs BACKUPRESTORE TO="/desktop\Backup for %username% on {date\|yyyy-MM-dd}" PASSWORD="cat" DESC="Quick Backup."`

If you wish to automate the backup or restore process, without showing the interactive wizard, use the separate **BACKUP** or **RESTORE** arguments.
</td></tr><tr><td>
COLLAPSEALL</td><td>
/S</td><td>

*(no value)*</td><td>

Collapses all categories in the **[Preferences](/Manual/preferences/README.md)** dialog. Combine with the `PAGE` argument to show a new page and collapse all other categories.

*Example:* `Prefs PAGE=folderformats COLLAPSEALL`
</td></tr><tr><td>
CUSTOMIZE</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **[Customize](/Manual/customize/README.md)** dialog. The dialog will open on the page that was last used.

*Example:* `Prefs CUSTOMIZE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<page\>*</td><td>

Displays the specified tab on the **Customize** dialog. Allowable values for this argument are **commands**, **toolbars**, **keys** and **menus**.

*Example:* `Prefs CUSTOMIZE=toolbars`
</td></tr><tr><td>
DESC</td><td>
/K</td><td>

*\<description\>*</td><td>

Assign a description to a configuration backup (used with the **BACKUP** or **BACKUPRESTORE** argument). Remember that if the description string contains spaces you need to enclose it with quotes.

*Example:* `Prefs BACKUP TO="/desktop/PrefsBackup" DESC="My Opus Config"`
</td></tr><tr><td>
FILETYPES</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **[File Types](/Manual/file_types/README.md)** dialog.

*Example:* `Prefs FILETYPES`
</td></tr><tr><td>
FROM</td><td>
/K</td><td>

*\<backup file\>*</td><td>

Specifies the configuration backup file to restore (used with the **RESTORE** argument to automate the configuration restore process).

*Example:* `Prefs RESTORE FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
FTPSITES</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the **[FTP Address Book](/Manual/ftp/ftp_address_book/README.md)**.

*Example:* `Prefs FTPSITES`
</td></tr><tr><td>
</td><td>
</td><td>

*\<site name\>*</td><td>

Displays the **[FTP Address Book](/Manual/ftp/ftp_address_book/README.md)** and automatically selects the named site. If the site is in a sub-folder in the address book you need to provide the full path of the site.

*Example:* `Prefs FTPSITES="WorkServers\Production"`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Prefs LAYOUTLIST HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Prefs STYLELIST HEADING="Styles"`
</td></tr><tr><td>
KEYS</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **Keys** page of the **Customize** dialog (equivalent to `Prefs CUSTOMIZE=keys`).

*Example:* `Prefs KEYS`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

*\<layout name\>*</td><td>

Loads the named [Lister layout](/Manual/basic_concepts/the_lister/layouts/README.md).

*Example:* `Prefs LAYOUT="Music Albums"`
</td></tr><tr><td>
LAYOUTCLOSELISTERS</td><td>
/K</td><td>

**yes**</td><td>

When loading a layout with the **LAYOUT** argument, this overrides the **Close all existing Listers when loading this layout** flag set for the layout, and forces all existing Listers to close. When saving a layout with the **LAYOUTSAVE** argument, it sets the state of that flag within the layout.

*Example:* `Prefs LAYOUT="FTP Sync" LAYOUTCLOSELISTERS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not close all existing Listers when loading a layout.

*Example:* `Prefs LAYOUT="Photo Album" LAYOUTCLOSELISTERS=no`
</td></tr><tr><td>
</td><td>
</td><td>

**current**</td><td>

Only closes Listers on the current virtual desktop.

*Example:* `Prefs LAYOUT="Work" LAYOUTCLOSELISTERS=yes,current`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Closes Listers on all desktops.

*Example:* `Prefs LAYOUT="Photo Organising" LAYOUTCLOSELISTERS=yes,all`
</td></tr><tr><td>
LAYOUTEDIT</td><td>
/S</td><td>

*(no value)*</td><td>

Opens the Preferences dialog and displays the **[Layouts and Styles / Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md)** page (equivalent to `Prefs PAGE=layouts`).

*Example:* `Prefs LAYOUTEDIT`
</td></tr><tr><td>
LAYOUTIGNOREFORMATS</td><td>
/K</td><td>

**yes**</td><td>

When loading a layout with the **LAYOUT** argument, this overrides the **Ignore folder formats saved within this layout** flag set for the layout, and forces the layout's [folder formats](/Manual/basic_concepts/folder_options/folder_formats.md) to be ignored. When saving a layout with the **LAYOUTSAVE** argument, it sets the state of that flag within the layout.

*Example:* `Prefs LAYOUT="Photo Viewing" LAYOUTIGNOREFORMATS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not ignore the layout's folder formats.

*Example:* `Prefs LAYOUT="Photos" LAYOUTIGNOREFORMATS=no`
</td></tr><tr><td>
LAYOUTIGNORETOOLBARS</td><td>
/K</td><td>

**yes**</td><td>

When loading a layout with the **LAYOUT** argument, this overrides the **Ignore toolbars saved within this layout** flag set for the layout, and forces the layout's toolbars to be ignored, and the default toolbar set to be used instead. When saving a layout with the **LAYOUTSAVE** argument, it sets the state of that flag within the layout.

*Example:* `Prefs LAYOUT="Photos" LAYOUTIGNORETOOLBARS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not ignore the layout's toolbars.

*Example:* `Prefs LAYOUT="Photos" LAYOUTIGNORETOOLBARS=no`
</td></tr><tr><td>
LAYOUTLIST</td><td>
/S</td><td>

*(no value)*</td><td>

Displays a list of your saved [Lister layouts](/Manual/basic_concepts/the_lister/layouts/README.md) (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting an item from the generated list loads the specified layout. The **LAYOUTCLOSELISTERS**, **LAYOUTIGNOREFORMATS** and **LAYOUTMOUSERELATIVE** flags can be used in conjunction with this argument to control the behaviour of the generated buttons.

*Example:* `Prefs LAYOUTLIST LAYOUTCLOSELISTERS=yes`
</td></tr><tr><td>
LAYOUTMOUSERELATIVE</td><td>
/K</td><td>

**yes**</td><td>

When loading a layout with the **LAYOUT** argument, this overrides the **Open layout relative to the monitor the mouse is currently on** flag set for the layout, and forces the layout's position to be relative to the mouse. When saving a layout with the **LAYOUTSAVE** argument, it sets the state of that flag within the layout.

*Example:* `Prefs LAYOUT="Find" LAYOUTMOUSERELATIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Does not open the layout relative to the mouse pointer.

*Example:* `Prefs LAYOUT="BackupFiles" LAYOUTMOUSERELATIVE=no`
</td></tr><tr><td>
LAYOUTNAME</td><td>
/K</td><td>

*\<layout name\>*</td><td>

Specifies a name when saving a [layout](/Manual/basic_concepts/the_lister/layouts/README.md) using the **LAYOUTSAVE** argument. If not provided Opus will prompt for a name for the new layout.

*Example:* `Prefs LAYOUTNAME="My Layout" LAYOUTSAVE`
</td></tr><tr><td>
LAYOUTNOVIRTDESKTOP</td><td>
/K</td><td>

**yes**</td><td>

When loading a layout, prevents Listers being restored to their original virtual desktops (overrides the setting in the Layout).

*Example:* `Prefs LAYOUT="Find" LAYOUTNOVIRTDESKTOP=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Allows Listers to be restored to their original virtual desktops.

*Example:* `Prefs LAYOUT="Find" LAYOUTNOVIRTDESKTOP=no`
</td></tr><tr><td>
LAYOUTSAVE</td><td>
/O</td><td>

*(no value)*</td><td>

Saves the currently open Listers as a [layout](/Manual/basic_concepts/the_lister/layouts/README.md). You can use the **LAYOUTNAME** argument to specify the layout name. You can also use the **LAYOUTCLOSELISTERS**, **LAYOUTIGNOREFORMATS** and **LAYOUTMOUSERELATIVE** arguments to control the state of those flags for the saved layout.

*Example:* `Prefs LAYOUTSAVE`
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

Saves only the active Lister as a layout. Any other currently open Listers are not included.

*Example:* `Prefs LAYOUTSAVE=single LAYOUTNAME="CurrentLister"`
</td></tr><tr><td>
</td><td>
</td><td>

**noupdatesettings**</td><td>

If you do not use the **LAYOUTNAME** argument to provide a name for the layout, Opus will display a dialog prompting for the name - this dialog also contains various options for the layout (ignore formats, mouse relative, etc). Changes you make to those options will be saved as the default settings for the **LAYOUTSAVE** function unless you specify the **noupdatesettings** value.

*Example:* `Prefs LAYOUTSAVE=noupdatesettings LAYOUTMOUSERELATIVE=yes LAYOUTNAME="My Layout"`
</td></tr><tr><td>
</td><td>
</td><td>

**updatecurrent**</td><td>

If the current lister is already part of a layout, that layout will be updated and you will not be prompted for a layout name or any further options.

*Example:* `Prefs LAYOUTSAVE=updatecurrent`
</td></tr><tr><td>
LAYOUTTHISLISTER</td><td>
/O</td><td>

*(no value)*</td><td>

In conjunction with the **LAYOUT** argument, this applies the settings from the specified layout to the current Lister instead of opening a new Lister.

If no value is given to the **LAYOUTTHISLISTER** argument, the layout's panels (e.g. viewer pane, dual file display, utility panel) are applied to the current lister but the window size and position, and current paths, are left unchanged.

*Example:* `Prefs LAYOUT="PhotoViewing" LAYOUTTHISLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**nopanels**</td><td>

Do not apply the layout's panels (e.g. viewer pane, dual file display, utility panel) to the currernt window. (If none of the other values are specified, then nothing will be done at all.)

*Example:* `Prefs LAYOUT="SmallLister" LAYOUTTHISLISTER=nopanels,size`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

Use the window size from the specified layout.

*Example:* `Prefs LAYOUT="SmallLister" LAYOUTTHISLISTER=size`
</td></tr><tr><td>
</td><td>
</td><td>

**pos**</td><td>

Use the window position from the specified layout.

*Example:* `Prefs LAYOUT="NiceSizedLister" LAYOUTTHISLISTER=pos,size`
</td></tr><tr><td>
</td><td>
</td><td>

**paths**</td><td>

Use the paths/tabs (and folder formats) from the specified layout.

*Example:* `Prefs LAYOUT="CurrentWork" LAYOUTTHISLISTER=pos,size,paths`

You can also use **LAYOUTIGNOREFORMATS** in conjunction with **LAYOUTTHISLISTER=paths** to override whether or not the layout's folder formats are applied (which is normally determined by a flag you can set when saving and editing each layout).

*Example:* `Prefs LAYOUT="My Layout" LAYOUTTHISLISTER=paths LAYOUTIGNOREFORMATS=yes`
</td></tr><tr><td>
LIMITPATH</td><td>
/K/M</td><td>

*\<paths\>*</td><td>

When opening a new Layout with the **LAYOUT** argument, this lets you restrict the newly opened Listers to one or more paths (and their descendants). Attempts to navigate outside of the allowed paths will display an error.

*Example:* `Prefs LAYOUT="Focus On Work" LIMITPATH "C:\Work"`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

If a Layout was saved with restricted paths, this lets you override the restrictions when opening the Layout.

*Example:* `Prefs LAYOUT="LockedLister" LIMITPATH=reset`
</td></tr><tr><td>
MENUMARKERS</td><td>
/S</td><td>

*(no value)*</td><td>

When used with **LAYOUTLIST**, if the generated list of layouts includes any submenus, the top-level buttons will display a glyph indicating a dropdown menu.

*Example:* `Prefs LAYOUTLIST MENUMARKERS`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(no value)*</td><td>

Allows a [script](/Manual/scripting/README.md) to run the `Prefs LAYOUT` command without triggering other scripts (or itself). Adding the **NOSCRIPT** argument disables the **[OnBeforeFolderChange](../../scripting_reference/scripting_events/onbeforefolderchange.md)**, **[OnAfterFolderChange](../../scripting_reference/scripting_events/onafterfolderchange.md)**, **[OnOpenTab](../../scripting_reference/scripting_events/onopentab.md)** and **[OnOpenLister](../../scripting_reference/scripting_events/onopenlister.md)** events that would otherwise be triggered by opening a Lister layout.

*Example:* `Prefs LAYOUT="My Layout" NOSCRIPT`
</td></tr><tr><td>
PAGE</td><td>
/K</td><td>

*\<prefs page\>*</td><td>

Opens the Preferences dialog to the specified page. If this argument is not supplied the Preferences dialog will open to the last-used page.

Opus can work out the command for you if you open the Preferences dialog, go to the page you want, then select **File / Copy Page Shortcut To Clipboard** at the top of the window.

Some pages allow data to be passed to them to indicate the item to edit. For example, **scripts** allows a script to be selected by name and its configuration dialog to be shown automatically. To do this, append a colon and the appropriate data to the page name.

*Example:* `Prefs PAGE=transitionanimations`  
*Example:* `Prefs PAGE=scripts:dopstack.js`
</td></tr><tr><td>
PASSWORD</td><td>
/K</td><td>

*\<password\>*</td><td>

Encrypt a configuration backup (used with the **BACKUP** or **BACKUPRESTORE** argument). You will need to enter the password when you restore the backup.

*Example:* `Prefs BACKUP TO="/desktop/PrefsBackup" PASSWORD="abc123"`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(no value)*</td><td>

Prevents the **Backup and Restore Configuration** wizard from appearing when the backup or restore are automated (when used with the **BACKUP** and **RESTORE** arguments). If specified when restoring a configuration, Opus will be restarted automatically - you can use the **Close AUTOLISTER** command to control whether a new Lister is opened when Opus restarts this way.

*Example:* `Prefs RESTORE FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
RESTORE</td><td>
/O</td><td>

*(no value)*</td><td>

Automates the configuration restore process. By default all the configuration settings, toolbars, menus and hotkeys from the backup will be restored, but extra data like images and sounds are not. The optional values for this argument can be used to control which extra data is included in the restore. Use the **FROM** argument to specify the name of the backup file. If the backup file was encrypted you can provide the password with the **PASSWORD** argument. The **QUIET** argument prevents any user interface from being displayed, and Opus will automatically restart when the restore is complete.

*Example:* `Prefs RESTORE FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**images**</td><td>

Restores images from the configuration backup (corresponds to the **Restore images** option in the *[Backup and Restore Configuration](/Manual/preferences/backing_up_and_restoring_preferences.md)* wizard).

*Example:* `Prefs RESTORE=images FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**sounds**</td><td>

Restores sounds from the configuration backup (corresponds to the **Restore sounds** option in the wizard).

*Example:* `Prefs RESTORE=images,sounds FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**data**</td><td>

Restores miscellaneous data (corresponds to the **Restore miscellaneous data** option in the wizard).

*Example:* `Prefs RESTORE=data FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**localstate**</td><td>

Restores local state data (corresponds to the **Restore local state data (window positions, etc)** option in the wizard).

*Example:* `Prefs RESTORE=data,localstate FROM="/desktop/PrefsBackup" QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

Replaces your existing configuration completely (corresponds to the similarly named option in the wizard). If you select this, your existing configuration is deleted before the restore is done. Without this option, the restored configuration files are written over the top of your existing configuration - but the effect of this is to merge things like toolbars and images with different names.

*Example:* `Prefs RESTORE=replace,images,sounds FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Restores all items in the configuration backup (the equivalent of **RESTORE=images,sounds,data,localstate**).

*Example:* `Prefs RESTORE=replace,all FROM="/desktop/PrefsBackup"`
</td></tr><tr><td>
SCRIPTDISABLE</td><td>
/O</td><td>

*(no value)*</td><td>

If no script name is given, the command toggles the global option to disable all script add-ins. This will disable any event scripts, command scripts and column scripts you have installed. This is typically used to test if problems are due to scripts or something else.

The global option does not affect the enabled/disabled state of any individual script. In other words, if a script is disabled and you then disable scripting globally, then enable scripting globally again, the script will still be disabled. The other difference between the global setting and individually disabling all scripts is that the global setting will also affect scripts which are installed after the change.

*Example:* `Prefs SCRIPTDISABLE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<script name\>*</td><td>

Enable or disable the specified script or scripts. The script name should match the filename(s) of the script add-in(s) you wish to affect.

If the global option to disable all script add-ins is in effect, no individual script can be enabled.

The script name can use simple \* wildcards to match multiple filenames. While this can be used to enable or disable multiple scripts at once, it is intended to avoid worrying about whether a script is installed with ".js" and ".vbs" or ".js.txt" and ".vbs.txt" style extensions.

(As a special case, if the script name wildcard is literally "\*" or "\*.\*", the command acts the same as if no script name was specified, and toggles the global option to disable all script add-ins.)

If the script name is the only parameter, the script will be toggled (enabled if currently disabled; disabled if currently enabled). If multiple scripts match the pattern, they will all be set to the same state as the first match, and not toggled individually.

*Example:* `Prefs SCRIPTDISABLE="My Script.js\*"`

If a script is inside a Script Package (.osp file), the package must be included in the name:

*Example:* `Prefs SCRIPTDISABLE="My Package.osp\My Script.vbs"`

Wildcards can make dealing with script packages easier, and can also handle script packages which contain multiple scripts, or where you distribute a script to people as a .osp but work on it privately as a text file:

*Example:* `Prefs SCRIPTDISABLE="My Package.osp\*"`  
*Example:* `Prefs SCRIPTDISABLE="\*My Script.vbs\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**enable**</td><td>

Enable the specified script(s), or all scripts if no script name is specified.

*Example:* `Prefs SCRIPTDISABLE="My Script.js\*,enable"`  
*Example:* `Prefs SCRIPTDISABLE=enable`
</td></tr><tr><td>
</td><td>
</td><td>

**disable**</td><td>

Disable the specified script(s), or all scripts if no script name is specified.

*Example:* `Prefs SCRIPTDISABLE="My Script.js\*,disable"`  
*Example:* `Prefs SCRIPTDISABLE=disable`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggle the specified script(s), or all scripts if no script name is specified.

(This is the default, if neither "enable" nor "disable" is specified, but you can include it if you wish to be more explicit.)

*Example:* `Prefs SCRIPTDISABLE="My Script.js\*,toggle"`  
*Example:* `Prefs SCRIPTDISABLE=toggle`

Note that when a **SCRIPTDISABLE** button is a toggle, the button will appear active (e.g. checked or highlighted) when scripts are *disabled*. As with most commands, you can add **@toggle:invert** on a new line at the top of the command sequence to reverse this.

//<Example://>

    @toggle:invert
    Prefs SCRIPTDISABLE="Viewer Select.js,toggle"
</td></tr><tr><td>
SCRIPTEDIT</td><td>
/K</td><td>

*\<script name\>*</td><td>

Launches the [Script Editor](/Manual/scripting/script_editor/README.md) for the specified script. If you're working on a specific script this lets you edit it quickly without having to go via the [Script Management](/Manual/scripting/script_management/README.md) interface.

The script name can use simple \* wildcards to avoid worrying about whether a script is installed with ".js" and ".vbs" or ".js.txt" and ".vbs.txt" style extensions.

*Example:* `Prefs SCRIPTEDIT="My Script.js\*"`

If a script is inside a Script Package (.osp file), the package must be included in the name:

*Example:* `Prefs SCRIPTEDIT="My Package.osp\My Script.vbs"`
</td></tr><tr><td>
SCRIPTINSTALL</td><td>
/O</td><td>

*(no value)*</td><td>

Launches the [installer](/Manual/scripting/script_management/installer.md) to install the currently selected script file.

*Example:* `Prefs SCRIPTINSTALL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<file path\>*</td><td>

Launches the Script Installer to install the specified script file.

*Example:* `Prefs SCRIPTINSTALL /downloads/CoolScript.osp`
</td></tr><tr><td>
SCRIPTS</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the [Script Management](/Manual/scripting/script_management/README.md) dialog - the centralised hub for creating, editing, managing and sharing script add-ins.

*Example:* `Prefs SCRIPTS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<script name\>*</td><td>

Displays the Script Management dialog, selects the specified script in the list, and (if the script has configuration items) displays its configuration dialog. The script name should match the filename of the script add-in you wish to edit the configuration of.

The script name can use simple \* wildcards to avoid worrying about whether a script is installed with ".js" and ".vbs" or ".js.txt" and ".vbs.txt" style extensions.

*Example:* `Prefs SCRIPTS="My Script.js\*"`

If a script is inside a Script Package (.osp file), the package must be included in the name:

*Example:* `Prefs SCRIPTS="My Package.osp\My Script.vbs"`

Wildcards can make dealing with script packages easier, and can also handle script packages which contain multiple scripts, or where you distribute a script to people as a .osp but work on it privately as a text file:

*Example:* `Prefs SCRIPTS="My Package.osp\*"`  
*Example:* `Prefs SCRIPTS="\*My Script.vbs\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**!scriptlist**</td><td>

Generates a list of all script add-ins (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)).

Selecting an item from the generated list will display the Script Management dialog with that item selected (and displays its configuration dialog, if it has one).

*Example:* `Prefs SCRIPTS=!scriptlist`
</td></tr><tr><td>
SETLISTERDEFAULTS</td><td>
/O</td><td>

*(no value)*</td><td>

Lets you select a Lister to save as the [Default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md), or to set other default parameters.

*Example:* `Prefs SETLISTERDEFAULTS`
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

Suppress the confirmation and success prompts when setting the Default Lister manually.

*Example:* `Prefs SETLISTERDEFAULTS=force`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Suppress the success prompt when setting the Default Lister.

*Example:* `Prefs SETLISTERDEFAULTS=quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeflister**</td><td>

Turns off saving of the *Default Lister* while still saving other default parameters.

*Example:* `Prefs SETLISTERDEFAULTS=quiet,nodeflister`
</td></tr><tr><td>
</td><td>
</td><td>

**toolbars**</td><td>

Saves the default [toolbar set](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md) from the selected Lister.

*Example:* `Prefs SETLISTERDEFAULTS=toolbars,nodeflister`
</td></tr><tr><td>
</td><td>
</td><td>

**formats**</td><td>

Saves the default [folder format](/Manual/basic_concepts/folder_options/folder_formats.md) from the selected Lister.

*Example:* `Prefs SETLISTERDEFAULTS=force,quiet,formats,toolbars,nodeflister`
</td></tr><tr><td>
SHOWICONS</td><td>
/S</td><td>

*(no value)*</td><td>

Displays icons for dynamic lists generated by the **LAYOUTLIST**, **STYLELIST** and **VFSPLUGINLIST** arguments.

*Example:* `Prefs LAYOUTLIST SHOWICONS`
</td></tr><tr><td>
STYLE</td><td>
/K</td><td>

*\<style name\>*</td><td>

Applies the specified [style](/Manual/basic_concepts/the_lister/styles.md) to the current Lister.

*Example:* `Prefs STYLE="Dual Horizontal"`
</td></tr><tr><td>
</td><td>
</td><td>

**^prev**</td><td>

This refers to the initial appearance of the Lister when it was opened, and lets you return to that state as if it were a normal style.

*Example:* `Prefs STYLE=^prev`
</td></tr><tr><td>
STYLEEDIT</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **[Layouts and Styles / Styles](/Manual/preferences/preferences_categories/layouts_and_styles/styles.md)** page in Preferences (equivalent to `Prefs PAGE=styles`).

*Example:* `Prefs STYLEEDIT`
</td></tr><tr><td>
STYLELIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a list of your saved [Lister styles](/Manual/basic_concepts/the_lister/styles.md) (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting an item from the generated list applies the specified style to the current Lister.

*Example:* `Prefs STYLELIST`
</td></tr><tr><td>
</td><td>
</td><td>

**showprevious**</td><td>

Includes the special "Previous" style in the generated list. This refers to the initial appearance of the Lister when it was opened, and lets you return to that state as if it were a normal style.

*Example:* `Prefs STYLELIST=showprevious`
</td></tr><tr><td>
STYLESAVE</td><td>
/O</td><td>

*(no value)*</td><td>

Saves the current appearance of the active Lister as a style.

*Example:* `Prefs STYLESAVE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<style name\>*</td><td>

Specifies the name for the style to create. Opus will prompt for a name if one is not provided.

*Example:* `Prefs STYLESAVE="My Style"`
</td></tr><tr><td>
THEMEIMPORT</td><td>
/K</td><td>

*\<filename\>*</td><td>

Imports the specified theme by copying it to the configuration folder. The full pathname must be specified.

*Example:* `Prefs THEMEIMPORT "c:\mythemes\dark.dlt"`
</td></tr><tr><td>
THEMELOAD</td><td>
/O</td><td>

*(no value)*

or

**all**</td><td>

All aspects of the theme specified by **THEMENAME** will be loaded.

The two examples below do the same thing.

*Example:* `Prefs THEMENAME=!defaultdark THEMELOAD`  
*Example:* `Prefs THEMENAME=!defaultdark THEMELOAD=all`

Loading a theme will replace aspects of your configuration. Loading a theme via this command will **not** save a backup of your old settings; use the Preferences user interface instead if you need that.

If you only want to load certain aspects of the theme, use one or more of the other values, below. Separate multiple values with a single comma and no spaces.

*Example:* `Prefs THEMENAME="Rainbow" THEMELOAD=colors,blending`
</td></tr><tr><td>
</td><td>
</td><td>

**blending**</td><td>

Loads the theme's *Color Blending* data.

*Example:* `Prefs THEMENAME=!defaultlight THEMELOAD=blending`
</td></tr><tr><td>
</td><td>
</td><td>

**colors**</td><td>

Loads the theme's *Directory Opus Colors* data.

*Example:* `Prefs THEMENAME="Cool" THEMELOAD=colors`
</td></tr><tr><td>
</td><td>
</td><td>

**fonts**</td><td>

Loads the theme's *Fonts* data.

*Example:* `Prefs THEMENAME="Big Text" THEMELOAD=fonts`
</td></tr><tr><td>
</td><td>
</td><td>

**images**</td><td>

Loads the theme's *Images* data.

*Example:* `Prefs THEMENAME="Cats" THEMELOAD=images,colors`
</td></tr><tr><td>
</td><td>
</td><td>

**wincolors**</td><td>

Loads the theme's *Windows Colors* data.

*Example:* `Prefs THEMENAME="My Theme" THEMELOAD=wincolors`
</td></tr><tr><td>
THEMENAME</td><td>
/K</td><td>

*\<theme file\>*</td><td>

Specifies the filename of the theme to load, when combined with the **THEMELOAD** argument.

Must be the name of the **.dlt** theme file on disk. A theme's filename may differ from the name displayed in Preferences, but the UI can generate the whole command for you: Double-click a theme in Preferences, then open the *Apply* button's menu for an option that puts the command into the clipboard.

The **.dlt** extension is optional and will be added automatically if omitted.

You may specify the full path to a theme file anywhere on your system. If a full path is not given, the specified name (or relative path) is assumed to be relative to the Themes config folder.

*Example:* `Prefs THEMENAME="My Theme" THEMELOAD`
</td></tr><tr><td>
</td><td>
</td><td>

**!defaultdark**</td><td>

Loads the internal *Default Dark* theme, effectively resetting some or all of your cosmetic settings.

*Example:* `Prefs THEMENAME="!defaultdark" THEMELOAD`
</td></tr><tr><td>
</td><td>
</td><td>

**!defaultlight**</td><td>

Loads the internal *Default Light* theme, effectively resetting some or all of your cosmetic settings.

*Example:* `Prefs THEMENAME="!defaultlight" THEMELOAD`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<backup file\>*</td><td>

Specifies the filename for the configuration backup (used with the **BACKUP** or **BACKUPRESTORE** argument).

*Example:* `Prefs BACKUP TO="/mydocuments/OpusPrefsBackup {date\|yyyy-MM-dd}"`
</td></tr><tr><td>
TOOLBARS</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **Toolbars** tab in the **Customize** dialog (equivalent to `Prefs CUSTOMIZE=toolbars`).

*Example:* `Prefs TOOLBARS`
</td></tr><tr><td>
VFSPLUGINABOUT</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Displays the **About** dialog for the specified [VFS plugin](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.md).

*Example:* `Prefs VFSPLUGINABOUT opus7zip.dll`
</td></tr><tr><td>
VFSPLUGINCONFIG</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Displays the **Configuration** dialog for the specified VFS plugin.

*Example:* `Prefs VFSPLUGINCONFIG opus7zip.dll`

A single VFS plugin DLL may present itself as multiple types. For example, the Archives plugin (opus7zip.dll) which comes with Opus has separate types for 7z, RAR, ISO, and so on. To display the config window for a particular type, add a ':' character and then the name of the type, as found in the Preferences VFS Plugins page.

*Example:* `Prefs VFSPLUGINCONFIG opus7zip.dll:7z`
</td></tr><tr><td>
VFSPLUGINDISABLE</td><td>
/K</td><td>

*\<plugin name\>*</td><td>

Enable or disable the specified VFS plugin. If the plugin is currently enabled it will be disabled, and vice versa.

*Example:* `Prefs VFSPLUGINDISABLE opus7zip.dll`

A single VFS plugin DLL may present itself as multiple types. For example, the Archives plugin (opus7zip.dll) which comes with Opus has separate types for 7z, RAR, ISO, and so on. If you specify just the name of the DLL, the entire plugin will be toggled. You can also toggle individual types (assuming the plugin as a whole is still enabled) by adding a ':' character after the DLL name and then the name of the type, as found in the Preferences VFS Plugins page.

*Example:* `Prefs VFSPLUGINDISABLE opus7zip.dll:rar`
</td></tr><tr><td>
</td><td>
</td><td>

**enable**</td><td>

Enable the specified VFS plugin.

*Example:* `Prefs VFSPLUGINDISABLE opus7zip.dll,enable`
</td></tr><tr><td>
</td><td>
</td><td>

**disable**</td><td>

Disable the specified VFS plugin.

*Example:* `Prefs VFSPLUGINDISABLE opus7zip.dll,disable`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggling is the default, if neither "enable" nor "disable" is specified, but you can specify "toggle" if you wish to be more explicit.

Note that when a **VFSPLUGINDISABLE** button is a toggle, the button will appear active (e.g. checked or highlighted) when plugins are *disabled*. As with most commands, you can add **@toggle:invert** on a new line at the top of the command sequence to reverse this.

//<Example://>

    @toggle:invert
    Prefs VFSPLUGINDISABLE="opus7zip.dll,toggle"
</td></tr><tr><td>
VFSPLUGINLIST</td><td>
/S</td><td>

*(no value)*</td><td>

Displays a list of the installed VFS plugins (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Each plugin in the list has a sub-menu containing *about*, *configure*, and *enable/disable* commands.

*Example:* `Prefs VFSPLUGINLIST`
</td></tr><tr><td>
VFSPLUGINMANAGER</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **[Zip & Other Archives / Archive and VFS Plugins](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.md)** page in Preferences (equivalent to `Prefs PAGE=vfsplugins`).

*Example:* `Prefs VFSPLUGINMANAGER`
</td></tr></tbody>
</table>

**Viewer Plugins:** See the separate **[Show command](show.md)** for managing Viewer Plugins.
