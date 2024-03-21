# Scripting

The Directory Opus scripting interface lets you write scripts using any installed ActiveX-scripting language. This allows scripts to be written in common languages which you may already know. JScript (a relative of JavaScript) and VBScript are built into Windows and usually the easiest choices when it comes to compatibility, help and examples from the Directory Opus support forum, and easy sharing with other users. Other languages like Perlscript and Python can be obtained from third-party providers.

With the scripting interface you can, for example:

- Query the state of Listers, tabs, paths and toolbars
- Obtain lists of files and folders and discover information about them (basic information like name, size, date modified, etc, as well as metadata like EXIF information, MP3 tags, etc)
- Write buttons and hotkeys functions purely from script code without resorting to "Rename" hacks
- Test the state of certain system settings (similar to **@ifset** in a traditional function)
- Build collections of files and run commands (Opus internal commands and external programs) on them
- Display dialogs and popup menus
- Access the clipboard, environment variables and folder aliases
- Extend the list of Opus internal commands
- Add additional file and folder information columns that can be displayed in file displays and infotips
- Automatically trigger scripts based on certain events
- Save and load configuration (Opus provides an editor that you can use to edit your script config)

The scripting interface is present as a series of objects that export methods you can invoke and properties you can query (and sometimes set).

There are three ways to use scripts with Opus.

- **[Rename Scripts](/Manual/scripting/rename_scripts/README.md)** let you write a script within the [Advanced Rename](file_operations/renaming_files/advanced_rename/README.md) dialog that gives complete control over file renaming. 
- **[Script Functions](/Manual/scripting/script_functions.md)** are scripts that are [defined directly in a button, menu or hotkey](customize/creating_your_own_buttons/README.md).  
  \* **[Script Add-ins](/Manual/scripting/script_add-ins/README.md)** are script files that are installed in the Opus *Script Addins* folder. Whereas Script Functions are user-driven (e.g. they execute when the user clicks a button to specifically run the script), script add-ins are event driven. They provide one or more defined event handlers that Opus will invoke in certain situations, and are also used to implement [custom commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) and [columns](/Manual/scripting/example_scripts/adding_a_new_column.md).

See the [Scripting Reference](scripting/README.md) section for a complete guide to the Opus scripting objects, and the [Example Scripts](/Manual/scripting/example_scripts/README.md) section for some examples of the various types of scripts.

Any errors/warnings or text output from a script (via the **DOpus.Output** function) will be displayed in the *Script Log* panel (part of the *Utility Panel*). You can choose the type of information to display in the log using the **[Preferences / Miscellaneous / Advanced](preferences/preferences_categories/miscellaneous/advanced_options.md): script_output_level** option.

You can also use the **[CLI](additional_functionality/cli.md)** tool to design and test ad-hoc scripts.

More:

[Scripting Reference](reference/scripting_reference/README.md)  
[Rename Scripts](/Manual/scripting/rename_scripts/README.md)  
[Script Functions](/Manual/scripting/script_functions.md)  
[Script Dialogs](/Manual/scripting/script_dialogs/README.md)  
[Script Add-ins](/Manual/scripting/script_add-ins/README.md)  
[Resources](/Manual/scripting/resources/README.md)  
[Example Scripts](/Manual/scripting/example_scripts/README.md)  
