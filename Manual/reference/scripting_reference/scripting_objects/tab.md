# Tab

The **Tab** object represents a folder tab in a Lister (even if the tab control isn't currently displayed, a Lister always has at least one open tab). You can obtain a collection of **Tab** objects from a **[Lister](lister.md)** object. **Tab** objects are also used with the **[Command](command.md)** and **[Func](func.md)** objects, and if a command results in new tabs being opened, the **[Results](results.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
all</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the files and folders currently displayed in this tab.

Note: The first time a script accesses this property (and all the other properties that return an **[Items](items.md)** object), a snapshot is taken of all the appropriate items. If the script then makes changes to those items (e.g. by creating a new file, modifying the selection, etc), these changes will not be reflected by the collection. To re-synchronize the collection call the **Update** method on the object.
</td></tr><tr><td>
backlist</td><td>

*collection:***[Path](path.md)**</td><td>

Returns a collection of **[Path](path.md)** objects that represents the paths in the "backward" history list for this tab (i.e. the folders you would get to by clicking the *Back* button).
</td></tr><tr><td>
color</td><td>

*string*</td><td>

Returns the tab's assigned color (if one has been assigned via, for example, the **Go TABCOLOR** command). The color is returned as a string in R,G,B format.
</td></tr><tr><td>
crumbpath</td><td>

*object:***[Path](path.md)**</td><td>
Returns the current path from the tab's breadcrumb control (if it has one), including any ghost path.
</td></tr><tr><td>
dest</td><td>

*bool*</td><td>

Returns **True** if this tab is currently the [destination](/Manual/basic_concepts/source_and_destination.md), and **False** otherwise.

Note that you cannot always assume a tab is the source if it is not the destination. Use the separate **source** property for that.
</td></tr><tr><td>
dirs</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the folders currently displayed in this tab.
</td></tr><tr><td>
dirty</td><td>

*bool*</td><td>

Returns **True** if the tab is marked as dirty, indicating its list of contents may be out of date. This can happen if the tab is in the background and the user has turned off the **Preferences / Folder Tabs / Options / Process file changes in background tabs** option.
</td></tr><tr><td>
displayed_label</td><td>

*string*</td><td>
Returns the currently displayed label of this tab.
</td></tr><tr><td>
filegroups</td><td>

*collection:***[FileGroup](filegroup.md)**</td><td>

Returns a collection of **[FileGroup](filegroup.md)** objects that represents all the file groups in the tab (when the tab is grouped). You can use the **format.group_by** property to test if the tab is grouped or not.
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the files currently displayed in this tab.
</td></tr><tr><td>
format</td><td>

*object:***[Format](format.md)**</td><td>

Returns a **[Format](format.md)** object representing the current folder format in this tab.
</td></tr><tr><td>
forwardlist</td><td>

*collection:***[Path](path.md)**</td><td>

Returns a collection of **[Path](path.md)** objects that represents the paths in the "forward" history list for this tab (i.e. the folders you would get to by clicking the *Forward* button).
</td></tr><tr><td>
hidden</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the files and folders currently hidden from this tab.
</td></tr><tr><td>
hidden_dirs</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the folders currently hidden from this tab.
</td></tr><tr><td>
hidden_files</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the files currently hidden from this tab
</td></tr><tr><td>
highlighted</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the files and folders currently displayed in this tab that have one or more cells [highlighted](/Manual/basic_concepts/selecting_files/selecting_cells.md).
</td></tr><tr><td>
label</td><td>

*string*</td><td>

Returns the current assigned tab label. Note that this may be an empty string if no custom label has been assigned. The **displayed_label** property returns the currently displayed label in all cases.
</td></tr><tr><td>
linktab</td><td>

*object:***Tab**</td><td>

If this tab is linked to another tab, returns a **Tab** object representing the linked tab. If this tab is not linked this property returns **0**.
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the parent Lister that owns this tab.
</td></tr><tr><td>
lock</td><td>

*string*</td><td>
Returns the current lock state of the tab; one of "off", "on", "changes", "reuse".
</td></tr><tr><td>
navlock</td><td>

*bool*</td><td>

Returns **True** if this tab is linked in Navigation Lock mode. This property does not exist if the tab is not linked, so make sure you check the value of **linktab** first.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>
Returns the current path shown in this tab.
</td></tr><tr><td>
quickfilter</td><td>

*object:***[QuickFilter](quickfilter.md)**</td><td>

Returns a **[QuickFilter](quickfilter.md)** object providing information about the state of the quick filter in this tab.
</td></tr><tr><td>
right</td><td>

*bool*</td><td>

Returns **True** if this tab is currently on the right or bottom side of a dual-display Lister, and **False** otherwise.
</td></tr><tr><td>
selected</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the selected files and folders currently displayed in this tab. Note that if [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) is turned on in the tab, this will be a collection of checked items rather than selected.
</td></tr><tr><td>
selected_dirs</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object that represents all the selected folders currently displayed in this tab.
</td></tr><tr><td>
selected_files</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** objects that represents all the selected files currently displayed in this tab
</td></tr><tr><td>
selstats</td><td>

*object:***[TabStats](tabstats.md)**</td><td>

Returns a **[TabStats](tabstats.md)** object that provides various information about the tab, including the number of files, number of selected files, total size of selected files, etc. The "selected" counts provided by this object take [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) into account (that is, if checkbox mode is currently turned on, the counts will be for checked files rather than for selected files).
</td></tr><tr><td>
source</td><td>

*bool*</td><td>

Returns **True** if this tab is currently the [source](/Manual/basic_concepts/source_and_destination.md), and **False** otherwise.

Note that you cannot always assume a tab is the destination if it is not the source. Use the separate **dest** property for that.
</td></tr><tr><td>
stats</td><td>

*object:***[TabStats](tabstats.md)**</td><td>

Returns a **[TabStats](tabstats.md)** object that provides various information about the tab, including the number of files, number of selected files, total size of selected files, etc. Unlike **selstats**, this object does not take [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) into account (so the "selected" counts will refer to selected rather than checked files).
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.md)**</td><td>

This **[Vars](vars.md)** object represents all defined variables with *tab scope* (that are scoped to this tab).
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

Returns **True** if this tab is currently visible (i.e. it is the active tab in either file display), and **False** otherwise.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
CloseFAYT</td><td>

*none*</td><td>

*none*</td><td>

Call this method from a [FAYT extension](/Manual/scripting/example_scripts/extending_the_fayt.md) script to forcibly close the FAYT field.
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.md)**</td><td>

Creates a new **[Dialog](dialog.md)** object, that lets you display dialogs and popup menus. The dialog's **window** property will be automatically assigned to this tab.
</td></tr><tr><td>
GetFocusItem</td><td>

*none*</td><td>

*object:***[Item](item.md)**</td><td>

Returns an **[Item](item.md)** object representing the file or folder which has focus in the tab.

The focus item is typically indicated by an outline around its name, and is usually the last item which was clicked on, or the last item which was moved to with the keyboard. The focus item is often also selected, but not always; focus and selection are two different things.

If no focus item exists, or if the focus item is a special file or folder, such as *This PC*, which cannot be represented by an **Item** object, then this method does not return an object. (In JScript, test if the result ***== null*** and in VBScript test if the result ***is nothing***.)
</td></tr><tr><td>
Notify</td><td>

\<string:type\>  
\<string:msg\>  
\[\<int:timeout\>\]</td><td>

*bool*</td><td>

Displays a notification message associated with this tab.

Currently the only defined type is "status", which displays the message in the status bar.

The *msg* string will be displayed in the status bar when the tab is active. The *timeout* value lets you specify an optional timeout (in milliseconds) after which the message will automatically be removed. If no timeout is specified the user needs to click the message to dismiss it.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

When a script accesses particular properties of a **Tab** object, a snapshot is taken of the tab's state. For example, if you ask for the **selected_files** property, the list of selected files is calculated and then stored in memory. This can speed things up, and also means you don't have to worry about the list changing under you as you work through it. If the script then makes changes to the tab (e.g. it selects files, creates a new folder, etc.), these changes will not be reflected by the cached snapshot(s) if you access the same properties on the same tab object again. To clear the cached snapshots and re-synchronize the object with the tab's current state, call the **Tab.Update** method.
</td></tr><tr><td>
UpdateFAYTSuggestions</td><td>

*array*  
or ***[vector](vector.md)**:string* or *object:***[map](map.md)**</td><td>

*none*</td><td>

When you're implementing a [FAYT extension](/Manual/scripting/example_scripts/extending_the_fayt.md) script, you can call this method at any time to update the list of suggestions shown to the user.

You can provide an array or **[vector](vector.md)** of strings, or a **[map](map.md)** of string/string pairs.

When providing a **[map](map.md)** each key represents the text that will be inserted if selected by the user, and the value represents a hint or description that's shown in a separate column in the suggestion list.

When providing an array or **[vector](vector.md)** of strings, you can provide the second column description by tab-separating it from the main value.
</td></tr></tbody>
</table>

