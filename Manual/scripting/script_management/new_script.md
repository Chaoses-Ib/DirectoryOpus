# Create New Script

The *Create New Script* dialog is accessed using the **New** command from the [script management]() dialog.

![](/Manual/images/scripting/new_script.png)

- **Script language**: Choose from *JScript* and *VBScript* here. Note that you can use other Active Scripting-compatible scripting languages in Opus, but you'll need to create the script files manually (simply create them in the `/dopusdata/Script AddIns` folder and Opus will load them automatically).
- **Script name**: Give your script a name. This is shown in the script list in the script management dialog.
- **Description**: A more detailed description of your script. This is shown under the script list when the script is selected.
- **Copyright**: A copyright notice, also displayed under the script list for the selected script.
- **Create an include file script**: Check this box if you want to create an [include file script](../script_add-ins/include_files.md).
  - **Shared include file**: Check this if you want your include file script to be easily usable by multiple scripts. Shared include files can be included using just their filename.
- **New style commands and columns**: If your script is targeted at Opus 12 and above, check this box to use the newer (and better) method of defining script commands and columns.
- **Create as a script package**: The script will be created as a `.osp` package rather than a single script file.
- **Create with a .txt extension**: If you're not creating the script as a package, you might want to check this to add a `.txt` suffix to the script filename (`.txt` files are easier to share on the web than `.js` files).

The list on the right lets you select the various [script events](/Manual/reference/scripting_reference/scripting_events/RAEDME.md) that you want to implement in your new script. Opus will create boilerplate code for all selected events. You can add additional events later if you need to.

At the bottom of the event list are the entries **NewScriptCommand** and **NewScriptColumn**. These are placeholders for commands and columns that you want to implement in your script. If you turn one of them on, Opus will prompt you to enter a name for the new command or column. It will then be added to the event list in its own right, and the **NewScriptCommand** / **NewScriptColumn** entries will be available again to add more commands or columns. The boilerplate code for any commands/columns you specify here will be created automatically.

Once the new script has been created the [script editor](../script_editor/RAEDME.md) will open automatically.
