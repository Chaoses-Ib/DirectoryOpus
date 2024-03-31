# The Default Lister

The Default Lister is a special [saved layout]() that consists of a single Lister. It is generally used whenever a "new" Lister is opened and a specific saved layout is not specified. The default Lister exists automatically - you do not need to create it yourself - and by default, it is updated automatically whenever you close a Lister.

### When is the default Lister used?

There are many different ways that a new Lister can be opened, and whether the default Lister is used or not depends on the method you open the Lister and any settings that may affect that particular method.

- Double-clicking on the Directory Opus program shortcut, or clicking its icon when it's pinned to taskbar, will generally use the default Lister if Opus was already running.
  If Opus was't already running the options on the **[Launching Opus / Startup](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.md)** Preferences page control whether the default Lister is used or not.

- Double-clicking an empty spot on the desktop will open the default Lister, if the **Open the Default Lister** option is enabled on the [Launching Opus / From the Desktop](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_desktop.md) Preferences page.
- If [Explorer Replacement](../../explorer_replacement.md) mode is enabled, the default Lister will be used whenever a new Lister is opened due to Explorer Replacement (e.g. double-clicking on a shortcut to a folder on the desktop).
- Pressing <kbd>Win+E</kbd> can open the default Lister, depending on the settings on the [Launching Opus / From the Win + E hotkey](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.md) Preferences page.
- Double-clicking the Opus taskbar notification icon will open the default Lister if the appropriate option is enabled on the **[Launching Opus / From the Taskbar icon](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_taskbar_icon.md)** Preferences page.
- A lister opened using the raw `Go NEW` command will generally use the default Lister.

### When is the default Lister NOT used?

The default Lister isn't used whenever a saved Lister layout is opened - either by manually opening the layout, or by triggering an action (like double-click on the desktop) that's configured to open a layout.

### Default Lister options

The [Default Lister](/Manual/preferences/preferences_categories/layouts_and_styles/default_lister.md) Preferences page contains options that control how the default Lister is used. Three options are worth mentioning here:

- **Ignore folder format of Default Lister**: Because the default Lister is actually a saved layout, it stores within it the folder format that was in use when the layout was saved or updated. If this option is turned on, the folder format stored within the default Lister is ignored - instead, the normal folder format for the path being displayed in the new Lister is used.
- **Ignore toolbars of Default Lister**: Similarly, the toolbars stored in the default Lister will be ignored if this option is on, and the [default toolbar set](../toolbars/the_default_toolbars/README.md) will be used instead.
- **Update Default Lister automatically when closing a Lister option**: If turned off, you can update the default Lister settings manually using the **Set As Default Lister** command in the **Settings** dropdown menu.
