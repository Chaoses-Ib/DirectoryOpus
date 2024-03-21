# Toolbar

The **Toolbar** internal command can be used to:

- Open or close toolbars or toolbar sets
- Open or close a floating toolbar, control its appearance and position on screen
- Save a new set or modify the Default Toolbar Set
- Import a toolbar into your configuration
- Reset your toolbars to the defaults

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| APPBAR | /K | **left** | When opening a floating toolbar, specify this argument to dock the toolbar with the left edge of the screen. Combine with **POS** to control which monitor it docks on.<br /><br />*Example:* `Toolbar my_tools STATE=float APPBAR=left TOGGLE` |
|  |  | **top** | Docks the toolbar with the top of the screen.<br /><br />*Example:* `Toolbar my_tools STATE=floatactive APPBAR=top` |
|  |  | **right** | Docks the toolbar with the right of the screen.<br /><br />*Example:* `Toolbar my_tools FLOAT POS=1920,0 APPBAR=right` |
|  |  | **bottom** | Docks the toolbar with the bottom of the screen.<br /><br />*Example:* `Toolbar my_tools STATE=float APPBAR=bottom` |
|  |  | **off** | Undocks the toolbar if it is already docked.<br /><br />*Example:* `Toolbar my_tools FLOAT APPBAR=off POS=50,100` |
| AUTOCLOSE | /S | *(no value)* | Add this argument when opening a floating toolbar to make the toolbar close automatically after running a command. This lets you have a toolbar that can pop open (by key press for example), run a command and close automatically again, and saves having to add the `Toolbar NAME=*this CLOSE` command to all the buttons on the toolbar.<br /><br />*Example:* `Toolbar my_tools STATE=float AUTOCLOSE` |
| CLOSE | /O | *(no value)* | Closes the toolbar specified with the **NAME** argument. Note that **NAME** is the default argument for this command, the **NAME** keyword itself does not need to appear. The toolbar will be closed only in the current Lister unless **LOCAL=no** is also specified to close it globally.<br /><br />*Example:* `Toolbar Operations CLOSE` |
|  |  | **all** | Closes all toolbars in the current Lister.<br /><br />*Example:* `Toolbar CLOSE=all` |
| FLOAT | /O | *(no value)* | Opens the toolbar as a floating toolbar. This is the equivalent of specifying **STATE=float**. Using the various arguments provides more control over the floating toolbar. If combined with the **UPDATE** argument you can make changes to already-open toolbars.<br /><br />*Example:* `Toolbar my_tools FLOAT TOGGLE` |
|  |  | **default** | Opens the floating toolbar with the default appearance. If not specified (and no other arguments are specified), Opus will remember the toolbar's settings from the last time it was floated.<br /><br />*Example:* `Toolbar my_tools FLOAT=default` |
|  |  | **active** | Activates the newly opened toolbar (equivalent to **STATE=floatactive**).<br /><br />*Example:* `Toolbar my_tools FLOAT=active` |
|  |  | **vertical** | Lay the floating toolbar out vertically instead of horizontally.<br /><br />*Example:* `Toolbar my_tools FLOAT=vertical` |
|  |  | \*\*locked \*\* | Lock the floating toolbar from being resized or moved.<br /><br />*Example:* `Toolbar my_tools FLOAT=vertical,locked POS=100,100` |
|  |  | **autohide** | Set the floating toolbar to auto-hide when it is docked.<br /><br />*Example:* `Toolbar my_tools FLOAT=autohide APPBAR=bottom` |
|  |  | **roundededges** | Display the toolbar with rounded edges.<br /><br />*Example:* `Toolbar my_tools FLOAT=roundededges` |
|  |  | **grid** | Make all buttons in the floating toolbar the same size.<br /><br />*Example:* `Toolbar my_tools FLOAT=vertical,grid` |
|  |  | **frame** | Display the floating toolbar with a frame.<br /><br />*Example:* `Toolbar my_tools FLOAT=frame,roundededges` |
|  |  | **noframe** | Display the floating toolbar with no frame.<br /><br />*Example:* `Toolbar my_tools FLOAT=noframe TOGGLE` |
|  |  | **transparent** | Make the floating toolbar transparent.<br /><br />*Example:* `Toolbar my_tools FLOAT=noframe,transparent` |
|  |  | **taskbar** | Display the floating toolbar with the system taskbar theme.<br /><br />*Example:* `Toolbar my_tools FLOAT=taskbar,autohide` |
|  |  | **glass** | Display the floating toolbar using glass.<br /><br />*Example:* `Toolbar my_tools FLOAT=glass` |
|  |  | **topopus** | Set the floating toolbar to appear in top of other Opus windows.<br /><br />*Example:* `Toolbar my_tools FLOAT=topopus` |
|  |  | **toplevel** | Set the floating toolbar to appear on top of all other windows.<br /><br />*Example:* `Toolbar my_tools FLOAT=toplevel` |
|  |  | **hotkeys** | Enable hotkeys in the floating toolbar.<br /><br />*Example:* `Toolbar my_tools FLOAT=hotkeys` |
| HEADING | /O | *(no value)* | When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.<br /><br />When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.<br /><br />*Example:* `Toolbar LIST=sets HEADING` |
|  |  | *\<heading text\>* | You can specify the heading text if you want it to be different to the button's label.<br /><br />*Example:* `Toolbar LIST HEADING="Toolbars"` |
| IMPORT | /S | *(no value)* | Imports the toolbar specified with the **NAME** argument into your Opus configuration. For this command, **NAME** must specify the full path of the toolbar file to import. This would be most useful on the context menu for **.dop** (toolbar) files.<br /><br />*Example:* `Toolbar NAME {f} IMPORT` |
| LINE | /K | *\<line\>* | When opening a toolbar, specifies the toolbar line it is to appear on. The line number is given relative to the specified toolbar state. For example, when **STATE** is bottom, the line given is relative to the group of toolbars at the bottom of the Lister. *\<line\>* is counted from 0.<br /><br />*Example:* `Toolbar Operations LINE 1` |
|  |  | *\<line\>,\<position\>* | Specifies both the line and the position of the new toolbar. This lets you open a toolbar on the same line as an existing toolbar. *\<position\>* is given as the number of pixels from the left (or top, for vertical toolbars) edge of the Lister window.<br /><br />*Example:* `Toolbar Images LINE 1,500` |
| LIST | /O | *(no value)* | Displays a generated list of all your toolbars (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This lets you turn toolbars on or off from a drop-down menu.<br /><br />*Example:* `Toolbar LIST` |
|  |  | **sets** | Displays a list of [toolbar sets](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md) and lets you switch between them.<br /><br />*Example:* `Toolbar LIST=sets` |
|  |  | **add** | When a toolbar set is chosen from the generated list, it will be loaded in "add" mode - meaning the toolbars within it will be added to any currently open toolbars. This overrides the state of the option saved within the set itself.<br /><br />*Example:* `Toolbar LIST=sets,add` |
|  |  | **replace** | When a toolbar set is chosen from the generated list, it will be loaded in "replace" mode - meaning the toolbars within it will replace any currently open toolbars.<br /><br />*Example:* `Toolbar LIST=sets,replace` |
|  |  | **toggle** | When a toolbar set is chosen from the generated list, it will turn off any previously loaded set, but leave the default toolbars unaffected. Selecting the set again will turn it off.<br /><br />*Example:* `Toolbar LIST=sets,toggle` |
|  |  | **usekeys** | When a toolbar set is chosen from the generated list, Opus will check the state of the **Shift** and **Ctrl** keys to determine the behaviour. Holding the **Shift** key will select "add" mode, and the **Ctrl** key will select "replace" mode.<br /><br />*Example:* `Toolbar LIST=sets,usekeys` |
|  |  | **nocontext** | Prevents the toolbar sets in the generated list from appearing "checked" when Opus considers they are currently active.<br /><br />*Example:* `Toolbar LIST=sets,add,nocontext` |
| LOADSET | /O | *(no value)* | Loads the set specified by the NAME argument. The default behaviour specified in the set ("add", "replace" or "toggle") will be used unless overridden.<br /><br />*Example:* `Toolbar my_set LOADSET` |
|  |  | **add** | Adds the toolbars in the specified set to any currently open toolbars.<br /><br />*Example:* `Toolbar my_set LOADSET=add` |
|  |  | **replace** | Replaces any currently open toolbars with those in the specified set.<br /><br />*Example:* `Toolbar my_set LOADSET=replace` |
|  |  | **toggle** | Turns off any previously loaded set, but leaves the default toolbars unaffected. If the specified set is already open it will be closed (so running the command twice has the effect of toggling the set on and off).<br /><br />*Example:* `Toolbar my_set LOADSET=toggle` |
|  |  | **usekeys** | Uses the state of the **Shift** and **Ctrl** keys to determine the behaviour when loading the set. Holding the **Shift** key will select "add" mode, and the **Ctrl** key will select "replace" mode.<br /><br />*Example:* `Toolbar my_set LOADSET=usekeys` |
| LOCAL | /O | *(no value)* | Opens a toolbar local to the current Lister. Note that as this is the default behaviour, specifying **LOCAL** or **LOCAL=yes** has no effect.<br /><br />*Example:* `Toolbar Images LOCAL` |
|  |  | **no** | Opens the toolbar globally in all Listers.<br /><br />*Example:* `Toolbar Images LOCAL=no` |
| NAME |  | *\<toolbar name\>* | Specifies the name of the toolbar - used in conjunction with the other arguments to open or close the specified toolbar. This is the default argument for the **Toolbar** command and so the **NAME** keyword does not need to be used, although it is still a good idea to do so. If no other arguments to the command are provided, the named toolbar will be turned on.<br /><br />*Example:* `Toolbar NAME="Images"` |
|  |  | **\*this** | Makes the command apply to the current toolbar. When used from a toolbar button, the Toolbar command will apply to the toolbar the button is contained within.<br /><br />*Example:* `Toolbar NAME=\*this CLOSE` |
| POS | /K | *\<x\>,\<y\>* | Specifies the on-screen position when opening a floating toolbar. The position is given relative to the top-left corner of the primary display monitor. This can also be used to control which monitor a docked toolbar appears on (by combining it with the **APPBAR** argument).<br /><br />*Example:* `Toolbar Applications STATE=float POS 1200,80` |
|  |  | **mouse** | The floating toolbar will appear centered over the current position of the mouse pointer.<br /><br />*Example:* `Toolbar LauncherBar STATE=float POS=mouse` |
|  |  | **mousel** | The floating toolbar is left-aligned with the position of the mouse pointer.<br /><br />*Example:* `Toolbar Images STATE=float POS=mousel TOGGLE` |
|  |  | **mouser** | The floating toolbar is right-aligned with the mouse pointer.<br /><br />*Example:* `Toolbar Applications STATE=float POS=mouser` |
| RESETDEFAULTS | /K | *(no value)* | Resets the toolbars to the factory defaults. All existing toolbars will be closed, the default toolbars will be reset, and then only those toolbars will be opened.<br /><br />If you have made changes to the default toolbars those changes will be lost, but none of your other toolbars will be affected (other than being turned off if they were open when the command was run).<br /><br />*Example:* `Toolbar RESETDEFAULTS` |
|  |  | **fdb** | Resets the [Location Bar](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) toolbar to its defaults. Use this in conjunction with **nolister** to only reset the location bar.<br /><br />Note that if neither the **stateonly** nor **nolister** arguments are provided, then **fdb** is implied (i.e. `Toolbar RESETDEFAULTS` by itself resets the location bar toolbar as well as the main Lister toolbars).<br /><br />*Example:* `Toolbar RESETDEFAULTS=nolister,fdb` |
|  |  | **nolister** | By default all Lister toolbars are reset; use this in conjunction with **fdb** and **viewer** to only reset those toolbars.<br /><br />*Example:* `Toolbar RESETDEFAULTS=fdb,nolister,stateonly` |
|  |  | **stateonly** | Doesn't modify the toolbars themselves - instead, only the current set of toolbars is reset to the defaults. Any toolbars you have created yourself will be closed and the default set of toolbars displayed, but any modifications you have made to the default toolbars will be unaffected.<br /><br />*Example:* `Toolbar RESETDEFAULTS=stateonly` |
|  |  | **quiet** | Suppresses the confirmation prompt before resetting the toolbars.<br /><br />*Example:* `Toolbar RESETDEFAULTS=quiet` |
|  |  | **viewer** | Resets the [Image Viewer](/Manual/additional_functionality/viewing_images/README.md) toolbar to its defaults. Use this in conjunction with **nolister** to only reset the viewer toolbar.<br /><br />*Example:* `Toolbar RESETDEFAULTS=nolister,viewer` |
| SAVESET | /O | *(no value)* | Saves the current toolbars as a [toolbar set](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md). By default the new set will be set to "replace" mode. Opus will prompt for a name for the set unless you specify one with the **NAME** argument.<br /><br />*Example:* `Toolbar SAVESET` |
|  |  | **add** | Saves the toolbar set in "add" mode.<br /><br />*Example:* `Toolbar SAVESET=add` |
|  |  | **toggle** | Saves the toolbar set in "toggle" mode.<br /><br />*Example:* `Toolbar SAVESET=toggle` |
|  |  | **quiet** | Suppresses the confirmation prompt when saving over an existing toolbar set.<br /><br />*Example:* `Toolbar my_set SAVESET=toggle,quiet` |
| SETDEFAULT | /O | *(no value)* | Saves the toolbars in the current Lister as the Default Toolbar Set.<br /><br />*Example:* `Toolbar SETDEFAULT` |
|  |  | **quiet** | Suppresses the confirmation prompt before saving the set.<br /><br />*Example:* `Toolbar SETDEFAULT=quiet` |
| STATE | /K | **top** | Opens the specified toolbar at the top of the Lister. This is the default behaviour for this command.<br /><br />*Example:* `Toolbar Applications STATE=top` |
|  |  | **bottom** | Opens the toolbar at the bottom of the Lister. These toolbars appear at the very bottom of the window, underneath all other Lister elements.<br /><br />*Example:* `Toolbar Images STATE=bottom TOGGLE` |
|  |  | **fdbottom** | Opens the toolbar at the bottom of the file display(s). Similar to **bottom** but will not extend left under the leftmost folder tree.<br /><br />*Example:* `Toolbar Images STATE=fdbottom TOGGLE` |
|  |  | **left** | Opens the toolbar at the left of the Lister. These toolbars appear vertically at the very left edge of the window.<br /><br />*Example:* `Toolbar Drives STATE=left` |
|  |  | **right** | Opens the toolbar at the right of the Lister. These toolbars appear vertically at the very right edge of the window.<br /><br />*Example:* `Toolbar Drives STATE=right LINE=1 TOGGLE` |
|  |  | **center** | Opens the toolbar in the center of the Lister. These toolbars appear between the two file displays in a [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) Lister - they will be either horizontal or vertical depending on the file display arrangement.<br /><br />*Example:* `Toolbar Drives STATE=center TOGGLE` |
|  |  | **viewpane** | Opens the toolbar between the file displays and the viewer pane, when the viewer pane is at the right of the Lister. If the viewer pane is not open, or is at the bottom of the window, this value behaves the same as **right**.<br /><br />*Example:* `Toolbar Applications STATE=viewpane` |
|  |  | **tree** | Opens the toolbar between the left file display and the folder tree.<br /><br />*Example:* `Toolbar Drives STATE=tree` |
|  |  | **float** | Floats the toolbar. You can specify the position of the floating toolbar with the **POS** argument.<br /><br />*Example:* `Toolbar Applications STATE=float TOGGLE` |
|  |  | **floatactive** | Floats the toolbar and makes it active. This can be used to open a toolbar and have it take input focus so you can open its drop-down menus from the keyboard.<br /><br />*Example:* `Toolbar Tools STATE=floatactive POS=0,0` |
|  |  | **fdb** | Changes which toolbar is used for the [File Display border](/Manual/basic_concepts/the_lister/navigation/file_display_border.md).<br /><br />*Example:* `Toolbar my_fdb STATE=fdb` |
| TOGGLE | /S | *(no value)* | Toggles the toolbar specified with the **NAME** argument. If the toolbar is not currently opened it will be opened, otherwise it will be closed.<br /><br />*Example:* `Toolbar Operations TOGGLE LINE=1` |
| UPDATE | /S | *(no value)* | Updates an existing floating toolbar with new appearance and position values. If the toolbar is not currently opened it will be opened using the defined appearance.<br /><br />*Example:* `Toolbar my_tools FLOAT=glass POS=50,50 UPDATE` |

