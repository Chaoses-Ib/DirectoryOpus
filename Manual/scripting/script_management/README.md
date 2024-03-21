# Script Management

The *Script Management* dialog shows you all your installed [script add-ins](/Manual/scripting/script_add-ins/README.md). You can create new scripts or manage your existing ones from here.

To get to the Script Management dialog, use the **Scripts** command in the default **Settings** menu. If you're using old toolbars without that command in them, you can add it from the **Customize / Default Toolbars** tab. The raw command is `Prefs SCRIPTS`.

##### Script list

Your installed scripts are shown in the list, with a number of columns:

- **Name**: The name of the script (set by the script itself). You can disable a script using the checkbox in front of its name.
  If a script has configuration options, it will be indicated with a cog icon - you can click this icon or use the **Configure** button in the toolbar to edit the configuration.

- **Status**: Indicates whether the script has loaded successfully or if it encountered an error.
- **Version**: The version number of the script (set by the script itself).
- **File**: The name of the file the script is implemented by.

Scripts can specify a group as part of their initialisation - if any scripts have done this, the script list will be split into two or more groups.

By default [include file scripts](script_add-ins/include_files.md) are also shown in the list, but you can hide them with the command in the **File** menu.

##### Installing a new script

The easiest way to install a new script is with the **File \> Install** command (or click the **Install** button on the toolbar).

The [script installer](/Manual/scripting/script_management/installer.md) will open to guide you through the install process. You can install single script files (e.g. `.js` or `.js.txt`), script packages (`.osp` files) and script install files (`.opusscriptinstall` files) this way.

##### Creating a new script

Click the **New** button to create a new script. The *[Create New Script](/Manual/scripting/script_management/new_script.md)* dialog opens.

##### Script management

Select a script from the list to see information about it at the bottom of the dialog.

You can right-click a script, or use the **Script** drop-down menu, to manage the selected script. Some of these functions are also available on the toolbar itself.

- **Enable** / **Disable**: Lets you enable or disable the script. Same effect as clicking the checkbox in front of its name.
- **About**: Shows information about the script (if the script provides it).
- **Configure**: Configures the script parameters (if the script has any).
- **Edit**: Opens the [script editor](script_editor/README.md) to edit the script.
- **Convert to Package**: Converts a standalone script file to a [script package](script_add-ins/script_package.md).
- **Share**: Converts the script to a [script install file](/Manual/scripting/script_management/installer.md) to share with other Opus 13 users.
- **Delete**: Deletes the selected script.
