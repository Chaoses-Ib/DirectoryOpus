# Locking the Format

Opus lets you **lock** the format in the file display. When the format is locked, automatic changes to the format are disabled - the display format won't change at all as you navigate from one folder to another, unless you manually change it using the [Folder Options](folder_options_dialog/README.md) dialog.

### Toggling the format lock

Right-click the ![](/Manual/images/media/13/info.png) information icon on the status bar, and choose **Format Lock** from the context menu to toggle the lock. You can also use the **Format Lock** command from the **Folder** drop-down menu in the default toolbars.

### Padlock icon

When the format is locked, the information icon on status bar turns into a ![](/Manual/images/media/13/tab_-_locked.png) padlock icon instead.

When the format lock is on the current folder format is preserved. You can still make manual changes using the [Folder Format](folder_formats.md) dialog (or by clicking the column headers in details mode, etc.), but it won't automatically change again until after you turn the lock off.

### Turning off the lock

Click the padlock icon, or use the **Format Lock** menu commands, to unlock the format.

### Showing the padlock all the time

If you find you use the format lock feature a lot, you can turn on the **Enable format lock padlock icon** option on the [File Displays / Status Bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md) Preferences page. The ![](/Manual/images/media/13/info.png) icon will change to show the padlock permanently, and you can toggle the lock on and off simply by clicking it.

### The status bar icon can be removed

The information icon (or its padlock equivalent) are generated on the status bar using the `{fl}` code. Since the status bar is configurable via Preferences, it's possible this code can be removed - in which case the icon won't be visible any more. You can still use the format lock using the menu commands mentioned above.
