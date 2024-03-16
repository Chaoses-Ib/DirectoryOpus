# Toolbars

These options affect the [location bar](/Manual/basic_concepts/the_lister/navigation/file_display_border.md) - the toolbar or title bar that is displayed above the file displays in the Lister.

The main choice to make on this page is whether you want the location bar displayed as a toolbar, or displayed as a static header (to mimic versions of Opus prior to 11).

##### Display as a toolbar

This option is on by default, and enables the use of one or more toolbars at the top of each file display. The factory toolbar used for this is [File Display](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.md), but you can use the lists to select your own toolbars.

The list on the left displays your available toolbars, and the list on the right shows those that have been selected for use in the location bar.

##### Display as a static header

This option disables the file display toolbar, and instead displays a static header that displays the current folder path and several small navigation and control buttons. While the displayed path has some functionality (e.g. you can click individual segments similar to the [breadcrumbs location field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md)), it is nowhere near as flexible as a toolbar.

- **Allow docking of Listers**: Lets you drag one single display Lister over the title bar of another to dock them together (the Lister you dragged is closed, the Lister you docked it with is changed to dual display mode, and the folder tabs it was showing are opened in the new display). You can also split a dual display Lister into two single displays by dragging from the [location bar](/Manual/basic_concepts/the_lister/navigation/file_display_border.md).
- **Clickable path components in headerborder**: You can click individual path segments in the border to browse to the current folder's parent locations.
- **Header's Up button does "Up + Back"**: When turned on, clicking the **Up** button behaves as if the `Go UP BACK` command was used (e.g. if the parent folder is in the path history, Opus goes "back" to it, preserving file selections and calculated folder sizes).
- **Show header even in single display mode**: The location bar has to be displayed in dual mode (to indicate [which side is the source and which is the destination](/Manual/basic_concepts/source_and_destination.md)), but you can turn it off in single display mode to save space.
