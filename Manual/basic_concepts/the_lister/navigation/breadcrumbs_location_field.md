# Path Field

The "breadcrumbs" path field displays the current folder location as a "trail of crumbs".

![](/Manual/images/media/13/crumbs1.png) 

Each component of the path is represented as a separate "crumb". Each crumb is actually a button and you can use them for navigation - taking the above screenshot as an example, to navigate to the **Program Files** folder you can simply click on it with the left mouse button. You can also right-click the crumb buttons to display the context menu for that level of the path, and drag and drop files to the buttons to copy or move files higher up the path.

### Breadcrumb menus

The arrow glyphs following each crumb are also buttons; clicking these displays a pop-up menu showing the contents of that folder.

![](/Manual/images/media/13/crumbs_menu1.png) 

Again, you can use these pop-up menus for navigation, and you can drag and drop files to the menu items to copy or move files to that location.

### Ghost breadcrumbs

When you navigate up the folder tree the branches of your previous deepest location are shown as "ghost" crumbs.

![](/Manual/images/media/13/breadcrumbs_ghosts.png)

These can be very handy both as a visual reminder of the location you last visited as well as letting you jump back and forth between higher and lower folders in the same hierarchy.

If you navigate to a sibling of an ancestor path, and the new folder has the same descendant hierarchy as the original ancestor, the ghost path is also preserved. This lets you jump very quickly to the same relative spot in a folder tree - for example, moving from the sub-folders of one user's profile directory to another.

### Current folder menu

The icon at the far left of the field represents the current folder. You can drag and drop this icon to the desktop or another Lister to create a shortcut to the folder. The pop-up menu for this icon (accessed from its arrow button) is different to the others:

![](/Manual/images/media/13/crumbs_menu_2.png)

Rather than showing the contents of the current folder, it contains links to various special folders on the desktop as well as the disk drives in the system.

### Overflow menu

The current folder menu also acts as an "overflow" menu if the breadcrumbs field is not wide enough to display the full path.

In these situations, the breadcrumbs field itself displays as many levels of the path as will fit, starting from the lowest level, and any higher levels that don't fit are displayed in the pop-up menu. Note that ghost crumbs are never displayed in the overflow menu.

### Manual path editing

You can use the breadcrumbs field to edit the path manually. If you click in an area of the field that doesn't contain a button, the crumbs will disappear and be replaced by a traditional edit control, where you can manually type in a path to navigate to.

When the edit control is active, pressing the <kbd>F5</kbd> key will deactivate it instead open the current folder drop-down menu. This is most useful when you have activated the breadcrumbs field by pressing its hotkey - for example, the default breadcrumbs field has <kbd>F4</kbd> assigned as the hotkey, meaning you can press <kbd>F4</kbd> followed by <kbd>F5</kbd> as a quick way to open the menu.

### Recent list

Clicking the drop-down arrow button at the far right of the breadcrumbs control displays a drop-down list of [recently](recent_and_history_lists.md) visited folders.

### Configuration

You can configure the appearance and behavior of the breadcrumbs field from the [Location Bar / Path Fields](/Manual/preferences/preferences_categories/location_bar/path_fields/README.md) Preferences section.

It can also be configured via the [toolbar customization](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md) system.
