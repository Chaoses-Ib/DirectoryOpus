# Lister

The **Lister** object represents an open [Lister](/Manual/basic_concepts/the_lister/README.md) window. A collection of currently open Lister objects is available from the **[DOpus](dopus.md).listers** property, and if a command results in a new Lister being opened, the **[Results](results.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
activetab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the currently active (source) tab.
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>
Lister window bottom-edge coordinate.
</td></tr><tr><td>
custom_title</td><td>

*string*</td><td>

Returns the custom title of the Lister (if any) as set by the **Set LISTERTITLE** command. This may be an empty string. The *title* property returns the actual window title.
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
Returns the ID of the virtual desktop this Lister is on.
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the current destination tab (in a dual-display Lister).
</td></tr><tr><td>
dual</td><td>

*int*</td><td>

Indicates whether the Lister is in [dual-display mode](/Manual/basic_concepts/the_lister/dual_display/README.md) or not. Possible values are:

|     |                                 |
|-----|---------------------------------|
| 0   | single-display mode             |
| 1   | dual-display, vertical layout   |
| 2   | dual-display, horizontal layout |
</td></tr><tr><td>
dualsize</td><td>

*int*</td><td>

Returns the current split percentage of the dual displays (e.g. **50** indicates they are evenly sized).
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

Returns **True** if this Lister is currently the foreground (active) window.
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

Returns **True** if this Lister is currently the active Lister (foreground window), or was the most recently active Lister.
</td></tr><tr><td>
layout</td><td>

*string*</td><td>

Provides the name of the [Lister layout](/Manual/basic_concepts/the_lister/layouts/README.md) that this Lister came from (if any).
</td></tr><tr><td>
left</td><td>

*int*</td><td>
Lister window left-edge coordinate.
</td></tr><tr><td>
metapane</td><td>

*int*</td><td>

Indicates whether the [metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md) is currently open or not. Possible values are:

|     |                                          |
|-----|------------------------------------------|
| 0   | metadata pane is not open                |
| 1   | metadata pane is open, vertical layout   |
| 2   | metadata pane is open, horizontal layout |
</td></tr><tr><td>
right</td><td>

*int*</td><td>
Lister window right-edge coordinate.
</td></tr><tr><td>
state</td><td>

*string*</td><td>

Returns the state of a single-display mode Lister:

|     |             |
|-----|-------------|
| 0   | off         |
| 1   | source      |
| 2   | destination |
| 4   | locked      |
</td></tr><tr><td>
style</td><td>

*string*</td><td>

Returns the name of the [Lister style](/Manual/basic_concepts/the_lister/styles.md) which was last applied to the Lister, or an empty string if there is none. This is just the last style which was loaded and does not mean the Lister still looks the same; the user may have opened or closed panels and made other changes via other methods in the time since the style was applied.
</td></tr><tr><td>
tabs</td><td>

*collection:***[Tab](tab.md)**</td><td>

Returns a collection of **[Tab](tab.md)** objects that represent all tabs in this Lister. In a dual-display Lister this includes tabs in both the left and right file displays.
</td></tr><tr><td>
tabgroupleft</td><td>

*string*</td><td>
Returns the name of the Folder Tab Group which was last loaded into the left half of the Lister, or an empty string if no group has been loaded.

The name only changes when a Folder Tab Group is loaded. The current tabs may no longer resemble the named tab group if the user has made changes since the group was loaded. The name persists across restarts, through the Default Lister and saved Layouts.
</td></tr><tr><td>
tabgroupright</td><td>

*string*</td><td>

Similar to **tabgroupleft**, above, but for the right half of the Lister (if any).
</td></tr><tr><td>
tabsleft</td><td>

*collection:***[Tab](tab.md)**</td><td>

Returns a collection of **[Tab](tab.md)** objects that represent the tabs in the left/top side of a dual-display Lister. In a single-display Lister this is equivalent to all the tabs in the Lister.
</td></tr><tr><td>
tabsright</td><td>

*collection:***[Tab](tab.md)**</td><td>

Returns a collection of **[Tab](tab.md)** objects that represent the tabs in the right/bottom side of a dual-display Lister. In a single-display Lister this will return an empty collection.
</td></tr><tr><td>
title</td><td>

*string*</td><td>
Returns the current title of the Lister window.
</td></tr><tr><td>
toolbars</td><td>

*collection:***[Toolbar](../../command_reference/internal_commands/toolbar.md)**</td><td>

Returns a collection of **[Toolbar](../../command_reference/internal_commands/toolbar.md)** objects representing all currently open toolbars in this Lister.

The collection is obtained directly each time the script asks for it, and is not a snapshot, so you don't need to call **Update** for it to reflect changes.
</td></tr><tr><td>
top</td><td>

*int*</td><td>
Lister window top-edge coordinate;
</td></tr><tr><td>
tree</td><td>

*int*</td><td>

Indicates whether or not the [folder tree](/Manual/basic_concepts/the_lister/navigation/folder_tree.md) is currently open. Possible values are:

|     |                                                      |
|-----|------------------------------------------------------|
| 0   | folder tree is not open                              |
| 1   | a single tree is open, at the left of the Lister     |
| 2   | a single tree is open, at the right of the Lister    |
| 3   | two folder trees are open (in a dual-display Lister) |
</td></tr><tr><td>
utilpage</td><td>

*string*</td><td>

If the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) is currently open, returns a string indicating the currently selected utility page. Possible values are **find** (which means the Find panel's Simple version), **findadvanced**, **sync**, **dupe**, **undo**, **filelog**, **ftplog**, **otherlog**, **email**.
</td></tr><tr><td>
utilpane</td><td>

*int*</td><td>

Indicates whether or not the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) is currently open. Possible values are:

|     |                           |
|-----|---------------------------|
| 0   | utility panel is not open |
| 1   | utility panel is open     |
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.md)**</td><td>

This **[Vars](vars.md)** object represents all defined variables with *Lister scope* (that are scoped to this Lister).
</td></tr><tr><td>
viewpane</td><td>

*int*</td><td>

Indicates whether or not the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md) is currently open. Possible values are:

|     |                                        |
|-----|----------------------------------------|
| 0   | viewer pane is not open                |
| 1   | viewer pane is open, vertical layout   |
| 2   | viewer pane is open, horizontal layout |
</td></tr><tr><td>
viewpanefile</td><td>

*object:***[Path](path.md)**</td><td>

Returns the path of the file currently displayed by the lister's viewer pane. The path will be an empty string if there is no file currenly displayed.

The path is obtained directly each time the script asks for it, and is not a snapshot, so you don't need to call **Update** for it to reflect changes.
</td></tr><tr><td>
windowstate</td><td>

*string*</td><td>

Returns the current visibility state of the Lister window. Possible values are:

|            |                                  |
|------------|----------------------------------|
| **min**    | the Lister is minimized          |
| **max**    | the Lister is maximized          |
| **hidden** | the Lister is hidden             |
| **normal** | the Lister is displayed normally |
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.md)**</td><td>

Creates a new **[Dialog](dialog.md)** object, that lets you display dialogs and popup menus. The dialog's **window** property will be automatically assigned to this Lister.
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*none*</td><td>

*bool*</td><td>

Returns **True** if the Lister is on the current virtual desktop.
</td></tr><tr><td>
MoveToDesktop</td><td>
\<string:desktop\></td><td>

*bool*</td><td>

Moves the Lister window to the specified virtual desktop. Returns **True** if successful.
</td></tr><tr><td>
SetTaskbarGroup</td><td>
\<string:group\></td><td>

*bool*</td><td>

Used to change how the Lister window is grouped with other Opus windows on the taskbar. Specify a group name to move the window into an alternative group, or omit the group argument to reset back to the default group. If one or more windows are moved into the same group, they will be grouped together, separate from other the default group.

This only works when taskbar grouping is enabled. Group names are limited to 103 characters and will be truncated if longer. Spaces and dots in group names are automatically converted to underscores. Returns **True** on success.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

The first time a script accesses a particular **Lister** object, a snapshot is taken of the Lister state. If the script then makes changes to that Lister (e.g. it opens a new tab, or moves the window), these changes will not be reflected by the object (unless otherwise mentioned). To re-synchronize the object with the Lister, call the **Lister.Update** method.
</td></tr></tbody>
</table>

