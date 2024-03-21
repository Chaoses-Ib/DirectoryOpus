# Default Lister

This page contains options that affect the way the [default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md) settings are used. The default Lister is the configuration that opens whenever you open a new Lister in Opus without specifying a layout. The default Lister is configured by taking an existing Lister and setting it as the default using the **Set As Default Lister** command in the Settings menu. Please see the [page on this concept](/Manual/basic_concepts/the_lister/the_default_lister.md) for more details.

- **Ignore folder format of Default Lister**: When you set a Lister as the default, the folder format currently used by its file displays is also saved. If you turn this option on, the saved format will be ignored when a new default Lister is opened. Instead, the format will be set by the usual process of the [Folder Formats](../folders/folder_formats/README.md) system for the folder being displayed in the new Lister.
- **Ignore toolbars of Default Lister**: When you set a Lister as the default, the toolbars it is using are also saved. If you turn this option on, the saved toolbars will be ignored when opening a new default Lister. Instead, your *Default Toolbar Set* will be used, and can be updated via **Settings / Toolbars / Set As Default Toolbar Set**.
- **Update Default Lister automatically when closing a Lister**: If this option is turned on then whenever you close a Lister, its settings will be saved as the new default. If you open a Lister, modify it in some way and close it again, the default Lister settings will be updated automatically. You will then get those new default settings back when you open a new Lister.

##### Default Lister positioning

This controls where new Listers appear on-screen when they are opened using the default Lister settings. Listers opened via a saved layout aren't affected by these options. If your default Lister is maximized then new Listers will also be maximized and the positioning options mainly just determine which monitor will be used.

- **In a fixed position relative to the monitor the mouse is on**: The position of the new Lister is based on the default Lister's position when it was saved. If you have more than one monitor then the new Lister will open on whichever monitor the mouse is over at the time, with its position relative to that monitor. For example, if you save the default Lister in the bottom-left corner of your primary monitor, then move your mouse to your secondary monitor and open a new Lister, the new Lister will open in the bottom-left corner of your secondary monitor. The new Lister's position will be adjusted to ensure it does not go off the edge of the monitor it opens on.
- **Always in the same position**: The new Lister always opens in the exact position, and on the same monitor, where the default Lister was saved. The mouse pointer's position does not affect where the new Lister opens. If the default Lister's position is partially off-screen or between two monitors, the new Lister will be the same.
- **Always over the mouse pointer**: The new Lister always opens underneath the mouse pointer. For example, if you have two monitors and the mouse is in the top-right corner of your second monitor then the new Lister will open in the same corner, regardless of where the Default Lister was saved. The new Lister's position will be adjusted to ensure it does not go off the edge of the monitor it opens on.

##### Virtual desktops

These options apply when using virtual desktops under Windows 10 and above:

- **Always open Default Lister on the current desktop**: The default Lister will be opened on whichever virtual desktop you're currently working on. If turned off, the default Lister will open on the virtual desktop it was saved on.
- **Avoid switching desktops to find existing Listers**: Various actions in Opus can look for an existing Lister before opening a new one; this option stops Opus switching desktops when it does that. If the Lister isn't on the current virtual desktop it'll be ignored.
