# Layouts

A Lister Layout is a saved collection of one or more Listers that you can re-open at any time. They're a great way to define separate environments for different tasks - and switching between them is as easy as clicking a button.

##### What's saved in a layout

Almost everything about the state of a saved Lister is remembered, including:

- Its size and position on-screen
- Whether it is in single or dual-file display mode
- Whether the folder tree and other UI elements like the viewer panel and metadata pane are open
- The currently displayed folder or folders
- Any folder tabs currently open, and which tab is currently active
- The folder format of the current folder and any folder tabs
- The toolbars currently open in the Lister

Although layouts save everything, you can choose which settings are restored when you load a saved layout.

##### Saving a layout

There's no "layout editor" - instead, layouts are created when you save your currently open Listers as a set.

The commands to do this are in the **Settings / Lister Layouts** menu:

- **Save This Lister**: Saves only the currently active Lister to the layout.
- **Save All Listers**: Saves **all** open Listers to the layout.

##### Virtual desktops

If you are using the virtual desktops feature in Windows 10 and above, only the windows on the active virtual desktop will be saved by default. You can change this using the **Save Listers on all virtual desktops** option when saving the layout.

##### Editing layouts

The **Edit Layout** command in the **Settings / Lister Layouts** menu takes you to the [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md) page in Preferences.

From this page you can view a list of all your saved layouts, rename them, re-order them, delete them, etc.

You can also update a saved Layout using the **Update** button on the *Edit Layout* dialog.

##### Loading a layout

The **Settings / Lister Layouts** menu shows a list of your layouts - simply select one from there to load it.

There's an option on the [Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/RAEDME.md) Preferences page to add a desktop context menu with a list of layouts. If turned on, right-click an empty spot on your desktop to show the menu.

You can also create shortcuts to layouts by dragging the layout from the list on the **[Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md)** Preferences page, and dropping it on the desktop.

##### Options when you load a layout

Each layout has a set of options that controls how it's loaded by default (the default options can be overridden using the `Prefs` internal command).

- **Close all existing Listers when loading this layout**: Any Listers already open will be closed when the Listers in the layout are opened.
  - **Close Listers on all virtual desktops**: Normally Listers on other desktops are left alone; this will close them too.
- **Use folder formats saved within this lister**: Each folder (in every tab) within the layout will be restored with the [folder format](/Manual/basic_concepts/folder_options/RAEDME.md) it had when the layout was saved. If turned off, each folder will be loaded with its default format.
- **Use toolbars saved within this layout**: Each Lister will open with the [toolbars](/Manual/basic_concepts/the_lister/toolbars/RAEDME.md) that were open when it was saved to the layout, rather than the default toolbar set.
- **Open layout relative to the monitor the mouse is currently on**: If you have multiple monitors, normally each Lister is restored to the monitor it was on when the layout was saved. This makes them re-open on the monitor the mouse cursor is currently on.
- **Restore each Lister to its original virtual desktop**: If turned off, every Lister in the layout will open on the current desktop.
- **Hide this layout from layout lists**: Lets you have a layout that you can load using the internal `Prefs LAYOUT` command, but that doesn't show up in the list in the **Settings / Lister Layouts** menu or desktop context menu.

The [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md) page in Preferences shows you a list of your layouts. In the list, layouts are shown along with a code that represents the default options in force when that layout is loaded.

To change a layout's options, double-click it (or select it and click the **Edit** button) in the list on the [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md) page.

##### A note on folder formats and toolbars

Folder formats and toolbars stored within layouts can be a point of confusion, particularly when you want to update the defaults.

When a layout is re-opened the stored settings will be used (if enabled), overriding any [saved folder formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) or the default toolbars if they have changed.

When you save a [folder format](../folder_options/RAEDME.md) there's an option to update the format for that folder stored in any layouts. If you want to change the toolbars stored in a layout, you generally need to re-save the layout.

More:  
[The Default Lister](/Manual/basic_concepts/the_lister/layouts/the_default_lister.md)  
