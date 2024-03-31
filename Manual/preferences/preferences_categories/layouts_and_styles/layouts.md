# Layouts

This page shows a list of your saved [Lister layouts](/Manual/basic_concepts/the_lister/layouts/README.md). A Lister layout is a saved collection of one or more Listers that you can re-open at any time. If you select a layout in this list a tiny preview at the bottom of the page gives you an indication of the Listers defined by the layout.

Use the toolbar at the top of the page to edit your layouts.

- **New Layout**: Saves all currently open Listers as a new layout (or over the top of an existing layout if the name matches one already in use).
- **New Folder**: You can organise layouts into folders (use drag and drop to move existing layouts into a folder).
- **Edit**: Change various layout options, and update the Listers within it (see below for details).
- **Rename**: Rename the selected layout.
- **Delete**: Delete the selected layout.
- **Insert Separator**: Inserts a separator line above the selected layout.

Use the **Move Up**, **Move Down** and **Sort** buttons to change the order of layouts. The order set here is how the list of layouts will appear in toolbar menus etc.

You can open a Lister layout by using the layout list in the *Settings / Lister Layouts* menu or the context menu on the desktop (if the option in [Windows Integration](../miscellaneous/windows_integration/README.md) is on). You can also create shortcuts to layouts by dragging the layout from the list (or using the **Create shortcut** button) and dropping it on the desktop.

### Layout options

Layouts have various options and to the right of each layout in the list a number of flag letters are shown that represent these options:

|     |                                                     |
|-----|-----------------------------------------------------|
| C   | Close all existing Listers                          |
| A   | Close Listers on all virtual desktops               |
| F   | Use folder formats saved within this layout         |
| T   | Use toolbars saved within this layout               |
| M   | Open layout relative to the monitor the mouse is on |
| V   | Restore each Lister to its original virtual desktop |
| H   | Hide this layout from layout lists                  |

### Editing Layouts

Click the **Edit** button or double-click a layout to edit it.

![](/Manual/images/media/13/layout_edit.png)

- **Name**: Set a name for the layout.
- **Description**: You can add an optional description. If you don't set this a description based on the layout's contents will be shown.
- **Close all existing Listers when loading this layout**: If this option is on, any existing Listers will be closed automatically when this layout is loaded.
  - **Close Listers on all virtual desktops**: Listers on all virtual desktops (Windows 10 and up) will be closed, not just those on the current desktop.
- **Use folder formats saved within this layout**: When you save a Lister layout, the folder formats currently used the file displays are also saved. If you turn this option on, the saved formats will be used when the layout is re-opened. If you turn this option off, the formats will be come from the usual [Folder Formats](../folders/folder_formats/README.md) system the same as if you navigated to the folders normally.
- **Use toolbars saved within this layout**: When you save a Lister layout, the toolbars currently in use are also saved. If you turn this option on, the saved toolbars will be used when re-opening the layout. If you turn it off, your *Default Toolbar Set* will be used instead. (The *Default Toolbar Set* can be updated via **Settings / Toolbars / Set As Default Toolbar Set**.)
- **Open layout relative to the monitor the mouse is currently on**: Normally a saved layout will re-open its Listers in the same location on-screen they were saved in. If you have a multiple monitor system and turn this option on, the Listers will be opened relative to the monitor the mouse is on (so, for instance, a Lister that was saved on monitor \#1 would open in the same relative location on monitor \#2 if the mouse was on that monitor at the time the layout was opened).
- **Restore each Lister to its original virtual desktop**: If you save a layout containing Listers on multiple virtual desktops, they'll be restored to the same desktop when the layout is opened.
- **Hide this layout from layout lists**: This option lets you mark a layout that is hidden when the layout list is displayed. Layouts that are hidden can still be accessed using the `Prefs LAYOUT` command.

### Updating an existing layout

The **Update** button on the *Edit Layout* dialog makes it easier to update an existing saved layout.

When you click the **Update** button, all existing Listers will be closed temporarily and the saved layout in question will be opened. You can then make the changes you want to the layout's Listers, before going back to the Preferences window.

![](/Manual/images/media/13/layout_update.png)

Click OK to save the modified layout. The previous Listers you had open will then be restored.
