# Identifying the current format

As you may have gathered, the folder formats system is rather complex - we find it's one of the things new Opus users are often most confused by. The display format can change automatically, sometimes seemingly at random, and it can be quite possible to have no idea why a particular format is being used.

A feature is provided to try to help with this problem. If you hover the mouse over the ![](/Manual/images/media/13/info.png) icon in the status bar, the tooltip that appears for will show a description of how and why the current display format came about.

![](/Manual/images/media/13/format_explain.png) 

In the above example we can see that the current format in this file display started as an [auto-remembered format](auto_folder_formats.md), but was then modified by a command that turned on a column (in this case, the user right-clicked the column header and added the *Created* column).

##### Additional information

The info tooltip also shows where the Lister came from (in this case a system layout called **Last Closed Listers** - i.e. it was open when Opus was shutdown previously). If applicable it can also show where the background image came from (if the [Folder Images](/Manual/preferences/preferences_categories/folders/folder_images.md) system is in use).

##### Format commands via info icon right-click menu

<img src="/media/13/status_info_menu.png" class="align-right" data-query="?nolink" />Right-click the status bar info icon to show its context menu. This gives you access to various folder format-related commands.

The first three commands are:

- **Format Lock**: [Locks](locking_the_format.md) the format to prevent automatic changes.
- **Folder Format**: Displays the [Folder Format dialog](folder_options_dialog/README.md).
- **Manage Folder Formats**: Takes you to the [Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md) page in Preferences.

The next group of commands list the different [content type formats](content_types.md). Select one of these commands to instantly switch to that format.

The next group of commands lets you reset the format in various ways:

- **Reset to folder's format**: The format that the folder would have if you loaded it into a fresh tab.
- **Reset to folder-type format**: The default format for this type of folder (rather than this specific one).
- **Reset to "User Default" format**: The editable "User Default" format.
- **Reset to factory default format**: The non-editable factory default format.

At the bottom, the **Edit Status Bar** command takes you to the [File Displays / Status Bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md) Preferences page, where the status bar definition can be configured.

##### The status bar icon can be removed

The ![](/Manual/images/media/13/info.png) icon is generated on the status bar using the `{fl}` code. Since the status bar is configurable via Preferences, it's possible this code can be removed - in which case the icon won't be visible. In that case, you can add it back from the [File Displays / Status Bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md) Preferences page.
