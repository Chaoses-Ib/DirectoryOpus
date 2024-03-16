# Modules

Modules are one of the two ways to split a large single script file into multiple files.

The other way, [include files](include_files.md), is designed for sharing code between multiple scripts. Modules, on the other hand, let you take what would be a single large file, and split it into multiple parts. When Opus runs your script it joins the files back together in memory, so in effect what you still have is a single large file - however you can work on it in separate parts, keeping related functionality together.

Module filenames must begin with the main script's name, followed by the module name, and have a `.osm` suffix.

For example, say you have a big script file called `MyScript.js` that you want to split up three files to make it easier to maintain - initialisation code, utility functions and the main script logic. Your files might be called:

- `MyScript.js` - this could include the initialisation code like `OnInitScript`.
- `MyScript.js.Utilities.osm` - this could be a module containing any utility functions used by the rest of the script
- `MyScript.js.Main.osm` - this could be the main logic of the script

Unlike include files, you don't need to explicitly say that you want to load a module - when the base script is loaded, all its modules are loaded as well (this is why the filenames are structured as they are - so that Opus can identify modules automatically).

The [script editor](../script_editor/RAEDME.md) lets you create new module files for an existing script.
