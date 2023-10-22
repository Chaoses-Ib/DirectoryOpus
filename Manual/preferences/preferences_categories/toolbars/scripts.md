# Scripts

The **Scripts** page displays a list of all your installed [script add-ins](/Manual/scripting/script_add-ins/RAEDME.md).

![](/Manual/images/media/script_list_001.png)

You can configure which columns the script list displays by right-clicking the column header. Any columns that aren't turned on are displayed at the bottom of the dialog when you select a script from the list. The checkbox next to each script name lets you disable the script without deleting it.

The toolbar buttons at the top allow you to control your installed scripts:

- ![](/Manual/images/media/script_new.png) **New Script**: Displays the *Create New Script* dialog, which makes it easy to start a new script. See below for more information.
- ![](/Manual/images/media/script_import.png) **Import**: Import a script that someone has shared with you. You can also install new script files by dragging and dropping them onto the list
- ![](/Manual/images/media/script_delete.png) **Delete**: Delete a script. If the script is part of a script package, the whole package will be deleted.
- ![](/Manual/images/media/script_about.png) **About**: If a script provides About information (via the **[OnAboutScript](/Manual/reference/scripting_reference/scripting_events/onaboutscript.md)** event), clicking the *About* button will display it.
- ![](/Manual/images/media/script_configure.png) **Configure**: If a script defines configuration options, clicking the *Configure* button will display a dialog letting you make changes to the script's configuration.
- ![](/Manual/images/media/script_edit.png) **Edit**: If a script is a standalone file (rather than a script package), clicking the *Edit* button will open it in your default text editor.
- ![](/Manual/images/media/script_folder.png) **Open Folder**: Opens the script folder in a new tab (the **/dopusdata/Script AddIns** folder).
- ![](/Manual/images/media/script_refresh.png) **Refresh**: Refresh the list of scripts.
- ![](/Manual/images/media/script_disable.png) **Disable All Scripts**: This option lets you disable all script add-ins at once - individual enable/disable states will be preserved. You need to click **Apply** to make this change.

If you click the New Script button ( ![](/Manual/images/media/script_new.png) ) the *Create New Script* dialog is displayed, which makes it easy to build a new script

![](/Manual/images/media/newscript.png)

Currently this dialog lets you create a template for a *JScript* or *VBScript* script.

Select the desired language, and enter a name, optional description and copyright string. Then use the checkboxes in the list to select the events that you want the script to create functions for.

The last two events in the list, *NewScriptColumn* and *NewScriptCommand*, lets you create a script that adds internal columns and commands. When you turn this option on it will activate and let you enter a name for the column or command. Press return to accept the new name, and another *NewScriptColumn* or *NewScriptCommand* entry will be added to the list. In this way you can easily create a template for a script that [adds multiple internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md).

The option to create the script with a .txt extension (that is, .js.txt or .vbs.txt, depending on language) exists to help you share scripts with other people, since downloads with .js and .vbs extensions are blocked by many websites, browsers and antivirus. The script will work the same in either case, and can always be renamed afterwards.
