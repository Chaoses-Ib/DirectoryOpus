# Location Bar

The location bar is a title bar that appears at the top of the file display area in the Lister. By default the location bar contains a toolbar, the [File Display](../toolbars/the_default_toolbars/file_display_toolbar.md) toolbar:

![](/Manual/images/media/13/file_display_toolbar.png)

### Default location bar toolbar

The main component of the default toolbar is the [breadcrumbs location field](breadcrumbs_location_field.md) which shows you the current folder and lets you navigate within the current hierarchy.

To the left of the location field the buttons are:

- ![](/Manual/images/media/13/location_toolbar_-_back.png) **Back**: Go [back](up_forwards_back.md) to the previous folder. Right-click to show a drop-down list of previous folders.
- ![](/Manual/images/media/13/location_toolbar_-_forward.png) **Forward**: Go [forward](up_forwards_back.md) to the next folder (if you've previously gone back). Right-click to show a drop-down list of next folders.
- ![](/Manual/images/media/13/location_toolbar_-_up.png) **Up**: Go [up](up_forwards_back.md) in the folder hierarchy. Right-click to show a drop-down menu with several different options.
- ![](/Manual/images/media/13/location_toolbar_-_refresh.png) **Refresh**: Refresh the current folder (both file display and tree are refreshed by default).
- ![](/Manual/images/media/13/location_toolbar_-_home.png) **Home**: Go to your [home folder](home_folder.md). Right-click to show a drop-down menu.

To the right of the location field the buttons are:

- **Duplicate**: Duplicates this folder display in the other file display. The Lister will be switched to dual-display mode if it isn't already.
- **Swap**: Swap this folder with the other file display. This button isn't visible in single display mode.
- **Close**: Close the current tab. If this is the only tab in a dual-display Lister, it will close the second file display. In a single display Lister with only one tab open this button isn't visible.

This is a fully [configurable toolbar](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.md), and as such you can add your own buttons and modify or remove the default ones. See the page on the [File Display toolbar](../toolbars/the_default_toolbars/file_display_toolbar.md) for more information about these buttons.

### Source / destination state

Some operations, like copying files, inherently require two folders to be involved - the source and the destination.

In a dual display Lister, one display is always designated the source and the other the destination. The location bar changes color to indicate this.

Single display Listers by default do not have a source/destination state as such, although you can enable this in Preferences if you prefer to work that way.

See the **[Source and Destination](../../source_and_destination.md)** topic for more information about the source/destination concept.

### Static header mode

In **[Location Bar / Toolbars](/Manual/preferences/preferences_categories/location_bar/toolbars.md)** you can choose to turn the File Display toolbar off, in which case the location bar reverts to a simpler, static header:

![](/Manual/images/media/13/fdb1.png)

In static header mode, in a single file display Lister the location bar is optional - you can choose whether it is shown or not using the **Show header in single display mode** option. In a dual file display Lister the location bar is always shown.

The elements of the static header, from left-to-right, are:

- **Location**: Shows the current location. The individual segments of the location are clickable links.
- **Back**: Go [back](up_forwards_back.md) to the previous folder.
- **Forward**: Go [forward](up_forwards_back.md) to the next folder (if you've previously gone back).
- **Up**: Go [up](up_forwards_back.md) in the folder hierarchy.
- **Duplicate**: Duplicates this folder display in the other file display.
- **Swap**: Swap this folder with the other file display.
- **Close**: Close the current tab.
