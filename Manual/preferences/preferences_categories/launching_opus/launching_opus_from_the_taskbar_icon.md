# From the Taskbar Icon

This page lets you configure what happens when you double-click on the icon that Opus adds to the taskbar notification area (also called the "tray" or "systray" icon).

![](/Manual/images/media/taskbar_icon.png) 

Opus adds the taskbar icon when the option in the [Windows Integration](../miscellaneous/windows_integration/RAEDME.md) page is turned on. In Windows 7 the icon will be hidden by Windows and moved to the icon overflow area by default, so if you want the icon to always be visible (which makes the double-click options on this page more useful) you will need to tell Windows to show it all the time.

- **Disable**: Select this to disable double-click on the taskbar icon.
- **Bring the last active Lister to the front**: If there are one or more Listers already open, a double-click on the taskbar icon will bring to the front the one you used most recently. If no Listers are open a new one is opened using the Default Lister settings. If you are using Windows 10's *virtual desktops* feature, only windows on the currently active desktop will be considered, unless you turn off the advanced **[Advanced](../miscellaneous/advanced_options.md)** setting.
- **Open the Default Lister**: Opens a new Lister using the settings for the [Default Lister](/Manual/basic_concepts/the_lister/layouts/the_default_lister.md).
- **Open a saved Lister layout**: Opens a saved [Lister layout](/Manual/basic_concepts/the_lister/layouts/RAEDME.md). If you turn on the **Close existing Listers** option then any existing Listers will be closed before opening the layout - if this is off, existing Listers will be unaffected.
- **Run a defined User command**: Lets you select a [User command](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md) from the drop-down to be run whenever the taskbar icon is double-clicked. This can be used to perform more complex actions including running external programs.

Users of Windows 7 and greater may prefer to use the [Jump List](../favorites_and_recent/jumplist.md) rather than the tray icon as it offers far more flexibility.
