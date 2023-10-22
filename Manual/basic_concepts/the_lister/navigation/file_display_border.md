# Location Bar

The File Display border is a title bar that appears at the top of the file display area in the Lister. By default the File Display border contains a toolbar, the [File Display](../toolbars/the_default_toolbars/file_display_toolbar.md) toolbar:

![](/Manual/images/media/file_display_toolbar.png)

The first three buttons on the default File Display toolbar are, from left-to-right, **Back** (![](/Manual/images/media/location_toolbar_-_back.png)), **Forward** (![](/Manual/images/media/forward.png)) and **Up** (![](/Manual/images/media/location_toolbar_-_up.png)). All of these buttons have an associated drop-down menu which you can access either by clicking-and-holding with the left mouse button, or single-clicking with the right mouse button. The Favorites button (![](/Manual/images/media/favorites_001.png)) provides access to your [favorite folders](favorites.md), and the [breadcrumbs location field](breadcrumbs_location_field.md) shows you the current folder.

This is a fully [configurable toolbar](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/RAEDME.md), and as such you can add your own buttons and modify or remove the default ones. See the page on the [File Display toolbar](../toolbars/the_default_toolbars/file_display_toolbar.md) for more information about these buttons.

The color of the file display border (and of the Opus icon, if enabled) indicates the state of the file display. A single display Lister can be one of three states - the default colors for these are shown below, but you can configure them through the **[Display / Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md)**Preferences page. These colors apply whether the File Display toolbar is enabled or not.

\* ![](/Manual/images/media/fdbsource.png) **Source** (for actions involving two folders, like copy, this will be the source of the operation). \* ![](/Manual/images/media/fdbdest.png) **Destination** (for actions involving two folders, this will be the destination of the operation). \* ![](/Manual/images/media/fdboff.png) **Off** (this Lister will not be involved in file operations with another window in this state).

In a dual display Lister, one display is always designated the source and the other the destination, so the file display border will never appear in the off state in a dual Lister. See the **[Source and Destination](../../source_and_destination.md)** topic for more information about the source/destination concept.

In **[Preferences / File Displays / Border](/Manual/preferences/preferences_categories/file_displays/file_display_border.md)** you can choose to turn the File Display toolbar off, in which case the file display border reverts to a simpler, static header:

![](/Manual/images/media/fdb1.png)

In static header mode, in a single file display Lister the file display border is optional - you can choose whether it is shown or not using the **Show file display border in single display mode** option on the **[File Displays / Border](/Manual/preferences/preferences_categories/file_displays/file_display_border.md)** page in Preferences. In a dual file display Lister the file display border is always shown.

This image is typical of the file display border in a single display Lister. The various elements of the single display border are:

- ![](/Manual/images/media/fdbicon.png): The Opus icon can be used to create a shortcut to this folder - simply drag the icon out and drop it on the desktop or in a Lister to make a shortcut to the current folder.
- ![](/Manual/images/media/fdbpath2.png): The current location is displayed here. See below for more information about the location string.
- ![](/Manual/images/media/fdbback.png): Go [back](up_forwards_back.md) to the previous folder in the [history](recent_and_history_lists.md).
- ![](/Manual/images/media/fdbfwd.png): Go [forward](up_forwards_back.md) to the next folder in the [history](recent_and_history_lists.md).
- ![](/Manual/images/media/fdbup.png): Go [up](up_forwards_back.md) to the parent folder.
- ![](/Manual/images/media/fdbcopy.png): Display this folder in the other file display. In a single display Lister, this will automatically place the Lister in [dual display mode](../dual_display/RAEDME.md).

The file display borders in a dual display Lister have a few more buttons than a single display.

![](/Manual/images/media/fdbdual.png) 

The additional buttons are:

- ![](/Manual/images/media/fdbswap.png): Swap the two file displays (their positions are exchanged).
- ![](/Manual/images/media/fdblayout.png): Change layout from side-by-side (vertical) to one-above-the-other (horizontal) and back again.
- ![](/Manual/images/media/fdbclose.png): Close the file display - closing one will leave the remaining one behind as a single display Lister.

If you move your mouse over the location string displayed in the file display border you'll notice that the individual path components are actually links. The file display border operations like a simple version of the "breadcrumbs" location field - you can left-click on any component of the path to navigate to that folder, and you can right-click to access its folder context menu.

![](/Manual/images/media/fdbhot.png) 

By default *hot paths* are only enabled when the file display is the source, and the Lister containing the file display is the active window. This is so you can click on a file display border to make it the source without worrying about accidentally clicking a link. You can change this behaviour with the options in the **[File Displays / Border](/Manual/preferences/preferences_categories/file_displays/file_display_border.md)** page in Preferences.
