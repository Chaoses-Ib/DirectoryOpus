# Starting Opus

We recommend that you set Opus to start automatically when Windows starts, using the options in the **[Launching Opus / Startup](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.md)** page in Preferences. Opus is designed to stay running in the background, even when no windows are open. There are several advantages to this:

- Opening a window (called a "Lister") is much quicker if Opus is already loaded in the background. Double-clicking the desktop or (if [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) is enabled) pressing <kbd>Win+E</kbd> or double-clicking a folder icon will cause a Lister to open almost instantly if Opus is already running - whereas there may be a delay of several seconds if Opus is not already in memory.
- Opus lets you create [floating toolbars](/Manual/additional_functionality/floating_toolbars/README.md) that you can use as command launchers - these can only be used when Opus is running.
- You can configure [system-wide hotkeys](/Manual/additional_functionality/system-wide_hotkeys.md) that run programs or initiate Opus functions - again, these only work when Opus is running.

You can also treat Opus like a traditional file manager, that you run when you need it and exit when not using it. The installer can place shortcut icons on the desktop and in the start menu, and you can use these icons to run Opus. You can also pin the icon to the taskbar and launch it that way.

##### Quitting Opus

To quit Opus when you're done using it, select the **Exit Directory Opus** command from the **File** menu in a Lister, or right-click on the taskbar notification icon (if enabled) and choose the exit command from that menu.

You can also set Opus to exit automatically when the last Lister is closed, with the **Shutdown Directory Opus when all functions finish** option on the [File Operations / Options](/Manual/preferences/preferences_categories/file_operations/options.md) Preferences page. With this option on, and Opus not set to run on startup, it will behave like a traditional, monolithic file manager.

We don't recommend killing the Opus process via task manager - you may end up with configuration files not saved or corrupted.
