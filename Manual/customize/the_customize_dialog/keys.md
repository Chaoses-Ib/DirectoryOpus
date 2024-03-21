# Keys

The Keys page lets you view and configure "keyboard shortcuts" or "hotkeys" (combinations of keys) that can be used to run commands or launch programs. Opus lets you assign one or more keys to a toolbar button or menu command, and pressing the key has the same effect as clicking the button. You can also create "hotkey-only" functions, which only exist as key assignments and aren't linked to a toolbar.

##### Categories

The category list lets you view keys by category or show all keys together. The categories are:

- **Conflicts**: Shows any conflicts - where the same key has been assigned to two more more actions at the same time.
- **Lister keys**: These are keys that only work inside a Lister - generally when the file display is active.
  - **Hotkeys**: Hotkey-only functions (not assigned to a button or menu).
  - **Toolbars**: Keys assigned to toolbar or menu buttons.
  - **Inactive Toolbars**: Keys from toolbars that are turned off (the keys themselves are still active though).
  - **Folder Tree**: Hotkey-only functions that only work when the folder tree is active.
  - **Quick Keys**: Keys configured in [Preferences](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md) to activate the [find-as-you-type field](/Manual/basic_concepts/the_lister/find-as-you-type_field.md).
  - **Favorite Folders**: Keys assigned to folders in your [favorites list](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.md).
- **System-wide keys**: These are hotkeys that work anywhere in the system (when Opus is running). You don't need a Lister open to use them - Opus just has to be running in the background.
  - **Hotkeys**: Hotkey-only functions.
  - **Floating Toolbars**: Keys assigned to buttons on floating toolbars.
  - **Tray Menu**: Keys assigned to buttons in the [tray icon menu](context_menus.md).
- **Viewer keys**: Hotkeys that only work in the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md).
  - **Hotkeys**: Hotkey-only functions.
  - **Toolbar**: Keys assigned to buttons in the image viewer toolbar.

##### Keys

The list shows one entry for each key combination assigned. The checkboxes next to each key in the list let you temporarily disable a hotkey without having to delete it.

If a function has multiple key assignments then they're shown separately (and can be enabled/disabled separately as well).

![](/Manual/images/media/13/hotkey_multiple.png)

For example, the path field on the location bar has three key assignments by default - <kbd>F4</kbd>, <kbd>Alt+D</kbd> and <kbd>Ctrl+L</kbd>. All three are listed here, and you can see that visually they're all linked to the *Location* field on the *File display* toolbar.

At the bottom of the page are two fields that let you filter the hotkey list. You can search separately by key and by command.

##### Editing keys

Use the toolbar at the top of the page to manipulate the hotkeys. The **New** drop-down menu lets you create four types of keys here:

- **New Lister Hotkey**: Corresponds to the *Lister keys/Hotkeys* category.
- **New System-wide Hotkey**: Corresponds to the *System wide-keys/Hotkeys* category.
- **New Folder Tree Hotkey**: Corresponds to the *Lister keys/Folder Tree* category.
- **New Viewer Hotkey**: Corresponds to the *Viewer keys/Hotkeys* category.

No other key types can be created from here - instead, you create them "in situ" (e.g. for a toolbar button, you assign a key to it by editing the button itself). Similarly, only those four types of keys can be deleted from here.

However, most existing keys can be modified here - the only exception are the keys which are configured in Preferences (*Favorite Folders* and *Quick Keys*) - using the **Change Key** field at the top of the page.

##### Import and Export

In the ![](/Manual/images/media/13/prefs_menu.png) page menu at the top-right of the dialog are commands for exporting and importing hotkey lists.

You can export your hotkeys list in three different formats (use the **Save as type** drop-down in the save dialog to choose what type to use).

- *Importable Hotkey Format* is a format that you can use to export your hotkeys in order to re-import them into Directory Opus (e.g. on another computer, or to share your keys with a friend). Selecting this format actually exports the functions as well as the key information. When this format is selected only "true" hotkeys are exported - toolbar key assignments etc. are not.
- *Comma-Separated List* exports a list of all the hotkeys along with their names and descriptions (but not the functions they run) as a **.csv** file. For example, you could use this if you wanted to make yourself a printable key reference. You could import this file into Excel or Word and perform further manipulation on it before printing. In this mode, all types of hotkeys are exported.
- *Text Format* exports a list of all your hotkeys as a plain text file. Like the *Comma-Separated List* option, all types of hotkeys are exported in this mode.
