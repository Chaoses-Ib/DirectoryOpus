# View Modes



![](/Manual/images/media/13/view_mode_menu.png)

Files and folders in the file displays can be shown in a number of different view modes. You can change view mode using the drop-down **View** menu in the default toolbar.

The three buttons to the right of the **View** menu provide quick access to the most commonly used view modes:

- ![](/Manual/images/media/13/detailsbutton.png) **Details**
- ![](/Manual/images/media/13/thumbtailsbutton.png) **Details + Thumbnails**
- ![](/Manual/images/media/13/thumbnailsbutton.png) **Thumbnails**

You can use the [Folder Format](../folder_options/README.md) system to automatically apply a view mode to specific folders. For example, you could have Opus automatically display your pictures library in thumbnails mode.

In the modes that **don't** display any information besides the filename, you can hover over a file to view its info tip (tooltip). The info tip will often show you lots of pertinent information about a file, and you can configure exactly what's shown from the [File Types](/Manual/file_types/filetype_editor/info_tip.md) dialog.

##### Large icons

Displays the folder contents using large icons.

![](/Manual/images/media/13/view_mode_-_large_icons.png)

The "large" icon size is defined by Windows itself; this is normally 32 x 32 pixels (scaled for system DPI).

##### Small icons

Displays the folder contents using small icons.

![](/Manual/images/media/13/view_mode_-_small_icon.png)

The "small" icon size is defined by Windows; this is normally 16 x 16 pixels (scaled for system DPI).

##### List

Similar to Small Icons, this mode displays the folder contents with a small icon and label.

![](/Manual/images/media/13/view_mode_-_list.png)

This view mode is popular with many people as it displays the most files at once in each file display. The layout in this mode is different to almost all other modes - instead of icons running left-to-right and then top-to-bottom, the order is reversed - files are displayed in columns running down the file display, and the display scrolls horizontally rather than vertically.

##### Details

Displays the folder contents as a table, with rows for each file and columns for information about each file.

![](/Manual/images/media/13/view_mode_-_details_001.png)

This mode can display additional columns of information for each file besides the filename. You can choose which columns are displayed using the **[Folder Format](../folder_options/README.md)** system. See the **[File Display Modes / Details Mode](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)** Preferences page for a description of the settings that can be configured for Details mode. You can also configure things like grid lines to visibly separate items in the list.

When in Details mode you can hold the <kbd>Ctrl</kbd> key down and turn the mouse wheel to increase or decrease the font size used to display the folder contents.

##### Details+Thumbnails

This is not strictly a view mode in its own right - instead, this is standard **Details** mode with the **Thumbnail** column added.

![](/Manual/images/media/13/detailsthumbnails.png)

The width of the column determines the size of the thumbnail - you can set the default column width using the **Default width** option on the [File Display Columns / Appearance](/Manual/preferences/preferences_categories/file_display_columns/appearance.md) Preferences page. You can position the *Thumbnail* column anywhere you like, but if it appears immediately adjacent to the *Name* column Opus will treat the two as a single column as far as selection and highlighting is concerned (as shown in the image above).

The **[File Display Modes / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)** and **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)** Preferences pages both have options that let you configure the *Thumbnail* column's aspect ratio (it defaults to 16:9), whether thumbnails in the column have a border displayed, and whether the file icon should be automatically hidden whenever the *Thumbnail* column is visible.

##### Power

This is very similar to Details mode (it looks identical), except the behaviour of the list when [interacting with it using the mouse and keyboard](../selecting_files/selecting_with_the_mouse_and_keyboard/README.md) can be configured to a far greater extent.

By default Power mode uses persistent selection - unlike the other view modes, files are not deselected automatically when you click an empty space in the file display. See the **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)** and\*\* [Power Mode / Buttons](/Manual/preferences/preferences_categories/file_display_modes/power_mode/buttons.md)\*\* Preferences pages for a full description of the Power Mode configuration options.

When in Power mode you can hold the <kbd>Ctrl</kbd> key down and turn the mouse wheel to increase or decrease the font size used to display the folder contents.

##### Thumbnails

This mode displays thumbnails for files and folders, which is particularly useful for image or video files.

![](/Manual/images/media/13/view_mode_-_thumbs.png)

Opus can generate thumbnails for many different file formats; files that a thumbnail can not be generated for will be displayed with the usual icon for that file type. As well as the file name, this mode can optionally display the file size and (for image file formats) the dimensions of the image below each thumbnail. You can configure the size and appearance of thumbnails from the **[File Display Modes / Thumbnails Mode](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.md)** Preferences page.

By default Opus will display a special toolbar - the [Images Toolbar](toolbars/the_default_toolbars/images_toolbar.md) - whenever the file display is set to thumbnails mode. This contains several commands for manipulating images, as well as a slider for adjusting thumbnail size. You can also increase or decrease the thumbnail size by holding the <kbd>Ctrl</kbd> key down and turning the mouse wheel.

##### Tiles

This mode combines large icons (or optionally thumbnails) with the ability of Details mode to display information besides the filename.

![](/Manual/images/media/13/view_mode_-_tiles.png)

You can choose what information is shown for each file type through the [File Types](/Manual/file_types/filetype_editor/tiles_mode.md) system. Also see the **[File Display Modes / Tiles Mode](/Manual/preferences/preferences_categories/file_display_modes/tiles_mode.md)** Preferences page for settings that can be configured for Tiles mode.
