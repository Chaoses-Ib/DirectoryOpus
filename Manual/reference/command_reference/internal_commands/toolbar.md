# Toolbar

The **Toolbar** internal command can be used to:

- Open or close toolbars or toolbar sets
- Open or close a floating toolbar, control its appearance and position on screen
- Save a new set or modify the Default Toolbar Set
- Import a toolbar into your configuration
- Reset your toolbars to the defaults

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
APPBAR</td><td>
/K</td><td>

**left**</td><td>

When opening a floating toolbar, specify this argument to dock the toolbar with the left edge of the screen. Combine with **POS** to control which monitor it docks on.

*Example:* `Toolbar my_tools STATE=float APPBAR=left TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**top**</td><td>

Docks the toolbar with the top of the screen.

*Example:* `Toolbar my_tools STATE=floatactive APPBAR=top`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Docks the toolbar with the right of the screen.

*Example:* `Toolbar my_tools FLOAT POS=1920,0 APPBAR=right`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

Docks the toolbar with the bottom of the screen.

*Example:* `Toolbar my_tools STATE=float APPBAR=bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Undocks the toolbar if it is already docked.

*Example:* `Toolbar my_tools FLOAT APPBAR=off POS=50,100`
</td></tr><tr><td>
AUTOCLOSE</td><td>
/S</td><td>

*(no value)*</td><td>

Add this argument when opening a floating toolbar to make the toolbar close automatically after running a command. This lets you have a toolbar that can pop open (by key press for example), run a command and close automatically again, and saves having to add the `Toolbar NAME=*this CLOSE` command to all the buttons on the toolbar.

*Example:* `Toolbar my_tools STATE=float AUTOCLOSE`
</td></tr><tr><td>
CLOSE</td><td>
/O</td><td>

*(no value)*</td><td>

Closes the toolbar specified with the **NAME** argument. Note that **NAME** is the default argument for this command, the **NAME** keyword itself does not need to appear. The toolbar will be closed only in the current Lister unless **LOCAL=no** is also specified to close it globally.

*Example:* `Toolbar Operations CLOSE`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Closes all toolbars in the current Lister.

*Example:* `Toolbar CLOSE=all`
</td></tr><tr><td>
FLOAT</td><td>
/O</td><td>

*(no value)*</td><td>

Opens the toolbar as a floating toolbar. This is the equivalent of specifying **STATE=float**. Using the various arguments provides more control over the floating toolbar. If combined with the **UPDATE** argument you can make changes to already-open toolbars.

*Example:* `Toolbar my_tools FLOAT TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**default**</td><td>

Opens the floating toolbar with the default appearance. If not specified (and no other arguments are specified), Opus will remember the toolbar's settings from the last time it was floated.

*Example:* `Toolbar my_tools FLOAT=default`
</td></tr><tr><td>
</td><td>
</td><td>

**active**</td><td>

Activates the newly opened toolbar (equivalent to **STATE=floatactive**).

*Example:* `Toolbar my_tools FLOAT=active`
</td></tr><tr><td>
</td><td>
</td><td>

**vertical**</td><td>

Lay the floating toolbar out vertically instead of horizontally.

*Example:* `Toolbar my_tools FLOAT=vertical`
</td></tr><tr><td>
</td><td>
</td><td>

\*\*locked \*\*</td><td>

Lock the floating toolbar from being resized or moved.

*Example:* `Toolbar my_tools FLOAT=vertical,locked POS=100,100`
</td></tr><tr><td>
</td><td>
</td><td>

**autohide**</td><td>

Set the floating toolbar to auto-hide when it is docked.

*Example:* `Toolbar my_tools FLOAT=autohide APPBAR=bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**roundededges**</td><td>

Display the toolbar with rounded edges.

*Example:* `Toolbar my_tools FLOAT=roundededges`
</td></tr><tr><td>
</td><td>
</td><td>

**grid**</td><td>

Make all buttons in the floating toolbar the same size.

*Example:* `Toolbar my_tools FLOAT=vertical,grid`
</td></tr><tr><td>
</td><td>
</td><td>

**frame**</td><td>

Display the floating toolbar with a frame.

*Example:* `Toolbar my_tools FLOAT=frame,roundededges`
</td></tr><tr><td>
</td><td>
</td><td>

**noframe**</td><td>

Display the floating toolbar with no frame.

*Example:* `Toolbar my_tools FLOAT=noframe TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**transparent**</td><td>

Make the floating toolbar transparent.

*Example:* `Toolbar my_tools FLOAT=noframe,transparent`
</td></tr><tr><td>
</td><td>
</td><td>

**taskbar**</td><td>

Display the floating toolbar with the system taskbar theme.

*Example:* `Toolbar my_tools FLOAT=taskbar,autohide`
</td></tr><tr><td>
</td><td>
</td><td>

**glass**</td><td>

Display the floating toolbar using glass.

*Example:* `Toolbar my_tools FLOAT=glass`
</td></tr><tr><td>
</td><td>
</td><td>

**topopus**</td><td>

Set the floating toolbar to appear in top of other Opus windows.

*Example:* `Toolbar my_tools FLOAT=topopus`
</td></tr><tr><td>
</td><td>
</td><td>

**toplevel**</td><td>

Set the floating toolbar to appear on top of all other windows.

*Example:* `Toolbar my_tools FLOAT=toplevel`
</td></tr><tr><td>
</td><td>
</td><td>

**hotkeys**</td><td>

Enable hotkeys in the floating toolbar.

*Example:* `Toolbar my_tools FLOAT=hotkeys`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Toolbar LIST=sets HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Toolbar LIST HEADING="Toolbars"`
</td></tr><tr><td>
IMPORT</td><td>
/S</td><td>

*(no value)*</td><td>

Imports the toolbar specified with the **NAME** argument into your Opus configuration. For this command, **NAME** must specify the full path of the toolbar file to import. This would be most useful on the context menu for **.dop** (toolbar) files.

*Example:* `Toolbar NAME {f} IMPORT`
</td></tr><tr><td>
LINE</td><td>
/K</td><td>

*\<line\>*</td><td>

When opening a toolbar, specifies the toolbar line it is to appear on. The line number is given relative to the specified toolbar state. For example, when **STATE** is bottom, the line given is relative to the group of toolbars at the bottom of the Lister. *\<line\>* is counted from 0.

*Example:* `Toolbar Operations LINE 1`
</td></tr><tr><td>
</td><td>
</td><td>

*\<line\>,\<position\>*</td><td>

Specifies both the line and the position of the new toolbar. This lets you open a toolbar on the same line as an existing toolbar. *\<position\>* is given as the number of pixels from the left (or top, for vertical toolbars) edge of the Lister window.

*Example:* `Toolbar Images LINE 1,500`
</td></tr><tr><td>
LIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a generated list of all your toolbars (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This lets you turn toolbars on or off from a drop-down menu.

*Example:* `Toolbar LIST`
</td></tr><tr><td>
</td><td>
</td><td>

**sets**</td><td>

Displays a list of [toolbar sets](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md) and lets you switch between them.

*Example:* `Toolbar LIST=sets`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

When a toolbar set is chosen from the generated list, it will be loaded in "add" mode - meaning the toolbars within it will be added to any currently open toolbars. This overrides the state of the option saved within the set itself.

*Example:* `Toolbar LIST=sets,add`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

When a toolbar set is chosen from the generated list, it will be loaded in "replace" mode - meaning the toolbars within it will replace any currently open toolbars.

*Example:* `Toolbar LIST=sets,replace`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

When a toolbar set is chosen from the generated list, it will turn off any previously loaded set, but leave the default toolbars unaffected. Selecting the set again will turn it off.

*Example:* `Toolbar LIST=sets,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**usekeys**</td><td>

When a toolbar set is chosen from the generated list, Opus will check the state of the **Shift** and **Ctrl** keys to determine the behaviour. Holding the **Shift** key will select "add" mode, and the **Ctrl** key will select "replace" mode.

*Example:* `Toolbar LIST=sets,usekeys`
</td></tr><tr><td>
</td><td>
</td><td>

**nocontext**</td><td>

Prevents the toolbar sets in the generated list from appearing "checked" when Opus considers they are currently active.

*Example:* `Toolbar LIST=sets,add,nocontext`
</td></tr><tr><td>
LOADSET</td><td>
/O</td><td>

*(no value)*</td><td>

Loads the set specified by the NAME argument. The default behaviour specified in the set ("add", "replace" or "toggle") will be used unless overridden.

*Example:* `Toolbar my_set LOADSET`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

Adds the toolbars in the specified set to any currently open toolbars.

*Example:* `Toolbar my_set LOADSET=add`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

Replaces any currently open toolbars with those in the specified set.

*Example:* `Toolbar my_set LOADSET=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Turns off any previously loaded set, but leaves the default toolbars unaffected. If the specified set is already open it will be closed (so running the command twice has the effect of toggling the set on and off).

*Example:* `Toolbar my_set LOADSET=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**usekeys**</td><td>

Uses the state of the **Shift** and **Ctrl** keys to determine the behaviour when loading the set. Holding the **Shift** key will select "add" mode, and the **Ctrl** key will select "replace" mode.

*Example:* `Toolbar my_set LOADSET=usekeys`
</td></tr><tr><td>
LOCAL</td><td>
/O</td><td>

*(no value)*</td><td>

Opens a toolbar local to the current Lister. Note that as this is the default behaviour, specifying **LOCAL** or **LOCAL=yes** has no effect.

*Example:* `Toolbar Images LOCAL`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Opens the toolbar globally in all Listers.

*Example:* `Toolbar Images LOCAL=no`
</td></tr><tr><td>
NAME</td><td>
</td><td>

*\<toolbar name\>*</td><td>

Specifies the name of the toolbar - used in conjunction with the other arguments to open or close the specified toolbar. This is the default argument for the **Toolbar** command and so the **NAME** keyword does not need to be used, although it is still a good idea to do so. If no other arguments to the command are provided, the named toolbar will be turned on.

*Example:* `Toolbar NAME="Images"`
</td></tr><tr><td>
</td><td>
</td><td>

**\*this**</td><td>

Makes the command apply to the current toolbar. When used from a toolbar button, the Toolbar command will apply to the toolbar the button is contained within.

*Example:* `Toolbar NAME=\*this CLOSE`
</td></tr><tr><td>
POS</td><td>
/K</td><td>

*\<x\>,\<y\>*</td><td>

Specifies the on-screen position when opening a floating toolbar. The position is given relative to the top-left corner of the primary display monitor. This can also be used to control which monitor a docked toolbar appears on (by combining it with the **APPBAR** argument).

*Example:* `Toolbar Applications STATE=float POS 1200,80`
</td></tr><tr><td>
</td><td>
</td><td>

**mouse**</td><td>

The floating toolbar will appear centered over the current position of the mouse pointer.

*Example:* `Toolbar LauncherBar STATE=float POS=mouse`
</td></tr><tr><td>
</td><td>
</td><td>

**mousel**</td><td>

The floating toolbar is left-aligned with the position of the mouse pointer.

*Example:* `Toolbar Images STATE=float POS=mousel TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**mouser**</td><td>

The floating toolbar is right-aligned with the mouse pointer.

*Example:* `Toolbar Applications STATE=float POS=mouser`
</td></tr><tr><td>
RESETDEFAULTS</td><td>
/K</td><td>

*(no value)*</td><td>

Resets the toolbars to the factory defaults. All existing toolbars will be closed, the default toolbars will be reset, and then only those toolbars will be opened.

If you have made changes to the default toolbars those changes will be lost, but none of your other toolbars will be affected (other than being turned off if they were open when the command was run).

*Example:* `Toolbar RESETDEFAULTS`
</td></tr><tr><td>
</td><td>
</td><td>

**fdb**</td><td>

Resets the [Location Bar](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) toolbar to its defaults. Use this in conjunction with **nolister** to only reset the location bar.

Note that if neither the **stateonly** nor **nolister** arguments are provided, then **fdb** is implied (i.e. `Toolbar RESETDEFAULTS` by itself resets the location bar toolbar as well as the main Lister toolbars).

*Example:* `Toolbar RESETDEFAULTS=nolister,fdb`
</td></tr><tr><td>
</td><td>
</td><td>

**nolister**</td><td>

By default all Lister toolbars are reset; use this in conjunction with **fdb** and **viewer** to only reset those toolbars.

*Example:* `Toolbar RESETDEFAULTS=fdb,nolister,stateonly`
</td></tr><tr><td>
</td><td>
</td><td>

**stateonly**</td><td>

Doesn't modify the toolbars themselves - instead, only the current set of toolbars is reset to the defaults. Any toolbars you have created yourself will be closed and the default set of toolbars displayed, but any modifications you have made to the default toolbars will be unaffected.

*Example:* `Toolbar RESETDEFAULTS=stateonly`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Suppresses the confirmation prompt before resetting the toolbars.

*Example:* `Toolbar RESETDEFAULTS=quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**viewer**</td><td>

Resets the [Image Viewer](/Manual/additional_functionality/viewing_images/README.md) toolbar to its defaults. Use this in conjunction with **nolister** to only reset the viewer toolbar.

*Example:* `Toolbar RESETDEFAULTS=nolister,viewer`
</td></tr><tr><td>
SAVESET</td><td>
/O</td><td>

*(no value)*</td><td>

Saves the current toolbars as a [toolbar set](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md). By default the new set will be set to "replace" mode. Opus will prompt for a name for the set unless you specify one with the **NAME** argument.

*Example:* `Toolbar SAVESET`
</td></tr><tr><td>
</td><td>
</td><td>

**add**</td><td>

Saves the toolbar set in "add" mode.

*Example:* `Toolbar SAVESET=add`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Saves the toolbar set in "toggle" mode.

*Example:* `Toolbar SAVESET=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Suppresses the confirmation prompt when saving over an existing toolbar set.

*Example:* `Toolbar my_set SAVESET=toggle,quiet`
</td></tr><tr><td>
SETDEFAULT</td><td>
/O</td><td>

*(no value)*</td><td>

Saves the toolbars in the current Lister as the Default Toolbar Set.

*Example:* `Toolbar SETDEFAULT`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Suppresses the confirmation prompt before saving the set.

*Example:* `Toolbar SETDEFAULT=quiet`
</td></tr><tr><td>
STATE</td><td>
/K</td><td>

**top**</td><td>

Opens the specified toolbar at the top of the Lister. This is the default behaviour for this command.

*Example:* `Toolbar Applications STATE=top`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

Opens the toolbar at the bottom of the Lister. These toolbars appear at the very bottom of the window, underneath all other Lister elements.

*Example:* `Toolbar Images STATE=bottom TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**fdbottom**</td><td>

Opens the toolbar at the bottom of the file display(s). Similar to **bottom** but will not extend left under the leftmost folder tree.

*Example:* `Toolbar Images STATE=fdbottom TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Opens the toolbar at the left of the Lister. These toolbars appear vertically at the very left edge of the window.

*Example:* `Toolbar Drives STATE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Opens the toolbar at the right of the Lister. These toolbars appear vertically at the very right edge of the window.

*Example:* `Toolbar Drives STATE=right LINE=1 TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

Opens the toolbar in the center of the Lister. These toolbars appear between the two file displays in a [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) Lister - they will be either horizontal or vertical depending on the file display arrangement.

*Example:* `Toolbar Drives STATE=center TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

Opens the toolbar between the file displays and the viewer pane, when the viewer pane is at the right of the Lister. If the viewer pane is not open, or is at the bottom of the window, this value behaves the same as **right**.

*Example:* `Toolbar Applications STATE=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

Opens the toolbar between the left file display and the folder tree.

*Example:* `Toolbar Drives STATE=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**float**</td><td>

Floats the toolbar. You can specify the position of the floating toolbar with the **POS** argument.

*Example:* `Toolbar Applications STATE=float TOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**floatactive**</td><td>

Floats the toolbar and makes it active. This can be used to open a toolbar and have it take input focus so you can open its drop-down menus from the keyboard.

*Example:* `Toolbar Tools STATE=floatactive POS=0,0`
</td></tr><tr><td>
</td><td>
</td><td>

**fdb**</td><td>

Changes which toolbar is used for the [File Display border](/Manual/basic_concepts/the_lister/navigation/file_display_border.md).

*Example:* `Toolbar my_fdb STATE=fdb`
</td></tr><tr><td>
TOGGLE</td><td>
/S</td><td>

*(no value)*</td><td>

Toggles the toolbar specified with the **NAME** argument. If the toolbar is not currently opened it will be opened, otherwise it will be closed.

*Example:* `Toolbar Operations TOGGLE LINE=1`
</td></tr><tr><td>
UPDATE</td><td>
/S</td><td>

*(no value)*</td><td>

Updates an existing floating toolbar with new appearance and position values. If the toolbar is not currently opened it will be opened using the defined appearance.

*Example:* `Toolbar my_tools FLOAT=glass POS=50,50 UPDATE`
</td></tr></tbody>
</table>

