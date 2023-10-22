# Script Package

To make it easier to distribute your scripts to others, you can bundle one or more script add-ins in an archive called a *Script Package* (a zip file with the **.osp** suffix).

You can also include a set of icons that can provide the default icon images for any internal commands your scripts add.

To make a script package:

- Create a Zip archive (leave its suffix as **.zip** for the moment).
- Copy your script files (**.js**, **.vbs**, etc) into the archive.
- When finished, rename the archive to give it a **.osp** suffix.

If you like you can add **.osp** to the list of recognized Zip file extensions on the **[Zip & Other Archives / Zip Files](/Manual/preferences/preferences_categories/zip_and_other_archives/RAEDME.md)** page in Preferences, to make script packages easier to deal with in Opus.

If you want to add icons that your scripts can refer to:

- Create an icon set, following the specifications in the [Icon Sets](/Manual/reference/icon_sets/RAEDME.md) reference section. *Do not zip this to a **.dis** file.*
- Create a sub-folder in the script package archive called **icons**.
- Copy all the files of your icon set into the **icons** sub-folder.

In your scripts, you can use the icons in your icon set as the default toolbar button images for any [internal commands](../example_scripts/adding_a_new_internal_command.md) you add, using the **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.md).icon** property.

Script packages can also include external [script resource](../resources/RAEDME.md) files. These must be XML files with the file extension **.odxml**. You can use the **[Script](/Manual/reference/scripting_reference/scripting_objects/script.md).LoadResources** method in your script to load the script resource file from the package.
