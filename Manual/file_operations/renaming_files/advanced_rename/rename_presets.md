# Rename Presets

The **presets** section of the Rename dialog lets you store and manage rename presets: predefined rename operations that can be invoked repeatedly without having to configure the parameters of the rename each time.

![](/Manual/images/media/13/rename_preset_example.png)

*Number Files* is a rename preset that comes supplied with Directory Opus as an example. To load a preset, simply double-click it, or select it from the list and click the **Load** button. The Rename dialog will be updated immediately with the settings from the preset. The title bar of the Rename dialog will display the name of the currently loaded preset. Opus will also notice if you’ve made changes to a loaded preset and ask if you want to save the changes before closing the Rename dialog.

The *Number Files* preset shown above has been made a favorite, which moves it to the top of the list and highlights it with a star icon. Simply click the star to mark or unmark a preset as a favorite.

The buttons above the presets list let you manage your presets. The **Last Rename** button loads the settings for the last-performed rename operation.

##### Manage menu

The drop-down **Manage** menu provides various commands for managing your presets (you can also right-click a preset to display its context menu).

![](/Manual/images/media/13/preset_management_menu.png)

- **Save**: Updates the currently loaded preset with the current settings from the rename dialog.
- **Save As**: Save the current rename dialog settings a sa new preset.
- **Assign To Group**: Lets you put your presets into groups (see below.)
- **Export Current Settings**: Exports the current configuration of the Rename dialog.
- **Create Function From Preset**: Puts a function on your clipboard that will run the selected preset as a command. You can go into [Customize](/Manual/customize/README.md) mode and add that to a toolbar or hotkey to automatically run the rename on selected files without opening the rename dialog.
- **Export Preset**: Exports the selected preset.
- **Import Preset File**: Import a preset that someone else has shared with you.
- **Reset Default Presets**: Lets you reset one or more of the default presets. Opus shows a list and lets you choose which ones to restore. The default presets are added to the list, they don't replace any existing presets you already have.

##### Putting presets in groups

The **Assign To Group** command in the **Manage** dropdown menu lets you put your presets into groups, which can be very useful if you've got a lot of presets to keep track of.

To move a preset to a group, select the **Assign To Group** command either from the drop-down, or by right-clicking the preset. If any groups have already been defined they'll be shown in the menu as seen above - you can either pick one or those, or create a new group (Opus will prompt you for its name). Any presets that aren't assigned to a specific group are displayed in the *Unspecified* group.
