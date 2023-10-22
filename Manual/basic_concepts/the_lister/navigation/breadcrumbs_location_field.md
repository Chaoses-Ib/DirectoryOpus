# Path Field

The "breadcrumbs" location field displays the current folder location as a "trail of crumbs".

![](/Manual/images/media/crumbs1.png) 

Each component of the path is represented as a separate "crumb". Each crumb is actually a button and you can use them for navigation - taking the above screenshot as an example, to navigate to the **Program Files** folder you can simply click on it with the left mouse button. You can also right-click the crumb buttons to display the context menu for that level of the path, and drag and drop files to the buttons to copy or move files higher up the path.

The  ![](/Manual/images/media/crumb_arrow.png) glyphs following each crumb are also buttons; clicking these displays a pop-up menu showing the contents of that folder.

![](/Manual/images/media/crumbs_menu1.png) 

Again, you can use these pop-up menus for navigation, and you can drag and drop files to the menu items to copy or move files to that location.

When you navigate up the folder tree the branches of your previous deepest location are shown as "ghost" crumbs.

![](/Manual/images/media/breadcrumbs_ghosts.png)

These can be very handy both as a visual reminder of the location you last visited as well as letting you jump back and forth between higher and lower folders in the same hierarchy. In the above screenshot we have navigated from the *Projects* folder back up the tree to the *Bill* folder.

Additionally, if you navigate to a sibling of an ancestor path, and the new folder has the same descendant hierarchy as the original ancestor, the ghost path is also preserved.

![](/Manual/images/media/breadcrumbs_sibling_ancestor.png)

This lets you jump very quickly to the same relative spot in a folder tree - for example, moving from the sub-folders of one user's profile directory to another. In this screenshot we are about to navigate to the *Ben* folder, a sibling of the ancestor folder *Bill*.

![](/Manual/images/media/breadcrumbs_sibling_ghost.png)

The result is that the previous deeper path remains as a ghost - clicking the *Projects* crumb will return you instantly to the same folder in the new hierarchy.

The icon at the far left of the field represents the current folder. You can drag and drop this icon to the desktop or another Lister to create a shortcut to the folder. The pop-up menu for this icon (accessed from its ![](/Manual/images/media/crumb_arrow.png) button) is different to the others:

![](/Manual/images/media/crumbs_menu_2.png)

Rather than showing the contents of the current folder, it contains links to various special folders on the desktop as well as the disk drives in the system. This menu also acts as an "overflow" menu if the breadcrumbs field is not wide enough to display the full path.

![](/Manual/images/media/crumbsmenu3.png) 

In these situations, the breadcrumbs field itself displays as many levels of the path as will fit, starting from the lowest level, and any higher levels that don't fit are displayed in the pop-up menu. Note that ghost crumbs are never displayed in the overflow menu.

You can also use the breadcrumbs field to edit the path manually. If you click in an area of the field that doesn't contain a button:

![](/Manual/images/media/crumbs2.png) 

The crumbs will disappear and be replaced by a traditional edit control, where you can manually type in a path to navigate to. In this mode, pressing the **F5** key will deactivate the edit control and instead open the *Desktop* branch drop-down menu. This is most useful when you have activated the breadcrumbs field by pressing its hotkey - for example, the default breadcrumbs field has **F4** assigned as the hotkey, meaning you can press **F4** followed by **F5** as a quick way to open the *Desktop* branch.

![](/Manual/images/media/crumbs3.png) 

Finally, clicking the arrow button at the right-hand edge of the breadcrumbs control displays a drop-down list of [recently](recent_and_history_lists.md) visited folders:

![](/Manual/images/media/crumbs_recent.png)

In a dual-display Lister, the breadcrumbs field displays the location of the current source file display. As you switch the two displays between [source and destination](../../source_and_destination.md) the breadcrumbs field will update to show the current source location. Similarly, navigation actions you make using the breadcrumbs field only affect the source file display.

You can [configure the appearance and behavior](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/breadcrumbs_configuration.md) of the breadcrumbs field by editing the [field button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/RAEDME.md) that generates it.
