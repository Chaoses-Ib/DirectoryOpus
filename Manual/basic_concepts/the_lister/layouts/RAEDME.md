# Layouts

A Lister Layout is a saved collection of one or more Listers that you can re-open at any time. Layouts are created when you save your currently open Listers as a set using the commands in the *Settings / Lister Layouts* menu.

![](/Manual/images/media/layouts_save_menu.png) 

The **Save This Lister** command saves only the currently active Lister, whereas the **Save All Listers** command saves **all** open Listers to the layout. (If you are using the virtual desktops feature in Windows 10 and above, only the windows on the active virtual desktop will be saved by default. You can change this via the advanced **[Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** setting.) The **Edit Layouts** command will open the Preferences dialog showing the **[Layouts and Styles / Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md)** page. From this page you can view a list of all your saved layouts, rename them, re-order them, delete them, etc.

When you save a Layout, you can choose various options that will apply whenever that layout is re-loaded:

![](/Manual/images/media/save_layout.png)

  
Depending on the selected options, almost everything about the state of the saved Lister is remembered, including:

- Its size and position on-screen (can be affected by the **Open this layout relative to the monitor the mouse is on** option)
- Whether it is in single or dual-file display mode
- Whether the folder tree and other UI elements like the viewer panel and metadata pane are open
- The currently displayed folder or folders
- Any folder tabs currently open, and which tab is currently active
- The folder format of the current folder and any folder tabs (if **Use folder formats saved within this layout** is turned on)
- The toolbars currently open in the Lister (if **Use toolbars saved within this layout** is turned on)

The last two items are important to mention. Because the toolbars and folder formats for each folder and tab are stored in the layout, when the layout is re-opened the stored settings will be used, overriding any [saved folder formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) or the default toolbars if they have changed. If you want to make a change to a folder format or toolbars stored in a layout, you must either re-save the layout, or use the ***Layouts & Folder Tabs*** variants in the **[Folder Options](../folder_options/RAEDME.md)** dialog **Save** drop-down.

You can edit the options for existing Layouts on the **[Layouts and Styles](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md)** Preferences page.

Saved layouts can be re-opened at any time using the layout list in the *Settings / Lister Layouts* menu or the context menu on the desktop (if the option in [Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/RAEDME.md) is on). You can also create shortcuts to layouts by dragging the layout from the list on the **[Layouts and Styles](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.md)** Preferences page, and dropping it on the desktop.

If the **Ignore toolbars** option is turned on for a layout, each Lister will open with the *Default Toolbar Set*. Use the **Settings / Toolbars / Set As Default Toolbar Set** command to update your default toolbar set if you want to change which toolbars are used by default.

More:

[The Default Lister](/Manual/basic_concepts/the_lister/layouts/the_default_lister.md)  
