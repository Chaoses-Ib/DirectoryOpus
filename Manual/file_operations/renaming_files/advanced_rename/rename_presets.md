# Rename Presets

The **presets** section of the Rename dialog lets you store and manage rename presets: predefined rename operations that can be invoked repeatedly without having to configure the parameters of the rename each time.

![](/Manual/images/media/rename_preset_example.png)

In the above image, *Number Files* is a rename preset that comes supplied with Directory Opus as an example. To load a preset, simply select it from the list and click the **Load** button ( ![](/Manual/images/media/rename_load.png) ), or double-click its name in the list. The Rename Dialog will be updated immediately with the settings from the preset. The title bar of the Rename dialog will display the name of the currently loaded preset. Opus will also notice if you’ve made changes to a loaded preset and ask if you want to save the changes before closing the Rename dialog.

The buttons at the top of the presets section are:

- ![](/Manual/images/media/rename_load.png) **Load**: Select a preset and click Load to load its settings.
- ![](/Manual/images/media/rename_preset_management.png) **Preset Management**: Displays a drop-down menu letting you manage your presets.
- ![](/Manual/images/media/rename_rename_preset.png) **Rename**: Rename the selected preset.
- ![](/Manual/images/media/rename_delete_preset.png) **Delete**: Delete the selected preset.
- ![](/Manual/images/media/rename_last_rename.png) **Last Rename**: Load the settings for the last-performed rename operation. 

The drop-down **Preset Management** menu provides various commands for managing your presets (you can also right-click a preset to display its context menu).

![](/Manual/images/media/preset_management_menu.png)

Use the **Save** or **Save As** commands to save the current Rename Dialog settings as a new preset. The two export commands let you export a preset file that you can share with others - **Export Current Settings** exports the current configuration of the Rename dialog, and if you have an existing preset selected in the preset list, the second command lets you export that preset. **Import Preset File** lets you import a preset that someone else has shared with you.

The **Assign To Group** command lets you put your presets into groups, which can be very useful if you've got a lot of presets to keep track of.

![](/Manual/images/media/rename_preset_groups.png)

To move a preset to a group, select the **Assign To Group** command either from the **Preset Management** drop-down, or by right-clicking the preset. If any groups have already been defined they'll be shown in the menu as seen above - you can either pick one or those, or create a new group (Opus will prompt you for its name). Any presets that aren't assigned to a specific group are displayed in the *Unspecified* group.

Each preset in the list has a star icon displayed next to its name, which you can click to designate that preset as a favorite. Favorite presets are displayed at the top of the preset list - if the list is grouped, a separate *Favorites* group will be created automatically.

You can rename a preset using the **Rename** button ( ![](/Manual/images/media/rename_rename_preset.png) ) or by right-clicking it and selecting **Rename** from the context menu. You can also rename groups using their context menu.

You can delete a preset using the **Delete** button ( ![](/Manual/images/media/rename_delete_preset.png) ) or from its context menu. You can remove groups using their context menu although if you delete a group, the presets within it aren't deleted - they're simply removed from that group (which is why the command to do this is called *Ungroup* rather than Delete).

The **Last Rename** button ( ![](/Manual/images/media/rename_last_rename.png) ) loads the settings for the last rename that you performed using the Rename dialog.
