# Script Add-ins

*Script Add-ins* are script files that are installed in the Opus *Script Addins* folder (you can find this folder by typing **/dopusdata/Script AddIns** into the location field). Script add-ins are plain text files with an extension that specifies the script language in use (e.g. a file ending with **.js** would be a *JScript* script). One or more script add-ins can be bundled, optionally with a set of icons, in an archive called a *[Script Package](/Manual/scripting/script_add-ins/script_package.md)* (a zip file with the **.osp** suffix).

Whereas [script functions](script_functions.md) are only called whenever the button they reside in is clicked, script add-ins can be invoked automatically in response to one or more [events](/Manual/reference/scripting_reference/scripting_events/README.md). Each script can provide handling for one or more defined event entry points, and Opus will automatically call on each script that provides handling for the event in question. Some of the events that scripts are notified for include when tabs are activate or deactivated, before and after folder changes, when the view mode is changed and when Listers are opened or closed. Script add-ins can also implement [custom commands](example_scripts/adding_a_new_internal_command.md), which let you extend the Opus internal command set in a similar way to *User commands*, and [custom columns](example_scripts/adding_a_new_column.md), which let you add additional information columns for files and folders.

  
The **[Script Management](/Manual/scripting/script_management/README.md)** dialog displays a list of any add-in scripts that have been installed. You can use the checkbox to enable or disable each script.

![](/Manual/images/media/script_list_001.png)

If you select a script in the list it reveals more information about it (a description, copyright information, and a list of the commands, columns and events that the scripts implements). The **About** and **Configure** buttons will be active if the script supports those actions. Clicking the **Edit** button will open the script in your default text editor (standalone scripts only).

You can easily install new scripts or script packages by dragging and dropping them onto the *Scripts* list. You can also create a new script using the **New Script** button in the toolbar above the list of scripts. This displays the *Create New Script* dialog:

![](/Manual/images/media/newscript.png)

This dialog lets you create a template for a *JScript* or *VBScript* script. Select the desired language, and enter a name, optional description and copyright string, and then use the checkboxes in the list to select the events that you want the script to create functions for.

  
The last two events in the list, *NewScriptCommand* and *NewScriptColumn*, let you create a script that adds internal commands or columns. When you turn this option on it will activate and let you enter a new name for the command or column. Press return to accept the new name, and another *NewScriptXXX* entry will be added to the list. In this way you can easily create a template for a script that adds multiple internal commands or columns.

More:

[Script Package](/Manual/scripting/script_add-ins/script_package.md)  
