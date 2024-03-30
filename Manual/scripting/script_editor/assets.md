# Script Assets

![](/Manual/images/media/13/scripteditor_assets.png)

 The Assets panel in the script editor is where you view and manage the various files and resources that are part of your script.

- Packaged scripts (those with a `.osp` suffix) support multiple script code files (each of which can contain embedded resources like dialogs and strings), and image and icon files.
- Single file scripts (i.e. a `.js` or `.vbs` file) supported embedded resources.

The panel has three tabs (two in the case of single file scripts):

- **Scripts**: Lists the individual code files that make up this script. For a single file script, this list will contain just a single item (the file itself). A packaged script can contain multiple code files, and they will be listed separately. Each individual code file can be split up into [modules](../script_add-ins/modules.md), and these are shown indented under their primary file.
- **Resources**: Shows any dialogs or language string sets that have been embedded in any of the code files that make up the script.
- **Other**: For script packages, shows any icon sets or image files that the package contains.

To add or manage assets a script's assets, right-click on the item in question, or use the commands in the *Assets* drop-down menu.
