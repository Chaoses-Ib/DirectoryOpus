# Context Menus

The Context Menus page is very similar to the [Toolbars](toolbars.md) page. It lets you configure various context menus (right-button menus). The menus that can be configured through this page are:

- **Tray Icon**: The context menu for the icon that Opus places in the taskbar notification area (a.k.a. "tray icon", "systray", etc). You can turn this icon on from the [Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/RAEDME.md) Preferences page, and then right-click it (in Windows 7 you can also left-click it) to display this configurable menu. In Windows 7 the icon will be hidden by Windows and moved to the icon overflow area by default, so if you want the icon to always be visible (which makes it much more useful) you will need to tell Windows to show it all the time.
- **Lister Context**: This is the context menu shown for a normal folder (a folder in the normal file system like *C:/Users*) when you right-click on the background of the file display (i.e. on an empty area, not on a file).
- **Lister ZIP Context**: Similar to **Lister Context** except this menu is shown when you are inside a Zip archive.
- **Lister FTP Context**: Similar to **Lister Context** except this menu is shown when you are connected to an FTP site.
- **Lister Column Header**: This is the context menu shown when you right-click the column header in a details or power mode file display.
- **Lister Collection Context**: Similar to **Lister Context** except this menu is shown when you have navigated to a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md).
- **Lister Libraries Context**: As above, this is the menu shown when you right-click on an empty area of the file display when viewing a [library](/Manual/basic_concepts/virtual_file_system/libraries.md). 
- **My Computer Context**: This menu is shown when you are viewing the [native view](/Manual/preferences/preferences_categories/folders/virtual_folders/RAEDME.md) of the *Computer* folder and you right-click an empty area of the file display.

For the most part the six folder context menu types will be the same, but they do let you add functions that are only relevant to one particular type of folder (e.g. the FTP folder context menu has commands for site properties and sending a raw command which don't make sense anywhere other than on an FTP site).

Functions launched from the **Lister Column Header** can discover which column was right-clicked on using the **%headeritem%** environment variable.

![](/Manual/images/media/customize_-_menus.png) 

To make changes to a menu, click it's checkbox in the list to reveal it. The menu will be displayed in a popup window - kind of like a floating toolbar - and it's this window where you can edit the buttons on the menu. Once you have finished editing the menu you can click the close button in the popup window's title, or click the checkbox again (or just close the Customize dialog). You can display more than one of the menus at once while editing, if for example you want to drag and drop buttons from one to the other.

On the right-hand side of the dialog page are the same **Background** and **Images & Labels** settings that are found on the [Toolbars](toolbars.md) tab. Select a menu from the list to make changes to these settings.

You can reset the context menus to their default settings using the command in the **File** menu.
