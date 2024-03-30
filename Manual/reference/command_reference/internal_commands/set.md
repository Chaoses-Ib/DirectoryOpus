# Set

The **Set** internal command can be used to:

- Turn the various Lister elements ([folder tree](/Manual/basic_concepts/the_lister/navigation/folder_tree.md), [metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md), [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md), [dual display](/Manual/basic_concepts/the_lister/dual_display/README.md), etc) on or off in the current Lister
- Add or remove information columns from the current file display
- Turn [Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md), [Flatview Mode](/Manual/basic_concepts/flat_view.md) and [Navigation Lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) on or off
- Make changes to [filtering](/Manual/basic_concepts/searching_and_filtering/README.md), [sorting](/Manual/basic_concepts/sorting_and_grouping/README.md), [grouping](/Manual/basic_concepts/sorting_and_grouping/README.md) and [view mode](/Manual/basic_concepts/the_lister/view_modes.md) settings
- Turn [Administrator mode](/Manual/file_operations/uac_and_administrator_mode.md) on or off
- Enable or disable the Copy and Delete [recursive filters](/Manual/file_operations/filtered_operations/README.md)
- Enable or disable full-row selection and grid lines
- Adjust the size and position of the current Lister window
- ... and lots of other things :)

You can combine multiple **Set** command arguments on the one command line to make multiple changes to the Lister at once. For example, \<nobr\>`Set DUAL=on TREE=off`\</nobr\> would turn dual-display mode on, and the folder trees off, in one operation.

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ADMIN</td><td>
/K</td><td>

**on**</td><td>

Turns [Administrator mode](/Manual/file_operations/uac_and_administrator_mode.md) in in the active Lister. Opus will prompt you for the timeout, after which Administrator mode is automatically deactivated. This function has no effect on Windows XP, or if UAC is disabled.

*Example:* `Set ADMIN=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns Administrator mode off in the active Lister.

*Example:* `Set ADMIN=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles Administrator mode on or off.

*Example:* `Set ADMIN=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

*\<timeout\>*</td><td>

Specify a timeout (in minutes) to suppress the timeout dialog from appearing.

*Example:* `Set ADMIN=toggle,10`

If you specify 0 (zero), the timeout is disabled and Administrator mode will stay on in the Lister until the button is pushed again or the window is closed.

*Example:* `Set ADMIN=toggle,0`
</td></tr><tr><td>
AUTOSIZE</td><td>
/K</td><td>

**on**</td><td>

Turns on the *Auto-size all columns in Details and Power modes* Folder Format option in the current file display. This overrides all column widths so they behave as "auto" until the option is turned off again. Note that any configured maximum column widths still apply.

*Example:* `Set AUTOSIZE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the *Auto-size all columns in Details and Power modes* option off.

*Example:* `Set AUTOSIZE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the *Auto-size all columns in Details and Power modes* option on or off in the current file display.

*Example:* `Set AUTOSIZE=toggle`
</td></tr><tr><td>
AUTOSIZECOLUMNS</td><td>
/O</td><td>

*(no value)*</td><td>

Automatically resizes all columns in the source file display (applies to details and power modes only). This is a one-off width change based on the current column contents, as opposed to setting the columns into autosize mode like the **AUTOSIZE** argument would do. Another difference is that this will not override columns with maximum widths set, nor ones set to *Collapse*, and so on.

*Example:* `Set AUTOSIZECOLUMNS`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Automatically resizes all columns in the destination file display.

*Example:* `Set AUTOSIZECOLUMNS=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Resizes all columns in the left (or top) file display of a dual display Lister.

*Example:* `Set AUTOSIZECOLUMNS=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Resizes all columns in the right (or bottom) file display.

*Example:* `Set AUTOSIZECOLUMNS=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Resizes all columns in both file displays of a dual display Lister (or the sole display of a single display Lister).

*Example:* `Set AUTOSIZECOLUMNS=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Resizes all columns in the file display that currently has input focus. (This is almost always the same as the source file display.)

*Example:* `Set AUTOSIZECOLUMNS=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**widest**</td><td>

Resizes the columns on both sides of a dual display Lister, setting the columns on both sides to the same width (the widest of the two).

*Example:* `Set AUTOSIZECOLUMNS=widest`
</td></tr><tr><td>
BLURFILENAMES</td><td>
/K</td><td>

**on**</td><td>

Turns on blurring of filenames in the source Lister. You might want to do this in order to use an external screenshot tool to take a screenshot while hiding potentially sensitive information.

*Example:* `Set BLURFILENAMES=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns filename blurring off in the source Lister.

*Example:* `Set BLURFILENAMES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles filename blurring on or off.

*Example:* `Set BLURFILENAMES=toggle`
</td></tr><tr><td>
CALCFOLDERSIZES</td><td>
/K</td><td>

**all**</td><td>

Turns on the Preferences option to calculate folder sizes automatically (for all folders). Note that this simply modifies the Preferences setting - any currently open Listers won't calculate their folder sizes until they are refreshed.

*Example:* `Set CALCFOLDERSIZES=all`
</td></tr><tr><td>
</td><td>
</td><td>

**local**</td><td>

Turns on the option to calculate folder sizes automatically for all local drives.

*Example:* `Set CALCFOLDERSIZES=local`
</td></tr><tr><td>
</td><td>
</td><td>

**fixed**</td><td>

Turns on the option for all fixed local drives.

*Example:* `Set CALCFOLDERSIZES=fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns automatic folder size calculation off.

*Example:* `Set CALCFOLDERSIZES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**selected**</td><td>

Turns on the option to calculate folder sizes in selected folders only. The list of folders is configured via the [Folder Sizes](/Manual/preferences/preferences_categories/folders/folder_sizes/README.md) Preferences page.

*Example:* `Set CALCFOLDERSIZES=selected,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles calculation on or off for the specified folder type.

*Example:* `Set CALCFOLDERSIZES=local,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**skipjunctions**</td><td>

Specify this flag as well to turn on the *Skip junctions and softlinks* option.

*Example:* `Set CALCFOLDERSIZES=local,toggle,skipjunctions`
</td></tr><tr><td>
CHECKBOXMODE</td><td>
/K</td><td>

**on**</td><td>

Turns [Checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) on in the source file display.

*Example:* `Set CHECKBOXMODE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns Checkbox mode off in the source file display.

*Example:* `Set CHECKBOXMODE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles Checkbox mode on or off.

*Example:* `Set CHECKBOXMODE=toggle`
</td></tr><tr><td>
CLEARFILTERS</td><td>
/S</td><td>

*(no value)*</td><td>

Clears all file and folder filters in the current source file display. The filters that are cleared are those controlled by the **HIDEFILTERFILENAME**, **HIDEFILTERFOLDERS**, **SHOWFILTERFILENAME** and **SHOWFILTERFOLDERS** arguments.

*Example:* `Set CLEARFILTERS`
</td></tr><tr><td>
CLEARSYNC</td><td>
/S</td><td>

*(no value)*</td><td>

Once you've used the **Find SYNC** and **Copy SYNC** commands to automate the [synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) operation, you can use `Set CLEARSYNC` to exit synchronize mode and return the Lister to normal.

//<Example://> See the `Find SYNC` [command](find.md#SYNC) for an example.
</td></tr><tr><td>
COLUMNS</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

Changes which columns are displayed in the current source file display. You can specify one or more comma-separated [column keywords](../../metadata_keywords/keywords_for_columns.md) - the columns will be displayed in the order specified. Note that the **Name** column must always be present and will be added automatically if you don't specify it.

*Example:* `Set COLUMNS name,sizeauto,desc,attr`
</td></tr><tr><td>
</td><td>
</td><td>

*\<format\>*</td><td>

Applies the columns from named favorite folder format to the current source file display. The format must have been previously created through the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** Preferences page. Note that if the name of your favorite format conflicts with the name of an actual column, the column name will "win".

*Example:* `Set COLUMNS "Photo Viewing"`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

Applies the columns from the Folder Type format applicable to the source file display's path. For example, if the current path is a network drive, the columns from the **Network Drives** format would be applied.

*Example:* `Set COLUMNS=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!factory**</td><td>

Applies the columns from the hardcoded factory-default folder format to the current source file display.

*Example:* `Set COLUMNS !factory`
</td></tr><tr><td>
</td><td>
</td><td>

**!folder**</td><td>

Finds and applies the columns by using the same rules as when the folder was initially loaded. This generally gives you the columns you would get if the current directory was loaded into a new window. See the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** Preferences page for a description of the rules applied when Opus chooses a folder format for a path.

*Example:* `Set COLUMNS !folder`
</td></tr><tr><td>
</td><td>
</td><td>

**!user**</td><td>

Applies the columns from the **User default** folder format to the current source file display.

*Example:* `Set COLUMNS !user`
</td></tr><tr><td>
COLUMNSADD</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

Adds the specified columns to the current source file display. Can also be used to move or resize existing columns. You can specify one or more comma-separated [column keywords](../../metadata_keywords/keywords_for_columns.md).

Each column name can optionally be followed by the position to insert the column, and the width to make the new column. The format of this is as follows:

<table>
<tbody>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;</em><strong>)</strong></td>
<td>Specify the position of the column. This can be a number where <strong>0</strong> represents the left-most column, <strong>1</strong> the second column and so on. It can also be specified relative to another column's current position - see below for more information.</td>
</tr>
<tr class="even">
<td><strong>(</strong><em>&lt;pos&gt;</em><strong>,<br />
</strong><em>&lt;size&gt;</em><strong>)</strong></td>
<td>Specify both the position and size. The <em>&lt;size&gt;</em> argument indicates the width of the new column. This can be a number in pixels, <strong>a</strong> for <em>Auto</em>, <strong>f</strong> for <em>Fill</em>, <strong>e</strong> for <em>Expand</em> and <strong>c</strong> for <em>Collapse</em></td>
</tr>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;</em><strong>)</strong></td>
<td>Specify position, size and maximum width. The <em>&lt;max&gt;</em> argument lets you specify the maximum width for automatically-sized columns. This can be a number in pixels, or <strong>f</strong> for <em>Fill</em>.</td>
</tr>
<tr class="even">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;,<br />
&lt;min&gt;</em><strong>)</strong></td>
<td>Specify position, size, maximum and minimum width. The <em>&lt;min&gt;</em> argument lets you specify the minimum width for automatically-sized columns. This should be a number in pixels.</td>
</tr>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;,<br />
&lt;min&gt;,<br />
</em><strong>z)</strong></td>
<td>Specify position, size, maximum width, minimum width, and freeze the columns at this point. This column and those that come before it remain left-aligned and do not scroll - any subsequent columns scroll beneath the frozen ones.</td>
</tr>
</tbody>
</table>

The *\<pos\>* argument can also be specified relative to another column's current position. For example:

- **0+Name** places the new column where the *Name* column was, pushing *Name* and everything after it one place to the right.
- **1+Name** places it directly on the right of *Name*.
- **2+Name** places it two to the right of *Name*.
- **1-Name** places it two to the left of *Name* (i.e. in the position of the column that was one to the left of *Name*). You can also set *\<pos\>* to **!** to leave it unchanged, or prefix it with **!** to say it should be unchanged if the column is already present, but use the position specified after the **!** if it is being added.

To specify any arguments other than *\<pos\>*, those that precede it must be included. If you don't want to provide a value for one of the prior arguments, use \* instead. For example, if you want to specify size 80 but without specifying a position, you could use **(\*, 80)**.

The *\<size\>*, *\<max\>* and *\<min\>* values of existing columns can also be changed by specifying a **!** for *\<pos\>*.

Within the **Lister Column Header** **[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)**, you can use several special values for the position:

|                    |                                                                                                                                                                                                                            |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **%header%**       | Turns into the ID of the column which was right-clicked. Typically used to remove the column which was right-clicked.                                                                                                      |
| **%headerinsert%** | Turns into the position nearest where you right-clicked. Typically used to insert a column nearest where you right-clicked. If the position is not specified, the column will be added to the end of the existing columns. |

*Example:* `Set COLUMNSADD picwidth`  
*Example:* `Set COLUMNSADD desc(2),author(\*,\*)`  
*Example:* `Set COLUMNSADD picwidth(\*,a)`  
*Example:* `Set COLUMNSADD=Status(!1+Name)`
</td></tr><tr><td>
COLUMNSFREEZE</td><td>
/K</td><td>

*\<columns\>*</td><td>

Sets the number of frozen columns in the current source display. Frozen columns remain left-aligned and do not scroll - any subsequent columns scroll beneath the frozen ones.

This command acts as a toggle - if the specified number of columns are already frozen, they will be unfrozen.

*Example:* `Set COLUMNSFREEZE=3` // - freeze the first three columns //
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off frozen columns in the current source display.

*Example:* `Set COLUMNSFREEZE=off`
</td></tr><tr><td>
COLUMNSREMOVE</td><td>
/O</td><td>

*\<column\>, ...*</td><td>

Removes the specified columns from the current source display. You can specify one or more comma-separated [column keywords](../../metadata_keywords/keywords_for_columns.md).

*Example:* `Set COLUMNSREMOVE=mp3bitrate,mp3samplerate`

Within the **Lister Column Header** **[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)**, you can use **%header%** to refer to the column which was right-clicked.

*Example:* `Set COLUMNSREMOVE=%header%`
</td></tr><tr><td>
COLUMNSTOGGLE</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

Toggles the specified columns on or off in the current source display. The position and size of added columns can be given as for **COLUMNSADD**.

You can specify one or more comma-separated [column keywords](../../metadata_keywords/keywords_for_columns.md). If more than one column name is provided, the named columns will only be turned off if **all** specified columns are currently present. Otherwise, those columns not currently present will be added.

*Example:* `Set COLUMNSTOGGLE=desc(2),author`  
*Example:* `Set COLUMNSTOGGLE=Status(1+Name)`

(See the **COLUMNSADD** argument, above, for detail on how to specify positions if the examples are not clear.)

Within the **Lister Column Header** **[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)** only:

- You can use **%headerinsert%** for the position to insert columns nearest where you right-clicked instead of at the end.

*Example:* `Set COLUMNSTOGGLE=picwidth(%headerinsert%)`
</td></tr><tr><td>
</td><td>
</td><td>

**any**</td><td>

Makes the command consider similar columns to be the same with regard to toggling.

For example, there are several columns which display file sizes in different units. If *Size (Bytes)* is the only size column in use, and **any** is not used, then a command to toggle the *Size (KB)* column will result in both size columns on at once. Adding **any** would instead turn off the *Size (Bytes)* column in that situation and not turn anything on the first time. If the command was then run a second time, with no size column present, then it would add the *Size (KB)* column.

*Example:* `Set COLUMNSTOGGLE=any,sizekb`
</td></tr><tr><td>
</td><td>
</td><td>

**columnlist**</td><td>

Specify the **columnlist** keyword to have Opus automatically generate a list of columns which can be toggled.

The list will appear as a several sub-menus, one for each column category (*Name and Path*, *Date and Time*, *Picture Metadata*, etc.). This is similar to the list in the default **Lister Column Header** **[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)**.

*Example:* `Set COLUMNSTOGGLE=columnlist`

The **columnlist** keyword is only supported by the **COLUMNSTOGGLE** argument; the similar **COLUMNSADD** and **COLUMNSREMOVE** arguments can't use it, but are unlikely to need it.
</td></tr><tr><td>
</td><td>
</td><td>

**insert**</td><td>

The **insert** keyword, when combined with the **columnlist** keyword and used in the **Lister Column Header** **[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)**, causes Opus to insert new columns in the position nearest where the you right-clicked the header. Without it, new columns will be added to the end.

*Example:* `Set COLUMNSTOGGLE=columnlist,insert`

The **insert** keyword does not work without the **columnlist** keyword or when used outside the **Lister Column Header** menu. To do something similar in a command which toggles one specific column, use **%headerinsert%** for the position, as documented above.
</td></tr><tr><td>
CONFIRM</td><td>
/S</td><td>

*(no value)*</td><td>

Used to show a confirmation message specific to the command being run, often with a link to the Preferences setting for making the change permanent. This is only supported by certain commands, and not something you'd generally use when creating your own buttons. It is used on the default toolbars to help people understand when something only affects the current window or tab, and how make the same change globally instead.

*Example:* `Set EXPANDABLEFOLDERS=Toggle CONFIRM`
</td></tr><tr><td>
CONTENTFORMAT</td><td>
/K</td><td>

*\<content group\>*</td><td>

Sets the current source file display to use the named [content type](/Manual/basic_concepts/folder_options/content_types.md) folder format.

*Example:* `Set CONTENTFORMAT Images`
</td></tr><tr><td>
COPYFILTER</td><td>
/K</td><td>

**on**</td><td>

Turns on the recursive [copy filter](/Manual/file_operations/filtered_operations/README.md) for the active Lister.

*Example:* `Set COPYFILTER=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the copy filter in the active Lister.

*Example:* `Set COPYFILTER=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the copy filter on or off in the active Lister.

*Example:* `Set COPYFILTER=toggle`
</td></tr><tr><td>
DARKMODE</td><td>
/K</td><td>

**on**</td><td>

Forces dark mode on for Opus, regardless of current Windows setting.

*Example:* `Set DARKMODE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Forces dark mode off for Opus, regardless of current Windows setting.

*Example:* `Set DARKMODE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

If dark mode is currently active, forces it off; otherwise, forces dark mode on.

*Example:* `Set DARKMODE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**togglesmart**</td><td>

Toggles dark mode, acting like **reset** if the new mode is the same as the Windows setting, and **toggle** if it is the opposite.

*Example:* `Set DARKMODE=togglesmart`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets dark mode within Opus to use and track the Windows setting.

*Example:* `Set DARKMODE=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**noreset**</td><td>

Prevents the button being highlighted as "active" if Opus is set to use the Windows setting, even if the Windows setting matches the mode the command would activate.

*Example:* `Set DARKMODE=on,noreset`
</td></tr><tr><td>
DELFILTER</td><td>
/K</td><td>

**on**</td><td>

Turns on the recursive [delete filter](/Manual/file_operations/filtered_operations/README.md) for the active Lister.

*Example:* `Set DELFILTER=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the delete filter in the active Lister.

*Example:* `Set DELFILTER=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the delete filter on or off in the active Lister.

*Example:* `Set DELFILTER=toggle`
</td></tr><tr><td>
DELRECYCLEBIN</td><td>
/K</td><td>

**on**</td><td>

Turns on the *Delete to Recycle Bin where possible* option on the [Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md) Preferences page.

*Example:* `Set DELRECYCLEBIN=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the *Delete to Recycle Bin where possible* option.

*Example:* `Set DELRECYCLEBIN=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the *Delete to Recycle Bin where possible* option on and off.

*Example:* `Set DELRECYCLEBIN=toggle`
</td></tr><tr><td>
DELRECYCLECONFIRM</td><td>
/K</td><td>

**on**</td><td>

Turns on the *Skip confirmation when deleting to Recycle Bin* option on the [Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md) page in Preferences.

*Example:* `Set DELRECYCLECONFIRM=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the *Skip confirmation when deleting to Recycle Bin* option.

*Example:* `Set DELRECYCLECONFIRM=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the *Skip confirmation when deleting to Recycle Bin* option on and off.

*Example:* `Set DELRECYCLECONFIRM=toggle`
</td></tr><tr><td>
DEST</td><td>
/K</td><td>

**left**</td><td>

Sets the left (or top) file display in a dual-display Lister to be the destination.

*Example:* `Set DEST=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Sets the right (or bottom) file display to be the destination.

*Example:* `Set DEST=right`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Sets the file display that currently has the input focus to be the destination.

*Example:* `Set DEST=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the state (source/destination) of the left and right file displays.

*Example:* `Set DEST=toggle`
</td></tr><tr><td>
DISABLEGLOBALHOTKEYS</td><td>
/K</td><td>

**on**</td><td>

Temporarily disables all global hotkeys. Hotkeys local to a Lister will continue to function.

*Example:* `Set DISABLEGLOBALHOTKEYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Re-enables all global hotkeys.

*Example:* `Set DISABLEGLOBALHOTKEYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles all global hotkeys on and off.

*Example:* `Set DISABLEGLOBALHOTKEYS=toggle`
</td></tr><tr><td>
DUAL</td><td>
/K</td><td>

**on**</td><td>

Turns on [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode in the active Lister.

*Example:* `Set DUAL=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off dual-display mode in the active Lister.

*Example:* `Set DUAL=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles dual-display mode on or off in the active Lister.

*Example:* `Set DUAL=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

Sets dual-display mode to use horizontal layout (one file display above the other). By itself this value will turn dual-display mode on, but you can combine it with **toggle** to toggle horizontal dual-display on or off. If dual-display mode is already on but the layout is set to vertical, the layout will change to horizontal.

*Example:* `Set DUAL=horiz,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

Sets dual-display mode to use vertical layout (one file display next to the other).

*Example:* `Set DUAL=vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

Toggles the layout of dual-display mode between horizontal and vertical. If dual-display mode is not currently active this command has no effect unless the **toggle** keyword and either the **horiz** or **vert** keywords are also given.

If combined with those other keywords the function will turn on dual-display mode if it's not on already, switch the layout (from horizontal to vertical or vice versa) if dual-display is already on but not in the desired orientation, and close dual-display mode if it is on and already in the desired orientation.

*Example:* `Set DUAL=togglelayout`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

When dual-display mode is turned on, the newly opened file display will become the source. This value must be combined with one of the other values that actually causes dual-display mode to be switched on.

*Example:* `Set DUAL=toggle,source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

When dual-display mode is turned on, the newly opened file display will become the destination.

*Example:* `Set DUAL=toggle,dest`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

When dual-display mode is turned off, it will be the right (or bottom) file display that closes.

*Example:* `Set DUAL=off,right`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

When dual-display mode is turned off, it will be the left (or top) file display that closes.

*Example:* `Set DUAL=toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**remember**</td><td>

Use this value with the **toggle** keyword to cause the second file display to remember its path when it is closed and then opened again. If this isn't specified, the newly opened file display's path will be controlled by the **Specify initial folder when switching to dual file display** option on the **[File Displays / Options](/Manual/preferences/preferences_categories/file_displays/options/README.md)** page in Preferences.

*Example:* `Set DUAL=toggle,horiz,remember`
</td></tr><tr><td>
DUALSIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*</td><td>

Adjusts the splitter between the dual file displays in the active Lister. If the displays are arranged vertically, the command will affect their widths; if they are arranged horizontally it will affect their heights.

The size is given as a percentage, specifying how much of the available space the first file display should use, with the second file display getting whatever is left.

For example, specify 50 to make both file displays the same size (the same as double-clicking the splitter between them):

*Example:* `Set DUALSIZE 50`

As another example, specify 75 to make the first file display use 75% of the space to leave 25% of the space for the second:

*Example:* `Set DUALSIZE 75`

It is also possible to specify two sizes to make the command toggle between them. This lets you create a button or hotkey to quickly toggle between giving most of the space to one display and making them equal again.

*Example:* `Set DUALSIZE 75,50`

You can also resize the splitter by a relative amount by specifying a positive or negative delta.

*Example:* `Set DUALSIZE +10`
</td></tr><tr><td>
ENABLELABELFILTER</td><td>
/K</td><td>

*\<name\>*</td><td>

This command allows named [wildcard labels and label filters](/Manual/file_operations/labels.md) to be turned on or off. The specified name must have been assigned to the filter before you can control it via this command. Both global and Folder Format-based label filters are supported. You can specify **local:*\<name\>*** and **global:*\<name\>*** to restrict the type of filter you want to control, or just provide the name and Opus will look for it in both types of filter.

*Example:* `Set ENABLELABELFILTER my_filter,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**on**</td><td>

Turns the specified label filter on.

*Example:* `Set ENABLELABELFILTER my_filter,on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the specified label filter off.

*Example:* `Set ENABLELABELFILTER my_filter,off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the specified label filter on or off.

*Example:* `Set ENABLELABELFILTER my_filter,toggle`
</td></tr><tr><td>
EVALUATORDISABLE</td><td>
/O</td><td>

**on**</td><td>

Disables the [evaluator](/Manual/evaluator/README.md). You might want to do this if you've been experimenting with it and you find it's causing problems that need to be resolved before it can be turned back on again. The evaluator will stay disabled until you re-enable it (or until Opus is restarted).

*Example:* `Set EVALUATORDISABLE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>
Re-enables the evaluator.
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>
Toggles the evaluator on and off.
</td></tr><tr><td>
EXPANDABLEFOLDERS</td><td>
/O</td><td>

**on**</td><td>

Turns on [expandable folders](/Manual/basic_concepts/expandable_folders.md) in the current Lister. In this mode, folders can be expanded inline in the file display, much as they can in the folder tree. This command lets you override the default setting on the [Folder Expansion](/Manual/preferences/preferences_categories/file_displays/folder_expansion.md) Preferences page.

*Example:* `Set EXPANDABLEFOLDERS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off expandable folders in the current Lister.

*Example:* `Set EXPANDABLEFOLDERS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles expandable folders on and off in the current Lister.

*Example:* `Set EXPANDABLEFOLDERS=toggle`
</td></tr><tr><td>
FDBTOOLBAR</td><td>
/O</td><td>

*\<name\>*</td><td>

This command lets you change which toolbar is used for the [File Display](/Manual/basic_concepts/the_lister/navigation/file_display_border.md). If you don't specify a name the default File Display Toolbar is selected.

Multiple toolbars can be specified, separated by a comma.

*Example:* `Set FDBTOOLBAR "My FDB Toolbar"`  
*Example:* `Set FDBTOOLBAR "File Display,Images"`
</td></tr><tr><td>
</td><td>
</td><td>

**!static**</td><td>

Turns off the FDB toolbar altogether (reverting to a static header).

*Example:* `Set FDBTOOLBAR !static`
</td></tr><tr><td>
FILTERS</td><td>
/K</td><td>

**on**</td><td>

Turns both the copy and delete [recursive filters](/Manual/file_operations/filtered_operations/README.md) for the active Lister.

*Example:* `Set FILTERS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns both recursive filters off in the active Lister.

*Example:* `Set FILTERS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles both recursive filters on or off in the active Lister.

*Example:* `Set FILTERS=toggle`
</td></tr><tr><td>
FLATVIEW</td><td>
/K</td><td>

**on**</td><td>

Turns [Flat View](/Manual/basic_concepts/flat_view.md) mode on in the source file display.

*Example:* `Set FLATVIEW=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns Flat View mode off in the source file display.

*Example:* `Set FLATVIEW=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles Flat View on or off in the current source file display. If combined with one of the mode keywords (**group**, **mixed**, **mixednofolders**), Flat View will only be turned off if it is currently in the specified mode - otherwise, it will be set to that mode (and turned on if needed).

*Example:* `Set FLATVIEW=toggle,grouped`
</td></tr><tr><td>
</td><td>
</td><td>

**toggleoff**</td><td>

Toggles Flat View on or off. Unlike **toggle**, Flat View will be turned off if it is currently enabled in *any* mode, even if the mode does not match the specified keyword.

*Example:* `Set FLATVIEW=mixednofolders,toggleoff`
</td></tr><tr><td>
</td><td>
</td><td>

**grouped**</td><td>

Sets Flat View to *Grouped* mode.

*Example:* `Set FLATVIEW=grouped`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

Sets Flat View to *Mixed* mode.

*Example:* `Set FLATVIEW=toggle,mixed`
</td></tr><tr><td>
</td><td>
</td><td>

**mixednofolders**</td><td>

Sets Flat View to *Mixed (No Folders)* mode.

*Example:* `Set FLATVIEW=mixednofolders,on`
</td></tr><tr><td>
</td><td>
</td><td>

**keepformat**</td><td>

Lets you toggle Flat View without changing the current folder format. (Like disabling the Flat View format in Preferences, but only for the current change.) This can be useful if you usually want the location column added, but don't want it when using a particular button. It can also be useful if you want to set up columns and filtering in the file display before switching Flat View on, to reduce overheads (calculating columns you didn't want) and visual noise (things appearing in the file display, only to be removed immediately).

As an example, this toggles Flat View with all files hidden and the Full Path column visible (and Location and Relative Location columns removed, if present):

    @if:Set FLATVIEW=grouped
    Set FLATVIEW=off,keepformat
    Set HIDEFILTERFILENAME
    Set FORMAT=!folder
    @if:else
    Set HIDEFILTERFILENAME=*
    Set COLUMNSREMOVE=path,pathrel
    Set COLUMNSADD=fullpath(1)
    Set FLATVIEW=grouped,keepformat
</td></tr><tr><td>
FOCUS</td><td>
/K</td><td>

**left**</td><td>

Sets the input focus to the left-hand file display in a dual-display Lister.

*Example:* `Set FOCUS=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Sets the input focus to the right-hand file display in a dual-display Lister.

*Example:* `Set FOCUS=right`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Sets the input focus to the current source file display.

*Example:* `Set FOCUS=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Sets the input focus to the destination file display.

*Example:* `Set FOCUS=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

Sets the input focus to the folder tree. In a dual-display Lister, with dual trees, focus will go to the tree attached to the source file display.

*Example:* `Set FOCUS=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**lefttree**</td><td>

Sets the input focus to the left-hand folder tree in a dual-display, dual-tree Lister.

*Example:* `Set FOCUS=lefttree`
</td></tr><tr><td>
</td><td>
</td><td>

**righttree**</td><td>

Sets the input focus to the right-hand folder tree in a dual-display Lister.

*Example:* `Set FOCUS=righttree`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the input focus between the left and right file displays.

*Example:* `Set FOCUS=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**pathfield**</td><td>

Sets the focus to the source breadcrumbs path field.

*Example:* `Set FOCUS=pathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**leftpathfield**</td><td>

Sets the focus to the left/top path field in a dual-display Lister.

*Example:* `Set FOCUS=leftpathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**rightpathfield**</td><td>

Sets the focus to the right/bottom path field in a dual-display Lister.

*Example:* `Set FOCUS=rightpathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**filedisplay**</td><td>

When testing which control has focus using [@if:set](/Manual/customize/creating_your_own_buttons/command_modifiers.md) you can use this to mean "any file display" rather than having to specifiy source/destination etc.

*Example:* `@if:set FOCUS=filedisplay`
</td></tr><tr><td>
</td><td>
</td><td>

**metapane**</td><td>

Gives focus to the [Metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md).

*Example:* `Set FOCUS=metapane`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

Sets the focus to the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md).

*Example:* `Set FOCUS=viewpane`
</td></tr><tr><td>
FOLDERTREESIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*\[,**left**\|**right**\|**dest**\]</td><td>

Adjusts the size of the folder tree pane in the active Lister. The size is given as an absolute width in pixels. It is possible to specify two separate sizes, and the command will toggle between them. You can also make the command operate on a folder tree other than the one attached to the current source file display by appending the **left**, **right** or **dest** keywords.

*Example:* `Set FOLDERTREESIZE 200,300`
</td></tr><tr><td>
FONTSCALE</td><td>
/K</td><td>

*\<absolute factor\>*</td><td>

Sets the font scaling in the file display to the specified factor. **100** (meaning 100%) is the baseline level, and represents the actual point size configured on the **[Fonts](/Manual/preferences/preferences_categories/colors_and_fonts/fonts.md)** page in Preferences. **200** would represent twice as large, **50** would represent half as large, and so on.

Note that font scaling only applies to Details, Power and Thumbnails [view modes](/Manual/basic_concepts/the_lister/view_modes.md). There are separate scaling settings for Details/Power and Thumbnails modes - by default this command adjusts the settings for the current mode, but you can use optional keywords to specify the affected mode.

*Example:* `Set FONTSCALE=125`
</td></tr><tr><td>
</td><td>
</td><td>

*\<relative factor\>*</td><td>

Adjusts the font scaling in the file display by the specified delta. Use a positive value to increase the scaling and a negative value to decrease it.

*Example:* `Set FONTSCALE=-10`
</td></tr><tr><td>
</td><td>
</td><td>

*\<factor1\>,\<factor2\>*</td><td>

Specify two absolute scale factors to create a command that toggles between the two.

*Example:* `Set FONTSCALE=100,150`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Scales the font in the left-hand file display, whether it is the source or not.

*Example:* `Set FONTSCALE=50,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Scales the font in the right-hand file display.

*Example:* `Set FONTSCALE=right,-25`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Scales the font in the destination file display.

*Example:* `Set FONTSCALE=dest,+50`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Scales the font in both the left and right file displays.

*Example:* `Set FONTSCALE=50,125,both`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

Only adjusts the font for Details and Power mode.

*Example:* `Set FONTSCALE=150,details`
</td></tr><tr><td>
</td><td>
</td><td>

**thumbnails**</td><td>

Only adjusts the font for Thumbnails mode.

*Example:* `Set FONTSCALE=+50,thumbnails`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Adjusts the font for both Details/Power modes and Thumbnails mode.

*Example:* `Set FONTSCALE=+50,thumbnails`
</td></tr><tr><td>
FORMAT</td><td>
/K</td><td>

*\<format\>*</td><td>

Applies the named favorite folder format to the current source file display. The format must have been previously created through the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** Preferences page.

*Example:* `Set FORMAT "Photo Viewing"`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

Applies the Folder Type format applicable to the source file display's path. For example, if the current path is a network drive, the **Network Drives** format would be applied.

*Example:* `Set FORMAT=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!factory**</td><td>

Applies the hardcoded, factory-default folder format to the current source file display.

*Example:* `Set FORMAT !factory`
</td></tr><tr><td>
</td><td>
</td><td>

**!folder**</td><td>

Finds and applies a folder format by using the same rules as when the folder was initially loaded. This generally gives you what you would get if you opened the current folder in a new window. See the **[Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** Preferences page for a description of the rules applied when Opus chooses a folder format for a path.

*Example:* `Set FORMAT !folder`
</td></tr><tr><td>
</td><td>
</td><td>

**!user**</td><td>

Applies the **User Default** folder format to the current source file display.

*Example:* `Set FORMAT !user`
</td></tr><tr><td>
FORMATLIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a generated list of your favorite and content type folder formats (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). This displays one item for each format saved in the Favorite Formats category on the **[Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md)** page in Preferences. Selecting a format from the generated list applies its settings to the current file display.

*Example:* `Set FORMATLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**contenttype**</td><td>

Only displays content type formats (omits those for favorites).

*Example:* `Set FORMATLIST=contenttype`
</td></tr><tr><td>
</td><td>
</td><td>

**favorites**</td><td>

Only displays favorite formats (omits those for content types).

*Example:* `Set FORMATLIST=favorites`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

Assigns icons to the list items the command generates. The button which creates the list must also have its icon turned on for them to appear.

*Example:* `Set FORMATLIST=icons,favorites`
</td></tr><tr><td>
</td><td>
</td><td>

**noreset**</td><td>

Prevents the addition of the "reset" commands which are normally generated at the end of the format list (e.g. Reset to Defaults).

*Example:* `Set FORMATLIST=favorites,noreset`
</td></tr><tr><td>
FORMATLOCK</td><td>
/K</td><td>

**on**</td><td>

Turns the [format lock](/Manual/basic_concepts/folder_options/locking_the_format.md) on in the current Lister. By default this works on the active file display (the one with focus) but you can combine with the other arguments to control which file displays are affected.

*Example:* `Set FORMATLOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the format lock off in the active file display.

*Example:* `Set FORMATLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the format lock on or off in the current Lister. This command can replace the padlock icon in the default status bar. If combined with the **all** keyword in a dual display Lister, this will turn the format lock on in both file displays if neither or one are currently on. Only if both are already on will the lock be turned off.

*Example:* `Set FORMATLOCK=toggle,all`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Applies the format lock to only the left (or top) file display in a dual-display Lister.

*Example:* `Set FORMATLOCK=toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Applies the format lock to only the right (or bottom) file display.

*Example:* `Set FORMATLOCK=toggle,right`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Applies the format lock to only the source file display in a dual-display Lister.

*Example:* `Set FORMATLOCK=toggle,source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Applies the format lock to only the destination file display.

*Example:* `Set FORMATLOCK=toggle,dest`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Applies the format lock to both file displays in a dual-display Lister (or the single display otherwise).

*Example:* `Set FORMATLOCK=off,all`
</td></tr><tr><td>
FRIENDLYDATES</td><td>
/K</td><td>

**normal**</td><td>

Turns on "friendly dates", where date columns display "Today" for today, "Yesterday" for yesterday, and weekday names ("Monday", etc.) for dates from the last seven days.

*Example:* `Set FRIENDLYDATES=normal`
</td></tr><tr><td>
</td><td>
</td><td>

**today**</td><td>

Turns on "friendly dates", but only for "Today".

*Example:* `Set FRIENDLYDATES=today`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off "friendly dates". All dates will display as a day, month and year (according to your date format settings).

*Example:* `Set FRIENDLYDATES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggles**</td><td>

Toggles "friendly dates" on and off. Can be combined with **normal** or **today** to specify a mode when turning friendly dates on; otherwise, the previously configured mode will be used.

*Example:* `Set FRIENDLYDATES=toggle`  
*Example:* `Set FRIENDLYDATES=toggle,normal`
</td></tr><tr><td>
FTPMODE</td><td>
/K</td><td>

**ascii**</td><td>

Sets the file transfer mode for the current FTP connection to ASCII. This command has no effect if the source file display is not currently viewing a remote FTP site.

*Example:* `Set FTPMODE=ascii`
</td></tr><tr><td>
</td><td>
</td><td>

**binary**</td><td>

Sets the transfer mode to binary for the current FTP connection.

*Example:* `Set FTPMODE=binary`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

Automatically selects the transfer mode based on the file type being transferred.

*Example:* `Set FTPMODE=auto`
</td></tr><tr><td>
FULLROWSELECT</td><td>
/K</td><td>

**on**</td><td>

Turns full-row selection on. There are separate full-row settings in Preferences for both power (**[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)**) and details (**[File Display Modes / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)**) [view modes](/Manual/basic_concepts/the_lister/view_modes.md), and by default this command will affect the setting for the current view mode in the source file display. You can use the other keywords for this argument to control which view mode is affected.

*Example:* `Set FULLROWSELECT=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns full-row selection off.

*Example:* `Set FULLROWSELECT=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles full-row selection on or off.

*Example:* `Set FULLROWSELECT=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**power**</td><td>

Only affects the setting for Power mode, irrespective of the current view mode.

*Example:* `Set FULLROWSELECT=toggle,power`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

Only affects the setting for details mode.

*Example:* `Set FULLROWSELECT=on,details`
</td></tr><tr><td>
</td><td>
</td><td>

**namecol**</td><td>

When turning off full-row selection, the "full width of Name column" mode will be used instead of "filename only" mode. Has no effect if full-row selection is being turned on.

*Example:* `Set FULLROWSELECT=off,namecol`
</td></tr><tr><td>
GLOBALHIDEFILENAME</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the **Global hide filter** filename filter (on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).

*Example:* `Set GLOBALHIDEFILENAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the **Global hide filter** filename filter to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md).

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the filter is already set to the specified pattern, it will be cleared, making the command automatically act as a toggle.

*Example:* `Set GLOBALHIDEFILENAME "(desktop.ini\|\*.db)"`  
*Example:* `Set GLOBALHIDEFILENAME regex:.db\$`
</td></tr><tr><td>
GLOBALHIDEFILTER</td><td>
/K</td><td>

**on**</td><td>

Turns the **Enable global wildcard filters** option on (on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).

*Example:* `Set GLOBALHIDEFILTER on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the **Enable global wildcard filters** option off.

*Example:* `Set GLOBALHIDEFILTER off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Enable global wildcard filters** option on or off.

*Example:* `Set GLOBALHIDEFILTER=toggle`
</td></tr><tr><td>
GLOBALHIDEFOLDERS</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the **Global hide filter** folder filter (on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).

*Example:* `Set GLOBALHIDEFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the **Global hide filter** folder filter to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md).

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the filter is already set to the specified pattern, it will be cleared, making the command automatically act as a toggle.

*Example:* `Set GLOBALHIDEFOLDERS .svn`
</td></tr><tr><td>
GLOBALHIDEHIDDEN</td><td>
/K</td><td>

**on**</td><td>

Turns the global **Hide hidden files** option on (on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).

*Example:* `Set GLOBALHIDEHIDDEN on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the global **Hide hidden files** option off.

*Example:* `Set GLOBALHIDEHIDDEN off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the global **Hide hidden files** option on or off.

*Example:* `Set GLOBALHIDEHIDDEN=toggle`
</td></tr><tr><td>
GRIDLINESH</td><td>
/K</td><td>

**on**</td><td>

Turns horizontal grid lines on in the current file display (only visible in power or details [view modes](/Manual/basic_concepts/the_lister/view_modes.md)). This command overrides the settings in Preferences (on either the **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)** or **[File Display Modes / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)** pages), but changes are only applicable to the current source file display - the global Preferences settings are not modified.

*Example:* `Set GRIDLINESH on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns horizontal grid lines off in the current file display.

*Example:* `Set GRIDLINESH off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles horizontal grid lines on or off in the current file display. If the **reset** keyword is also given, the command will toggle between the grid lines specified in the command line, and the current Preferences settings.

*Example:* `Set GRIDLINESH=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the horizontal grid lines settings in the current file display to those defined in Preferences. You can combine this with the **toggle** keyword to toggle between the Preferences settings and another set of custom settings.

*Example:* `Set GRIDLINESH=reset,toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

*\<style\>*</td><td>

Sets horizontal grid lines to use the specified style. Use this keyword in conjunction with the **on**, **off** or **toggle** keywords to control which style is displayed by the command.

Supported styles are **solid**, **alternate**, **dot**, **dash**, **dashdot**, **dashdotdot** and **fill**. Note that **solid** indicates a solid unbroken single-pixel line, whereas **fill** indicates alternating rows (i.e. thick lines which fill the whole background of every second row).

*Example:* `Set GRIDLINESH=toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<color\>*</td><td>

Sets the color of the horizontal grid lines. *\<color\>* can be specified in either decimal format (**rrr,ggg,bbb**) or hex format (**\#rrggbb**). Because the **color=** keyword contains an equals sign, you must enclose the whole value for the **GRIDLINES** argument in quotes to avoid confusing the command parser.

*Example:* `Set GRIDLINESH "toggle,fill,color=#ff8000"`
</td></tr><tr><td>
</td><td>
</td><td>

**opacity=***\<opacity\>*</td><td>

Sets the opacity of the horizontal gridlines. *\<opacity\>* must be a value from **1** (nearly transparent) to **100** (solid). Because the **opacity=** keyword contains an equals sign, you must enclose the whole value for the **GRIDLINES** argument in quotes to avoid confusing the command parser.

*Example:* `Set GRIDLINESH "toggle,solid,color=#808080,opacity=50"`
</td></tr><tr><td>
GRIDLINESV</td><td>
/K</td><td>

**on**</td><td>

Turns vertical grid lines on in the current file display (only visible in power or details [view modes](/Manual/basic_concepts/the_lister/view_modes.md)). This command overrides the settings in Preferences (on either the **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)** or **[File Display Modes / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)** pages), but changes are only applicable to the current source file display - the global Preferences settings are not modified.

*Example:* `Set GRIDLINESV on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns vertical grid lines off in the current file display.

*Example:* `Set GRIDLINESV off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles vertical grid lines on or off in the current file display. If the **reset** keyword is also given, the command will toggle between the grid lines specified in the command line, and the current Preferences settings.

*Example:* `Set GRIDLINESV=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the vertical grid lines settings in the current file display to those defined in Preferences. You can combine this with the **toggle** keyword to toggle between the Preferences settings and another set of custom settings.

*Example:* `Set GRIDLINESV=reset,toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

*\<style\>*</td><td>

Sets vertical grid lines to use the specified style. Use this keyword in conjunction with the **on**, **off** or **toggle** keywords to control which style is displayed by the command.

Supported styles are **solid**, **alternate**, **dot**, **dash**, **dashdot**, and **dashdotdot**.

*Example:* `Set GRIDLINESV=toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<color\>*</td><td>

Sets the color of the vertical grid lines. *\<color\>* can be specified in either decimal format (**rrr,ggg,bbb**) or hex format (**\#rrggbb**). Because the **color=** keyword contains an equals sign, you must enclose the whole value for the **GRIDLINES** argument in quotes to avoid confusing the command parser.

*Example:* `Set GRIDLINESV "toggle,fill,color=#ff8000"`
</td></tr><tr><td>
</td><td>
</td><td>

**opacity=***\<opacity\>*</td><td>

Sets the opacity of the vertical gridlines. *\<opacity\>* must be a value from **1** (nearly transparent) to **100** (solid). Because the **opacity=** keyword contains an equals sign, you must enclose the whole value for the **GRIDLINES** argument in quotes to avoid confusing the command parser.

*Example:* `Set GRIDLINESV "toggle,solid,color=#808080,opacity=50"`
</td></tr><tr><td>
GROUPBY</td><td>
/K</td><td>

*\<column\>*</td><td>

[Groups](/Manual/basic_concepts/sorting_and_grouping/README.md) the current file display by the specified column. The value must be one of the valid [column keywords](../../metadata_keywords/keywords_for_columns.md).

As well as the column keywords, **GROUPBY** recognizes the special keyword synonyms **accessed**, **created**, **date, disksize, modified, path** and **size**. This lets you group by date, size or path without needing to know the exact column that is displayed (e.g. the column could be **size**, **sizekb** or **sizerel** - but the sorting is the same in all cases, and `Set GROUPBY=size` would work for any column).

If you have any [evaluator grouping schemes](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.md) defined for the specified column, you can use the **GROUPSCHEME** argument to select one.

The **GROUPBY** argument also recognizes the special keywords **dupes** and **cdstage**. These do not correspond with columns, and are only valid in certain folders.

`Set GROUPBY=dupes` can only be used in a [file collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) that has been used as the target of a [Duplicate Files](/Manual/additional_functionality/duplicate_file_finder.md) search (to group the list by the duplicate file groups found), and `Set GROUPBY=cdstage` can only be used on a recordable CD/DVD to group the list into files waiting to be burned and files already on the disk.

*Example:* `Set GROUPBY=picsize`

Within the **Lister Column Header[Context Menu](/Manual/customize/the_customize_dialog/context_menus.md)**, you can use **%header%** to refer to the column which was right-clicked.

*Example:* `Set GROUPBY=%header%,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles grouping by the specified column on or off. Note that the column name must come first.

*Example:* `Set GROUPBY=picsize,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns grouping off in the current file display.

*Example:* `Set GROUPBY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**grouplist**</td><td>

When used on a toolbar or menu, the command will turn into a dynamic list of available columns which can be grouped by. Add the **GROUPSCHEME** argument to display sub-menus for any grouping schemes defined for those columns.

*Example:* `Set GROUPBY=grouplist GROUPSCHEME`
</td></tr><tr><td>
GROUPCOLLAPSE</td><td>
/K</td><td>

**on**</td><td>

Turns on the Collapsed option for grouping in the current file display.

You can also combine this with the `GROUPBY` argument to automatically collapse all groups when switching into grouping mode.

*Example:* `Set GROUPCOLLAPSE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the Collapsed option.

*Example:* `Set GROUPCOLLAPSE off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the Collapsed option on and off for the current file display. Note that you need to reread the folder to see the result of the change.

*Example:* `Set GROUPCOLLAPSE=toggle`
</td></tr><tr><td>
GROUPCOMBINE</td><td>
/K</td><td>

**normal**</td><td>

Sets the **Grouping / Combine** option to **Combine similar values** in the folder format for the current file display. This is the default grouping behaviour. For example, when grouping by filename, you might have groups for names beginning with A-H, I-P and Q-Z.

*Example:* `Set GROUPCOMBINE=normal GROUPBY=name`
</td></tr><tr><td>
</td><td>
</td><td>

**never**</td><td>

Never combines group values. If this is turned on and the file display is grouped, one group will be created for each distinct value rather than a range of values falling into a single group (e.g. instead of A-H you would have A, B, C, D, E, F, G, H). This is only really useful for text fields like "User description".

*Example:* `Set GROUPCOMBINE=never`
</td></tr><tr><td>
</td><td>
</td><td>

**other**</td><td>

Groups will be combined as with the **normal** option, but groups with only one item in them are further combined into a special group called **Other**.

*Example:* `Set GROUPCOMBINE=other`
</td></tr><tr><td>
</td><td>
</td><td>

**cycle**</td><td>

Cycles through the three grouping modes.

*Example:* `Set GROUPCOMBINE=cycle`
</td></tr><tr><td>
GROUPFOLDERSATTOP</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Keep folders at top when grouped** option in the current file display.

*Example:* `Set GROUPFOLDERSATTOP=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Keep folders at top when grouped** option.

*Example:* `Set GROUPFOLDERSATTOP=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the Keep folders at top when grouped option on or off in the current file display.

*Example:* `Set GROUPFOLDERSATTOP=toggle`
</td></tr><tr><td>
GROUPREVERSE</td><td>
/K</td><td>

**on**</td><td>

Reverses the direction of grouping in the current file display. The actual order of the groups is reversed, not the order of files within the groups.

*Example:* `Set GROUPREVERSE=on GROUPBY=picsize`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns reverse grouping off.

*Example:* `Set GROUPREVERSE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles reverse grouping on or off in the current file display.

*Example:* `Set GROUPREVERSE=toggle`
</td></tr><tr><td>
GROUPSCHEME</td><td>
/O</td><td>

*(no value)*</td><td>

When used with the **GROUPBY=grouplist** argument, this displays submenus for any columns that have [evaluator grouping schemes](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.md) defined.

*Example:* `Set GROUPBY=grouplist GROUPSCHEME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<group\>*</td><td>

Specifies the name of a grouping scheme to use when enabling grouping with the **GROUPBY** argument.

*Example:* `Set GROUPBY=name GROUPSCHEME=first_letter`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Set COLUMNSTOGGLE=columnlist HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Set SORTBY=sortlist HEADING="Sort"`
</td></tr><tr><td>
HIDE</td><td>
/S</td><td>

*(no value)*</td><td>

Hides any **Set** command toolbar button that would ordinarily be disabled because the function is not available. This argument does nothing on its own - it is only used in conjunction with other **Set** command arguments.

For example, the command `Set FTPMODE=ascii` would normally be disabled on the toolbar when not currently in an FTP folder, but the command `Set FTPMODE=ascii HIDE` would cause the button to be removed from the toolbar instead of just being disabled.

*Example:* `Set FLATVIEW=toggle,grouped HIDE`
</td></tr><tr><td>
HIDEEXT</td><td>
/K</td><td>

**on**</td><td>

Turns the *Hide file extension in Filename column* option on in the current file display.

*Example:* `Set HIDEEXT=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the *Hide file extension* option off.

*Example:* `Set HIDEEXT=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the *Hide file extension* option on or off in the current file display.

*Example:* `Set HIDEEXT=toggle`
</td></tr><tr><td>
HIDEFILTERATTR</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the attributes hide filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Hide Filter / Attributes*.

*Example:* `Set HIDEFILTERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

Sets the attributes hide filter in the source file display. Files that have all the specified attributes set will be hidden from the display of the current folder.

The *\<attributes\>* value is one or more of the following letters: **R** (read-only), **A** (archive), **H** (hidden), **S** (system), **E** (encrypted), **C** (compressed), **O** (offline), **I** (non-indexed), **P** (pinned). See [Changing Attributes](/Manual/file_operations/changing_attributes.md) for detailed descriptions.

*Example:* `Set HIDEFILTERATTR hs`

If the specified attributes are already set as the filter, the filter will be cleared, making the command automatically act as a toggle. You can also specify two sets of attributes, and the command will alternate between them each time it is run.

*Example:* `Set HIDEFILTERATTR hs,rhs`
</td></tr><tr><td>
HIDEFILTERFILENAME</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the filename hide filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Hide Filter / Filename*.

*Example:* `Set HIDEFILTERFILENAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the filename hide filter in the source file display to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Files that match the pattern will be hidden from the display of the current folder.

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the specified pattern is already set as the filter, the filename filter will be cleared, making the command automatically work as a toggle.

*Example:* `Set HIDEFILTERFILENAME \*.(jpg\|bmp\|png\|gif)`
</td></tr><tr><td>
HIDEFILTERFOLDERATTR</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the folder attributes hide filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Hide Filter / Folder Attributes*.

*Example:* `Set HIDEFILTERFOLDERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

Sets the folder attributes hide filter in the source file display. Folders that have all the specified attributes set will be hidden from the display of the current folder.

The *\<attributes\>* value is one or more of the following letters: **R** (read-only), **A** (archive), **H** (hidden), **S** (system), **E** (encrypted), **C** (compressed), **O** (offline), **I** (non-indexed), **P** (pinned). See [Changing Attributes](/Manual/file_operations/changing_attributes.md) for detailed descriptions.

*Example:* `Set HIDEFILTERFOLDERATTR h`

If the specified attributes are already set as the filter, the filter will be cleared, making the command automatically act as a toggle. You can also specify two sets of attributes, and the command will alternate between them each time it is run.

*Example:* `Set HIDEFILTERFOLDERATTR h,ce`  
*Example:* `Set HIDEFILTERFOLDERATTR h,off`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Disables the separate folder attributes hide filter. When the folder attributes filter is disabled, the regular attributes filter will apply to both files and folders.

*Example:* `Set HIDEFILTERFOLDERATTR off`
</td></tr><tr><td>
HIDEFILTERFOLDERS</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the folders hide filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Hide Filters / Folder Names*.

*Example:* `Set HIDEFILTERFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the folders hide filter in the source file display to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Folders whose name matches the pattern will be hidden from the display of the current folder.

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the specified pattern is already set as the filter, the name filter will be cleared, making the command automatically work as a toggle.

*Example:* `Set HIDEFILTERFOLDERS .svn`
</td></tr><tr><td>
HIDESYSTEMFILES</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Hide protected operating system files** option on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences. This option causes all files and folders with both the H (hidden) and S (system) attributes to be hidden.

*Example:* `Set HIDESYSTEMFILES on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Hide protected operating system files** option.

*Example:* `Set HIDESYSTEMFILES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Hide protected operating system files** option on or off.

*Example:* `Set HIDESYSTEMFILES=toggle`
</td></tr><tr><td>
ICONMODESORTHEADER</td><td>
/K</td><td>

**on**</td><td>

Turns on the display of the column header (for sorting) in the icon modes (large icon, thumbnail, etc). This controls the *Show sort header in icon modes* on the **[File Displays / Options](/Manual/preferences/preferences_categories/file_displays/options/README.md)** page in Preferences.

*Example:* `Set ICONMODESORTHEADER=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the column header in the icon modes.

*Example:* `Set ICONMODESORTHEADER=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the icon mode column header on and off.

*Example:* `Set ICONMODESORTHEADER=toggle`
</td></tr><tr><td>
ICONS</td><td>
/K</td><td>

**on**</td><td>

Enables the display of icons in power and details view modes in the current file display. This overrides the setting on the appropriate page in Preferences (**[File Display Modes / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.md)** or **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.md)**).

*Example:* `Set ICONS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the display of icons in power and details modes for the current file display.

*Example:* `Set ICONS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the display of icons in power and details modes.

*Example:* `Set ICONS=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the icon display to the current Preferences settings.

*Example:* `Set ICONS=reset`
</td></tr><tr><td>
IMAGEASPECTOVERLAYS</td><td>
/K</td><td>

**on**</td><td>

Turns on display of thumbnails-mode aspect ratio bars. This modifies the **Overlay aspect ratio bars** option on the **[File Display Modes / Thumbnails](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.md)** page in Preferences. As this is a global setting, all currently open Listers will be affected.

*Example:* `Set IMAGEASPECTOVERLAYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off display of thumbnails-mode aspect ratio bars.

*Example:* `Set IMAGEASPECTOVERLAYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles display of thumbnails-mode aspect ratio bars on or off.

*Example:* `Set IMAGEASPECTOVERLAYS=toggle`
</td></tr><tr><td>
INVERT</td><td>
/S</td><td>

*(no value)*</td><td>

Inverts the appearance of toolbar buttons that appear highlighted (or checked) when the **Set** option they control is currently on.

For example, a command like `Set TREE=toggle` will appear highlighted on the toolbar when the folder tree is displayed. Changing the command to `Set TREE=toggle INVERT` would cause the toolbar button to appear highlighted when the tree is not displayed.

*Example:* `Set HIDESYSTEMFILES=toggle INVERT`
</td></tr><tr><td>
JOBSBAR</td><td>
/K</td><td>

**on**</td><td>

Displays the [jobs bar](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md) in the current Lister.

*Example:* `Set JOBSBAR=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Hides the [jobs bar](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md) in the current Lister.

*Example:* `Set JOBSBAR=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the [jobs bar](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md) on and off.

*Example:* `Set JOBSBAR=toggle`
</td></tr><tr><td>
KEEPFOLDERSALPHA</td><td>
/K</td><td>

**on**</td><td>

Turns the **Keep folders sorted alphabetically** option on in the source file display. This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set KEEPFOLDERSALPHA=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the **Keep folders sorted alphabetically** option off.

*Example:* `Set KEEPFOLDERSALPHA off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the state of the **Keep folders sorted alphabetically** option.

*Example:* `Set KEEPFOLDERSALPHA=toggle`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

**remember**</td><td>

Remembers the current layout and appearance of the active Lister.

*Example:* `Set LAYOUT=remember`
</td></tr><tr><td>
</td><td>
</td><td>

**restore**</td><td>

Restores the previously remembered layout and appearance of the active Lister. For example, if you run the `Set LAYOUT=remember` command, and then make changes to the Lister like closing the tree, opening the viewer pane, or selecting a new [style](/Manual/basic_concepts/the_lister/styles.md), the `Set LAYOUT=restore` command would restore the Lister to its original state.

*Example:* `Set LAYOUT=restore`
</td></tr><tr><td>
LISTERCMD</td><td>
/K</td><td>

**minimize**</td><td>

Minimizes the currently active Lister window.

*Example:* `Set LISTERCMD=minimize`
</td></tr><tr><td>
</td><td>
</td><td>

**maximize**</td><td>

Maximizes the currently active Lister window.

*Example:* `Set LISTERCMD=maximize`
</td></tr><tr><td>
</td><td>
</td><td>

**restore**</td><td>

Restores the original size and position of the window (before it was either minimized or maximized).

*Example:* `Set LISTERCMD=restore`
</td></tr><tr><td>
</td><td>
</td><td>

**togglemaximize**</td><td>

If the current Lister window is not maximized, it will be maximized, otherwise it will be restored. You could use this to add a hotkey that switches a Lister in and out of "full-screen" mode.

*Example:* `Set LISTERCMD=togglemaximize`
</td></tr><tr><td>
</td><td>
</td><td>

**showall**</td><td>

Makes all currently open Listers visible. Minimized windows will be restored, and all Lister windows will come to the front.

*Example:* `Set LISTERCMD=showall`
</td></tr><tr><td>
</td><td>
</td><td>

**minimizeall**</td><td>

Minimizes all currently open Listers.

*Example:* `Set LISTERCMD=minimizeall`
</td></tr><tr><td>
</td><td>
</td><td>

**tileh**</td><td>

Tiles all currently open Listers horizontally across the screen.

*Example:* `Set LISTERCMD=tileh`
</td></tr><tr><td>
</td><td>
</td><td>

**tilev**</td><td>

Tiles all Listers vertically across the screen.

*Example:* `Set LISTERCMD=tilev`
</td></tr><tr><td>
</td><td>
</td><td>

**cascade**</td><td>

Cascades all Lister windows. All windows are made the same size and positioned staggered diagonally down and across the screen.

*Example:* `Set LISTERCMD=cascade`
</td></tr><tr><td>
</td><td>
</td><td>

**undotilecascade**</td><td>

Undoes the previous tile or cascade operation. As much as possible windows are put back to their previous sizes and positions.

*Example:* `Set LISTERCMD=undotilecascade`
</td></tr><tr><td>
</td><td>
</td><td>

**toggleminimizeall**</td><td>

Minimizes all currently open Lister windows. If all windows are already minimized they will all be restored.

*Example:* `Set LISTERCMD=toggleminimizeall`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

Brings the Lister window to the front. This command is most useful when run from a [script](/Manual/scripting/README.md).

*Example:* `Set LISTERCMD=tofront`
</td></tr><tr><td>
LISTERPOS</td><td>
/K</td><td>

*\<x\>,\<y\>*</td><td>

Sets the position of the active Lister to the specified x and y coordinates. You can also specify a delta to modify the current position.

*Example:* `Set LISTERPOS=500,200`  
*Example:* `Set LISTERPOS=+100,+50`
</td></tr><tr><td>
LISTERSIZE</td><td>
/K</td><td>

*\<w\>,\<h\>*</td><td>

Sets the size of the currently active Lister to the specified width and height. You can also specify a delta to modify the current size.

*Example:* `Set LISTERSIZE=1024,768`  
*Example:* `Set LISTERSIZE=+50,+50`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

Automatically resizes the Lister horizontally (as much as possible) to exactly fit the currently displayed columns (only in Details or Power mode).

*Example:* `Set LISTERSIZE=auto`
</td></tr><tr><td>
LISTERTITLE</td><td>
/O</td><td>

*(no value)*</td><td>

Resets the title of the current Lister back to its default.

*Example:* `Set LISTERTITLE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<custom title\>*</td><td>

Sets a custom title for the currently active Lister. You can use several special "tokens" in the title string to insert various pieces of information:

|        |                                                                       |
|--------|-----------------------------------------------------------------------|
| **%P** | full path of the current (source) folder                              |
| **%N** | name of the current (source) folder                                   |
| **%R** | drive root of the current (source) folder                             |
| **%D** | full path of the destination folder                                   |
| **%M** | name of the destination folder                                        |
| **%G** | target if the folder is a junction or softlink                        |
| **%1** | full path in the left file display                                    |
| **%2** | full path in the right file display                                   |
| **%3** | folder name in the left file display                                  |
| **%4** | folder name in the right file display                                 |
| **%L** | name of the Layout the Lister came from (if any)                      |
| **%S** | name of the current Style selected in the Lister (if any)             |
| **%T** | complete original title (useful for simply adding a prefix or suffix) |
| **%!** | hide section                                                          |

*Example:* `Set LISTERTITLE "Directory Opus - %N"`

This command normally act as a toggle, such that the title will be cleared if you run the command when the specified title is already set. You can prevent this by prefixing the title with "notoggle:". This can be useful in event-driven scripts which may make redundant requests to set the title and would have to check its current value to avoid resetting it otherwise.

*Example:* `Set LISTERTITLE "notoggle:Directory Opus - %N"`

The **%!** code lets you hide sections in the string where all other tokens inside the section are empty.

*Example:* `Set LISTERTITLE "%!%T - %!Directory Opus"`

That means that if the **%T** token expands to an empty string, the result will be just "Directory Opus" rather than " - Directory Opus".
</td></tr><tr><td>
MANUALSORT</td><td>
/K</td><td>

**on**</td><td>

Turn on [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) in the current file display. The default manual sort order will be used unless alternative manual sort names have been configured and you specify the name using the *\<name\>* parameter.

*Example:* `Set MANUALSORT=on,MySortOrder`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turn off manual sorting in the current source file display.

*Example:* `Set MANUALSORT=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggle the manual sort mode on or off in the current file display.

*Example:* `Set MANUALSORT=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

*\<name\>*</td><td>

Specifies an alternative name for the sort order to use, which must first have been configured using the **manual_sort_names** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

*Example:* `Set MANUALSORT=MySortOrder,toggle`
</td></tr><tr><td>
MANUALSORTRESET</td><td>
/O</td><td>

*(no value)*</td><td>

Resets the current manual sort order for the folder in the source file display. The file list will be resorted using the current (non-manual) sort method and your old manual sort order will be discarded.

*Example:* `Set MANUALSORTRESET`
</td></tr><tr><td>
</td><td>
</td><td>

*\<name\>*</td><td>

Resets the named manual sort order for the current folder. The name must first have been configured using the **manual_sort_names** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

*Example:* `Set MANUALSORTRESET=MySortOrder`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

Resets the default manual sort order for the current folder.

*Example:* `Set MANUALSORTRESET=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!all**</td><td>

Resets all manual sort orders (default and named) for the current folder.

*Example:* `Set MANUALSORTRESET=!all`
</td></tr><tr><td>
MANUALSORTSAVE</td><td>
/S</td><td>

*(no value)*</td><td>

Saves the current manual sort order in the current folder. You would only need to use this command if you don't have automatic saving of manual sort orders enabled.

*Example:* `Set MANUALSORTSAVE`
</td></tr><tr><td>
METAPANE</td><td>
/K</td><td>

**on**</td><td>

Turns the [metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md) on in the currently active Lister.

*Example:* `Set METAPANE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the metadata pane off in the active Lister.

*Example:* `Set METAPANE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the metadata pane on or off.

*Example:* `Set METAPANE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

Forces the metadata pane to horizontal layout when it is opened.

*Example:* `Set METAPANE=toggle,horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

Specifies vertical layout for the metadata pane.

*Example:* `Set METAPANE=on,vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

Toggles the layout of the metadata pane between vertical and horizontal.

*Example:* `Set METAPANE=togglelayout`
</td></tr><tr><td>
METAPANESIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*</td><td>

Adjusts the size of the metadata pane in the active Lister. The size is given as a percentage of the total size of the Lister, and applies in the appropriate dimension based on the current layout of the metadata pane (so for example, when the pane is horizontal this affects its height).

It is also possible to specify two separate sizes, and the command will toggle between them.

*Example:* `Set METAPANESIZE 25,50`
</td></tr><tr><td>
MINIMIZEPROGRESS</td><td>
/K</td><td>

**on**</td><td>

Turns on the *Minimize progress indicators automatically* option from the [Progress Indicators](/Manual/preferences/preferences_categories/file_operations/progress_indicators/README.md) page in Preferences.

*Example:* `Set MINIMIZEPROGRESS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the *Minimize progress indicators automatically* option off.

*Example:* `Set MINIMIZEPROGRESS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles *Minimize progress indicators automatically* on or off.

*Example:* `Set MINIMIZEPROGRESS=toggle`
</td></tr><tr><td>
NAVLOCK</td><td>
/K</td><td>

**on**</td><td>

Turns [navigation lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) on in the current Lister. This command is only available if the Lister is in [dual-display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode.

*Example:* `Set NAVLOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns navigation lock off in the active Lister.

*Example:* `Set NAVLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles navigation lock on or off in the active Lister.

*Example:* `Set NAVLOCK=toggle`
</td></tr><tr><td>
NOOP</td><td>
/S</td><td>

*(no value)*</td><td>

Guaranteed not to do anything. If specified, other arguments are ignored. Can be used to create a hotkey which does nothing, so pushing that key won't trigger Find-As-You-Type or anything else.

*Example:* `Set NOOP`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(no value)*</td><td>

Use the **NOSCRIPT** argument to prevent [script events](/Manual/scripting/script_add-ins/README.md) from firing in response to the Set command. Currently this only works with the `Set LISTERCMD=ToFront` command, to prevent the **[OnActivateLister](../../scripting_reference/scripting_events/onactivatelister.md)** event from being triggered.

*Example:* `Set LISTERCMD=ToFront NOSCRIPT`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<preset name\>*</td><td>

When used in conjunction with the **UTILITY** argument, this lets you open the Find/Duplicates/Synchronize panel and automatically load the specified preset.

*Example:* `Set UTILITY=Find,Toggle PRESET=WorkDocuments`
</td></tr><tr><td>
PROGRESSCMD</td><td>
/K</td><td>
minimize</td><td>

Sends a "minimize" command to all current progress dialogs. Any that are currently visible will be minimized.

*Example:* `Set PROGRESSCMD=minimize`
</td></tr><tr><td>
</td><td>
</td><td>
restore</td><td>
Sends a "restore" command to all progress dialogs. Any that are currently minimized will be restored to visibility.
</td></tr><tr><td>
</td><td>
</td><td>
show</td><td>
Brings all non-minimized progress dialogs to the front.
</td></tr><tr><td>
</td><td>
</td><td>
pause</td><td>
Sends a "pause" command to all progress dialogs. All running operations that support pause will be paused.
</td></tr><tr><td>
</td><td>
</td><td>
resume</td><td>
Sends a "resume" command to all progress dialogs. All paused operations will be resumed.
</td></tr><tr><td>
</td><td>
</td><td>
abort</td><td>

Sends an "abort" command to all progress dialogs. All running **and** queued operations will be aborted.
</td></tr><tr><td>
QUICKFILTER</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) and gives keyboard focus to the pattern field on it. Similar to pushing the \* key under the default keyboard configuration.

*Example:* `Set QUICKFILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the quick filter in the current source file display to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). This is the same filter edited by the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md). Files that do not match the pattern will be hidden from the display.

Normally, if the filter is already set to the specified pattern, it will be cleared, making the command work as a toggle automatically.

*Example:* `Set QUICKFILTER=\*.jpg`

You can prevent the automatic toggling by prefixing the pattern with "notoggle:".

*Example:* `Set QUICKFILTER="notoggle:Hello World.\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**!clear**</td><td>

Clears the quick filter pattern in the current file display. Note that this does not clear the **QUICKFILTERFLAGS** value, and so it's possible that files may remain filtered out even after the filter pattern is cleared. Use the **QUICKFILTERCLEAR** argument to clear the quick filter completely.

*Example:* `Set QUICKFILTER=!clear`
</td></tr><tr><td>
</td><td>
</td><td>

**!prev**</td><td>

Restores the previous quick filter in the current file display. By default the quick filter is cleared when changing folders (although this can be changed with the **Clear Quick filter automatically when changing folders** option on the **[File Displays / Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md)** page in Preferences). For example, you could assign a hotkey to restore the previous filter after having gone into a sub-directory and then back again to the parent.

*Example:* `Set QUICKFILTER=!prev`
</td></tr><tr><td>
QUICKFILTERCLEAR</td><td>
/S</td><td>

*(no value)*</td><td>

Clears the quick filter in the current source file display. Both the filter pattern and the flags are cleared. This does not affect filtering caused by folder options or the global filters in Preferences.

*Example:* `Set QUICKFILTERCLEAR`
</td></tr><tr><td>
QUICKFILTERFLAGS</td><td>
/O</td><td>

*(no value)*</td><td>

Resets and clears the quick filter flags in the current source file display. The flags are as listed below. Clearing the flags does not clear the filter pattern, so it's possible that files may remain filtered out even after the flags are cleared.

*Example:* `Set QUICKFILTERFLAGS`

Alternatively, use the **QUICKFILTERCLEAR** argument to clear the quick filter completely, both pattern and flags.
</td></tr><tr><td>
</td><td>
</td><td>

**set**</td><td>

When combined with other flags, ensures they are only ever turned on. Without **set** or **clear**, the other specified tags will be *toggled*, i.e. turned on if off and off if on.

*Example:* `Set QUICKFILTERFLAGS=set,showfiles`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

When combined with other flags, ensures they are only ever turned off. Without **set** or **clear**, the other specified tags will be *toggled*, i.e. turned on if off and off if on.

*Example:* `Set QUICKFILTERFLAGS=clear,showfiles`
</td></tr><tr><td>
</td><td>
</td><td>

**showfiles**</td><td>

Shows all files, even if they are hidden by the filter pattern. This does not override folder format or global filters.

*Example:* `Set QUICKFILTERFLAGS=showfiles`

Turning on **showfiles** will automatically turn off **hidefiles**.
</td></tr><tr><td>
</td><td>
</td><td>

**showdirs**</td><td>

Shows all folders, even if they are hidden by the filter pattern.

*Example:* `Set QUICKFILTERFLAGS=showdirs QUICKFILTER="a\*"`

Turning on **showdirs** will automatically turn off **hidedirs**.
</td></tr><tr><td>
</td><td>
</td><td>

**hidefiles**</td><td>

Hides all files, even if they match the filter pattern.

*Example:* `Set QUICKFILTERFLAGS=hidefiles`

Turning on **hidefiles** will automatically turn off **showfiles**, and also turns off **hidedirs** unless **set** is also specified.
</td></tr><tr><td>
</td><td>
</td><td>

**hidedirs**</td><td>

Hides all folders, even if they match the filter pattern.

*Example:* `Set QUICKFILTERFLAGS=hidedirs`

Turning on **hidedirs** will automatically turn off **showdirs**, and also turns off **hidefiles** unless **set** is also specified.
</td></tr><tr><td>
</td><td>
</td><td>

**disable**</td><td>

Temporarily disables the quick filter, leaving the filter pattern intact.

*Example:* `Set QUICKFILTERFLAGS=disable`
</td></tr><tr><td>
</td><td>
</td><td>

**flatviewon**</td><td>

Enables filtering of folders when in Flat View, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=flatviewon`
</td></tr><tr><td>
</td><td>
</td><td>

**flatviewoff**</td><td>

Disables filtering of folders when in Flat View, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=flatviewoff`
</td></tr><tr><td>
</td><td>
</td><td>

**regexpon**</td><td>

Turns on regular expressions (instead of wildcards), overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=regexpon`
</td></tr><tr><td>
</td><td>
</td><td>

**regexpoff**</td><td>

Turns off regular expressions (i.e. forces wildcards), overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=regexpoff`
</td></tr><tr><td>
</td><td>
</td><td>

**ignorediacriticson**</td><td>

Turns on the "ignore diacritics" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=ignorediacriticson`
</td></tr><tr><td>
</td><td>
</td><td>

**ignorediacriticsoff**</td><td>

Turns off the "ignore diacritics" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=ignorediacriticsoff`
</td></tr><tr><td>
</td><td>
</td><td>

**anywordon**</td><td>

Turns on the "match any word" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=anywordon`
</td></tr><tr><td>
</td><td>
</td><td>

**anywordoff**</td><td>

Turns off the "match any word" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=anywordoff`
</td></tr><tr><td>
</td><td>
</td><td>

**partialon**</td><td>

Turns on the "partial matching" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=partialon`
</td></tr><tr><td>
</td><td>
</td><td>

**partialoff**</td><td>

Turns off the "partial matching" option, overriding the global Preferences setting.

*Example:* `Set QUICKFILTERFLAGS=partialoff`
</td></tr><tr><td>
READONLY</td><td>
/K</td><td>

**on**</td><td>

Makes the current file display read-only. Currently this is only supported by Zip archives. When the file display is marked as read-only, attempts to modify the contents of the current Zip archive will fail. This command has no affect when not viewing a Zip archive.

*Example:* `Set READONLY=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Clears the read-only flag from the current file display. The **Open Zip files as read-only by default** option on the **[Zip & Other Archives / Zip Files](/Manual/preferences/preferences_categories/zip_and_other_archives/zip_file_options.md)** page in Preferences can make Zip archives read-only by default, and you can then use this command to make them writeable.

*Example:* `Set READONLY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the read-only flag on or off in the current file display.

*Example:* `Set READONLY=TOGGLE`
</td></tr><tr><td>
RECYCLEBINEMPTY</td><td>
/S</td><td>

*(no value)*</td><td>

This has no effect as a command - its only use is with the **@ifset** and **@icon** [command modifiers](/Manual/customize/creating_your_own_buttons/command_modifiers.md). It lets you test if the recycle bin is currently empty.

//<Example://>

    @ifset:RECYCLEBINEMPTY
    @confirm The recycle bin is 
     empty!
    @ifset:else
    Delete EMPTYRECYCLE
</td></tr><tr><td>
RELATIVEDATEGRAPHS</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Show graphs behind modified and created date and time columns** option on the [File Display Columns / Options](/Manual/preferences/preferences_categories/file_display_columns/options.md) page in Preferences. As this is a global setting, all currently open Listers will be affected.

*Example:* `Set RELATIVEDATEGRAPHS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Show graphs behind date columns** option.

*Example:* `Set RELATIVEDATEGRAPHS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Show graphs behind date columns** option on or off.

*Example:* `Set RELATIVEDATEGRAPHS=toggle`
</td></tr><tr><td>
RELATIVESIZEGRAPHS</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Show graphs behind size columns** option on the [File Display Columns / Options](/Manual/preferences/preferences_categories/file_display_columns/options.md) page in Preferences. As this is a global setting, all currently open Listers will be affected.

*Example:* `Set RELATIVESIZEGRAPHS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Show graphs behind size columns** option.

*Example:* `Set RELATIVESIZEGRAPHS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Show graphs behind size columns** option on or off.

*Example:* `Set RELATIVESIZEGRAPHS=toggle`
</td></tr><tr><td>
RELDIMENSIONOVERLAYS</td><td>
/K</td><td>

**on**</td><td>

Turns the display of thumbnails-mode relative dimension bars on. This modifies the **Overlay relative dimension bars** option on the **[File Display Modes / Thumbnails](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.md)** page in Preferences. As this is a global setting, all currently open Listers will be affected.

*Example:* `Set RELDIMENSIONOVERLAYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the display of thumbnails-mode relative dimension bars off.

*Example:* `Set RELDIMENSIONOVERLAYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the display of thumbnails-mode relative dimension bars on or off.

*Example:* `Set RELDIMENSIONOVERLAYS=toggle`
</td></tr><tr><td>
SAVEFORMAT</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the *Save Folder Format* dialog, which lets you save the [folder format](/Manual/basic_concepts/folder_options/README.md) in the source file display.

*Example:* `Set SAVEFORMAT`
</td></tr><tr><td>
</td><td>
</td><td>

**folder**</td><td>

Saves the folder format for the current folder (without displaying the *Save Folder Format* dialog). You can combine this with the **replace** and **subfolders** arguments, or with the **clear** argument.

*Example:* `Set SAVEFORMAT=folder`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Saves the current format for all folders (i.e. this makes it the new **User default** format). You can combine this with the **clear**, **replace** and **quiet** arguments.

*Example:* `Set SAVEFORMAT=all`
</td></tr><tr><td>
</td><td>
</td><td>

**favorite**</td><td>

Saves the current format as a **Favorite Format**. You can specify the format name using the **FORMAT** argument.

*Example:* `Set SAVEFORMAT=favorite FORMAT "My Fave Format"`
</td></tr><tr><td>
</td><td>
</td><td>

**subfolders**</td><td>

Use with the **folder** argument to save the folder format for the current folder and all sub-folders.

*Example:* `Set SAVEFORMAT=folder,subfolders`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

Use with the **folder** or **all** arguments to replace any existing folder formats within layouts and styles with the new format.

*Example:* `Set SAVEFORMAT=all,replace`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

Use with the **folder** argument to delete the saved format (if any) for the current folder.

*Example:* `Set SAVEFORMAT=folder,clear`

Use with the **all** argument to clear any existing saved folder formats (so that the new **User default** format will be used).

*Example:* `Set SAVEFORMAT=all,clear`

After clearing formats, you can tell a folder tab to re-evaluate the format for its current path via `Set FORMAT=!folder` or similar.
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Use with the **all** argument to suppress the warning dialog before replacing all existing folder formats.

*Example:* `Set SAVEFORMAT=all,replace,quiet`
</td></tr><tr><td>
SHOWEVERYTHING</td><td>
/K</td><td>

**on**</td><td>

Turns the *[Show Everything](/Manual/basic_concepts/searching_and_filtering/show_everything.md)* mode on in the source file display. This overrides any active filters and ensures that all files and folders are visible.

*Example:* `Set SHOWEVERYTHING=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the *Show Everything* mode off in the source file display.

*Example:* `Set SHOWEVERYTHING=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles Show Everything mode on or off.

*Example:* `Set SHOWEVERYTHING=toggle`
</td></tr><tr><td>
SHOWFILTERATTR</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the attributes show filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Show Filter / Attributes*.

*Example:* `Set SHOWFILTERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

Sets the attributes show filter in the source file display. Only files that have the specified attributes set will be displayed - all others will be hidden.

The *\<attributes\>* value is one or more of the following letters: **R** (read-only), **A** (archive), **H** (hidden), **S** (system), **E** (encrypted), **C** (compressed), **O** (offline), **I** (non-indexed), **P** (pinned). See [Changing Attributes](/Manual/file_operations/changing_attributes.md) for detailed descriptions.

*Example:* `Set SHOWFILTERATTR e`

If the specified attributes are already set as the filter, the filter will be cleared, making the command automatically act as a toggle. You can also specify two sets of attributes, and the command will alternate between them each time it is run.

*Example:* `Set SHOWFILTERATTR e,ra`
</td></tr><tr><td>
SHOWFILTERFILENAME</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the filename show filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Show Filter / Filename*.

*Example:* `Set SHOWFILTERFILENAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the filename show filter in the source file display to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Only files that match the pattern will be shown - all other files will be hidden from the display.

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the specified pattern is already set as the filter, it will be cleared, making the command work as a toggle automatically.

*Example:* `Set SHOWFILTERFILENAME \*.(doc\|xls)`
</td></tr><tr><td>
SHOWFILTERFOLDERATTR</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the folder attributes show filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Show Filter / Folder Attributes*.

*Example:* `Set SHOWFILTERFOLDERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

Sets the folder attributes show filter in the source file display. Only folders that have the specified attributes set will be displayed - all others will be hidden.

The *\<attributes\>* value is one or more of the following letters: **R** (read-only), **A** (archive), **H** (hidden), **S** (system), **E** (encrypted), **C** (compressed), **O** (offline), **I** (non-indexed), **P** (pinned). See [Changing Attributes](/Manual/file_operations/changing_attributes.md) for detailed descriptions.

*Example:* `Set SHOWFILTERFOLDERATTR o`

If the specified attributes are already set as the filter, the filter will be cleared, making the command automatically act as a toggle. You can also specify two sets of attributes, and the command will alternate between them each time it is run.

*Example:* `Set SHOWFILTERFOLDERATTR o,off`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Disables the separate folder attributes show filter. When the folder attributes filter is disabled, the regular attributes filter will apply to both files and folders.

*Example:* `Set SHOWFILTERFOLDERATTR off`
</td></tr><tr><td>
SHOWFILTERFOLDERS</td><td>
/O</td><td>

*(no value)*</td><td>

Clears the folders show filter in the source file display. This modifies the folder options for the current folder - the equivalent setting in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog is *Filters / Show Filters / Folder Names*.

*Example:* `Set SHOWFILTERFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Sets the folders show filter in the source file display to the specified [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md). Only folders whose name matches the pattern will be shown - all other folders will be hidden from the display.

The supplied pattern can be prefixed with **regex:** to specify the pattern is a regular expression.

If the specified pattern is already set as the filter, it will be cleared, making the command work as a toggle automatically.

*Example:* `Set SHOWFILTERFOLDERS "\* Reports \*"`
</td></tr><tr><td>
SHOWMILLIS</td><td>
/K</td><td>

**on**</td><td>

Turns on the display of milliseconds in file time columns. This controls the **Show milliseconds** option on the [File Display Columns / Options](/Manual/preferences/preferences_categories/file_display_columns/options.md) Preferences page. Note that seconds must also be displayed for this command to have any effect.

*Example:* `Set SHOWMILLIS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the display of milliseconds in file time columns.

*Example:* `Set SHOWMILLIS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the display of milliseconds on or off.

*Example:* `Set SHOWMILLIS=toggle`
</td></tr><tr><td>
SHOWSECONDS</td><td>
/K</td><td>

**on**</td><td>

Turns on the display of seconds in file time columns. This controls the **Show seconds** option on the [File Display Columns / Options](/Manual/preferences/preferences_categories/file_display_columns/options.md) Preferences page.

*Example:* `Set SHOWSECONDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the display of seconds in file time columns.

*Example:* `Set SHOWSECONDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the display of seconds on or off.

*Example:* `Set SHOWSECONDS=toggle`
</td></tr><tr><td>
SIDE</td><td>
/K</td><td>

**left**</td><td>

When tested as a condition, returns true if the command is on a [location bar toolbar](/Manual/basic_concepts/the_lister/navigation/file_display_border.md) attached to the left (or top) file display.

*Example:* `@<icon:copysourcedest_right,Set> SIDE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

True when attached to the right (or bottom) file display.

*Example:* `@<icon:copysourcedest_left,Set> SIDE=right`
</td></tr><tr><td>
SORTBY</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

[Sorts](/Manual/basic_concepts/sorting_and_grouping/README.md) the current file display by the specified column. The value must be one of the valid [column keywords](../../metadata_keywords/keywords_for_columns.md), and the column must also be displayed in the file display.

As well as the column keywords, **SORTBY** recognizes the special keyword synonyms **accessed**, **created**, **date, disksize, modified, path** and **size**. This lets you sort by date, size or path without needing to know the exact column that is displayed (e.g. the column could be **size**, **sizekb** or **sizerel** - but the sorting is the same in all cases, and `Set SORTBY=size` would work for any column).

It is possible to sort the list by multiple columns, by specifying more than one comma-separated keyword. You can also specify that the sort order for a particular column should be reversed by prefixing its keyword with a hyphen.

The `Set SORTBY` command can also be used to automatically add the specified columns to the file display (since a column needs to be displayed in the list in order to sort by it). Prefix the column with a **+** sign to enable this. If the column is not already in the list it will be added to the end of the existing columns. You can also specify the position where the column should be added if it doesn't already exist - see the description of the `Set COLUMNSADD` command for details on this.

*Example:* `Set SORTBY=picsize,-modified`  
*Example:* `Set SORTBY=+datetaken`
</td></tr><tr><td>
</td><td>
</td><td>

**sortlist**</td><td>

When used on a toolbar or menu, the command will turn into a dynamic list of available columns which can be sorted by.

*Example:* `Set SORTBY=sortlist`
</td></tr><tr><td>
SORTNAMEEXTSEPARATELY</td><td>
/K</td><td>

**on**</td><td>

Turns the **Sort name and extension separately** option on in the source file display. This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTNAMEEXTSEPARATELY=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the **Sort name and extension separately** option off.

*Example:* `Set SORTNAMEEXTSEPARATELY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Sort name and extension separately** option on or off in the current file display.

*Example:* `Set SORTNAMEEXTSEPARATELY=toggle`
</td></tr><tr><td>
SORTNEWFILES</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Sort newly created and copied files** option in the source file display. This modifies the **[folder format](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTNEWFILES=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Sort newly created and copied files** option in the source file display.

*Example:* `Set SORTNEWFILES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Sort newly created and copied files** option on or off in the source file display.

*Example:* `Set SORTNEWFILES=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the **Sort newly created and copied files** option for the source file display to the default setting from the [sorting](/Manual/preferences/preferences_categories/filtering_and_sorting/sorting.md) Preferences page.

*Example:* `Set SORTNEWFILES=reset`
</td></tr><tr><td>
SORTNUMERIC</td><td>
/K</td><td>

**on**</td><td>

Turns the **Numeric order filename sorting** option on in the source file display. This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTNUMERIC=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the **Numeric order filename sorting** option off.

*Example:* `Set SORTNUMERIC=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Numeric order filename sorting** option on or off in the current file display.

*Example:* `Set SORTNUMERIC=toggle`
</td></tr><tr><td>
SORTORDER</td><td>
/K</td><td>

**folders**</td><td>

Changes the sort order in the source file display so that folders are listed before files. This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTORDER=folders`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

Lists files before folders in the current file display.

*Example:* `Set SORTORDER=files`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

Sorts files and folders together in the current file display.

*Example:* `Set SORTORDER=mixed`
</td></tr><tr><td>
</td><td>
</td><td>

**cycle**</td><td>

Cycles through the three different ordering options in the current file display.

*Example:* `Set SORTORDER=cycle`
</td></tr><tr><td>
SORTREVERSE</td><td>
/K</td><td>

**on**</td><td>

Reverses the sort order in the current file display. If the list is only sorted by one column, the direction of that column sort is reversed. If multiple columns are selected for sorting, their directions are not altered but the overall result is reversed as the final step in the sorting.

This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTREVERSE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the reverse sort flag off for the current folder, restoring the sort order to normal.

*Example:* `Set SORTREVERSE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles reverse sort on or off in the current folder.

*Example:* `Set SORTREVERSE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**togglesmart**</td><td>

Toggles reverse sort on or off in the current folder. If used with the **SORTBY** argument on the same command line, this argument operates slightly differently to **toggle**. If the column specified for **SORTBY** is already sorted, the sort order will be reversed, but if the specified column is not already sorted, the sort order will not be reversed.

To illustrate this, imagine the list is currently sorted forwards by name, and the command `Set SORTBY=size SORTREVERSE=toggle` is run multiple times. The resulting sort orders after each iteration would be:

1.  Sorted by name, forwards
2.  Sorted by size, backwards
3.  Sorted by size, forwards

Contrast this with the command `Set SORTBY=size SORTREVERSE=togglesmart`:

1.  Sorted by name, forwards
2.  Sorted by size, forwards
3.  Sorted by size, backwards

*Example:* `Set SORTBY=desc SORTREVERSE=togglesmart`
</td></tr><tr><td>
SORTWORDS</td><td>
/K</td><td>

**on**</td><td>

Turns the \*\*Word sort \*\*option on in the source file display. This modifies the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** for the current folder.

*Example:* `Set SORTWORDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Word sort** option in the source file display.

*Example:* `Set SORTWORDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Word sort** option in the current folder.

*Example:* `Set SORTWORDS=toggle`
</td></tr><tr><td>
SOUNDS</td><td>
/K</td><td>

**on**</td><td>

Turns on the **Enable Sound Events** option on the **[Miscellaneous / Sounds](/Manual/preferences/preferences_categories/miscellaneous/sounds.md)** page in Preferences.

*Example:* `Set SOUNDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the **Enable Sound Events** option.

*Example:* `Set SOUNDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the **Enable Sound Events** option on or off.

*Example:* `Set SOUNDS=toggle`
</td></tr><tr><td>
SOURCE</td><td>
/K</td><td>

**left**</td><td>

Sets the left (or top) file display in a dual-display Lister to be the source.

*Example:* `Set SOURCE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Sets the right (or bottom) file display to be the source.

*Example:* `Set SOURCE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Sets the file display that currently has the input focus to be the source.

*Example:* `Set SOURCE=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the state (source/destination) of the left and right file displays.

*Example:* `Set SOURCE=toggle`
</td></tr><tr><td>
SPACING</td><td>
/K</td><td>

*\<item\>**:**\<value\>*</td><td>

Modifies the spacing of various user interface elements (those that can be changed by a [user interface spacing scheme](/Manual/preferences/preferences_categories/user_interface/spacing.md)).

You can specify one or more items, separated by commas, and provide either new absolute values or positive or negative deltas, for each item.

The item keywords are:  
**detailslinespacing**, **detailslinepadding**, **powerlinespacing**, **powerlinepadding**, **pathiconleft**, **pathiconright**, **pathlabelleft**, **pathlabelright**, **thumbnailspacingh**, **thumbnailspacingv**, **tilespacingh**, **tilespacingv**, **treepadding**, **toolbarspacingh**, **toolbarspacingv**, **dragdistance**, **dblclkdistance**.

*Example:* `Set SPACING detailslinespacing:+16,powerlinespacing:+16`  
*Example:* `Set SPACING tilespacingv:20,tilespacingh:32`
</td></tr><tr><td>
SPACINGSCHEME</td><td>
/O</td><td>

*(no value)*</td><td>

Generates a list of configured [user interface spacing schemes](/Manual/preferences/preferences_categories/user_interface/spacing.md). Selecting an item from the list will switch to that scheme.

*Example:* `Set SPACINGSCHEME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<scheme name\>*</td><td>

Switches to the specified UI spacing scheme.

*Example:* `Set SPACINGSCHEME=CouchFriendly`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

Resets to the default UI spacing values.

*Example:* `Set SPACINGSCHEME=!default`
</td></tr><tr><td>
STATE</td><td>
/K</td><td>

**source**</td><td>

Sets the currently active Lister to be the source. When a Lister becomes the source, the previous source (if any) becomes the destination, and the previous destination (if any) is turned off. In a dual-display Lister, this command has no effect, because the currently active file display is by definition already the source.

*Example:* `Set STATE=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Sets the currently active Lister to be the destination. In a dual-display Lister, this is equivalent to `Set SOURCE=toggle` - the source will become the destination and vice versa.

*Example:* `Set STATE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**lockoff**</td><td>

Locks the active Lister as off. When a Lister is locked off, clicking in it will not make it the source or destination - only another `Set STATE` command can unlock it. This command has no effect in a dual-display Lister.

*Example:* `Set STATE=lockoff`
</td></tr><tr><td>
STATUSBAR</td><td>
/K</td><td>

**on**</td><td>

Turns the [status bar](/Manual/basic_concepts/the_lister/status_bar.md) on in the active Lister.

*Example:* `Set STATUSBAR=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the status bar off in the active Lister.

*Example:* `Set STATUSBAR=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the status bar on or off in the active Lister.

*Example:* `Set STATUSBAR=toggle`
</td></tr><tr><td>
STATUSBARSTYLE</td><td>
/K</td><td>

**single**</td><td>

Sets the status bar style to one single status bar even in a dual-display Lister.

*Example:* `Set STATUSBARSTYLE=single`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

One single status bar, with a separate definition in dual-display mode.

*Example:* `Set STATUSBARSTYLE=dual`
</td></tr><tr><td>
</td><td>
</td><td>

**independent**</td><td>

Separate status bars for left/right file displays, with separate definitions for left and right.

*Example:* `Set STATUSBARSTYLE=independent`
</td></tr><tr><td>
</td><td>
</td><td>

**independentsame**</td><td>

Separate status bars for left/right file displays, with the same definition for both.

*Example:* `Set STATUSBARSTYLE=independentsame`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

Puts the status bar at the bottom of the Lister rather than at the bottom of the file display.

*Example:* `Set STATUSBARSTYLE=dual,bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**nobottom**</td><td>

Puts the status bar at the bottom of the file display rather than the bottom of the Lister.

*Example:* `Set STATUSBARSTYLE=independentsame,nobottom`
</td></tr><tr><td>
</td><td>
</td><td>

**glass**</td><td>

Enable glass when the status bar is at the bottom of the Lister.

*Example:* `Set STATUSBARSTYLE=bottom,glass`
</td></tr><tr><td>
</td><td>
</td><td>

**noglass**</td><td>

Disable glass when the status bar is at the bottom of the Lister.

*Example:* `Set STATUSBARSTYLE=bottom,single,noglass`
</td></tr><tr><td>
TABPOSITION</td><td>
/K</td><td>

**above**</td><td>

Set folder tabs in the current Lister to display above the file displays. This overrides the default folder tab position as configured on the **[Folder Tab Bar](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.md)** page in Preferences.

*Example:* `Set TABPOSITION=above`
</td></tr><tr><td>
</td><td>
</td><td>

**below**</td><td>

Folder tabs in the current Lister will display below the file displays.

*Example:* `Set TABPOSITION=below`
</td></tr><tr><td>
</td><td>
</td><td>

\*\*left \*\*</td><td>

Folder tabs will display to the left of the file displays.

*Example:* `Set TABPOSITION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Folder tabs will display to the right of the file display.

*Example:* `Set TABPOSITION=right`
</td></tr><tr><td>
</td><td>
</td><td>

**together**</td><td>

In a dual file display Lister, the folder tabs for each file display will display together (e.g. when set to above or below, a horizontal dual-display Lister would have the two folder tab bars together between the two file displays). This overrides the default setting configured on the **[Folder Tab Bar](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.md)** page in Preferences.

You can use this keyword by itself or in conjunction with one of the above positional arguments, to change both settings simultaneously.

*Example:* `Set TABPOSITION=above,together`
</td></tr><tr><td>
</td><td>
</td><td>

**apart**</td><td>

In a dual display Lister, folder tabs will be apart from each other (e.g. when set to above or below, a horizontal dual-display Lister would have tabs above the top file display and below the bottom file display).

*Example:* `Set TABPOSITION=apart`
</td></tr><tr><td>
</td><td>
</td><td>

**normal**</td><td>

In a dual display Lister the folder tab position will be as configured (e.g. when set to above, both tab bars would be above their respective displays).

*Example:* `Set TABPOSITION=above,normal`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

Resets the folder tab position in this Lister to the defaults as configured in Preferences.

*Example:* `Set TABPOSITION=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**save**</td><td>

Makes the changes made by this command permanent (and applies them to any other open Listers).

*Example:* `Set TABPOSITION=above,normal,save`
</td></tr><tr><td>
TABWIDTH</td><td>
/K</td><td>

*\<size\>*</td><td>

Set the width of the folder tab bar, if it is displayed to the left or right of the file display. (All `Set TABWIDTH` variants have no effect on the folder tab bar if it is above or below the file display.)

*Example:* `Set TABWIDTH=250`

The width you specify will normally be DPI scaled, but you can specify a negative number if you want an absolute pixel width without scaling:

*Example:* `Set TABWIDTH=-300`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

Auto-size the folder tab bar to fit the labels of the current tabs. (Similar to double-clicking the tab bar's splitter.)

*Example:* `Set TABWIDTH=auto`

When **auto** and **both** are combined, the two tab bars auto-size to an equal width, wide enough for both sides.

*Example:* `Set TABWIDTH=auto,both`

(If you want to auto-size both sides indepdently, run `Set TABWIDTH=auto,left` and then `Set TABWIDTH=auto,right`.)
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Specifies that you want to resize the tab bar for the *source* file display in a dual-display window. (This is usually implicit and does not need specifying, but can override which file display is affected by buttons on the File Display Toolbar.)

*Example:* `Set TABWIDTH=auto,source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Specifies that you want to resize the tab bar for the *destination* file display in a dual-display window.

*Example:* `Set TABWIDTH=auto,dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Specifies that you want to resize the tab bar for the *left* (or *top*) file display.

*Example:* `Set TABWIDTH=auto,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Specifies that you want to resize the tab bar for the *right* (or *bottom*) file display.

*Example:* `Set TABWIDTH=auto,right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Specifies that you want to resize the tab bars for both the *left* and *right* (or *top* and *bottom*) file displays at once.

*Example:* `Set TABWIDTH=300,both`

Combining **both** and **auto** will resize both sides to the maximum needed by either side. See **auto**, above, for more detail.
</td></tr><tr><td>
</td><td>
</td><td>

**thinnest**</td><td>

In a dual-display window, makes both tab bars the same width as the thinnest one.

*Example:* `Set TABWIDTH=thinnest`
</td></tr><tr><td>
</td><td>
</td><td>

**widest**</td><td>

In a dual-display window, makes both tab bars the same width as the widest one.

*Example:* `Set TABWIDTH=widest`
</td></tr><tr><td>
THUMBNAILLABELS</td><td>
/K</td><td>

**on**</td><td>

Turns the display of thumbnail labels on. This is a global setting - it modifies the state of the **Display labels** option on the **[File Display Modes / Thumbnails](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.md)** page in Preferences.

*Example:* `Set THUMBNAILLABELS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns thumbnail labels off.

*Example:* `Set THUMBNAILLABELS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles thumbnail labels on or off.

*Example:* `Set THUMBNAILLABELS=toggle`
</td></tr><tr><td>
THUMBNAILRATINGS</td><td>
/K</td><td>

**on**</td><td>

Turns the thumbnail overlay of rating stars on or off. This is a global setting - it modifies the state of the **Overlay rating** option on the **[File Display Modes / Thumbnails](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.md)** page in Preferences.

*Example:* `Set THUMBNAILRATINGS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the ratings overlay off.

*Example:* `Set THUMBNAILRATINGS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the ratings overlay on or off.

*Example:* `Set THUMBNAILRATINGS=toggle`
</td></tr><tr><td>
THUMBSTRETCH</td><td>
/K</td><td>

**reset**</td><td>

Turns off any override of the thumbnail stretch mode which the current folder format is applying. The stretch mode defined in Preferences for the current file display mode will then be used instead.

*Example:* `Set THUMBSTRETCH=reset`
</td></tr><tr><td>
</td><td>
</td><td>

*\<mode\>*</td><td>

Applies an override of the thumbnail stretch mode, via the current folder format.

Valid modes: **FitReduce**, **FitSmooth**, **FitPixelated**, **FillCropSmooth**, and **FillCropPixelated**.

While the override is in effect, all file display modes that can display thumbnails are affected, within the current folder tab only. (Sub-images in folder thumbnails are not affected.)

*Example:* `Set THUMBSTRETCH=FitPixelated`
</td></tr><tr><td>
TREE</td><td>
/K</td><td>

**on**</td><td>

Turns the folder tree on in the active Lister. In a dual-display Lister, the **Open second Folder Tree in dual display mode** option on the **[Folder Tree / Options](/Manual/preferences/preferences_categories/folder_tree/options.md)** page in Preferences controls whether a second tree opens automatically - if that option is off, you can use the **dual** keyword to force a second tree to open as well.

*Example:* `Set TREE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the folder tree off in the active Lister.

*Example:* `Set TREE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the folder tree on or off in the active Lister.

*Example:* `Set TREE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

Controls the left (or top) folder tree in a dual-display Lister.

*Example:* `Set TREE=left,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

Controls the right (or bottom) folder tree in a dual-display Lister.

*Example:* `Set TREE=right,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

In a dual-display Lister, controls both trees at once.

*Example:* `Set TREE=dual,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

Controls the folder tree that "belongs" to the source file display.

*Example:* `Set TREE=source,on`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

Controls the folder tree that belongs to the destination file display.

*Example:* `Set TREE=dest,toggle`
</td></tr><tr><td>
TREELOCK</td><td>
/K</td><td>

**on**</td><td>

Turns the folder tree lock on for the active Lister (or when there are two trees, for the source file display). This is equivalent to clicking the padlock icon in the folder tree's header, but can be used even if the tree header is turned off in Preferences. When the folder tree is locked it no longer changes selection automatically to follow the current source path.

*Example:* `Set TREELOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the folder tree lock off for the active Lister.

*Example:* `Set TREELOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the folder tree lock on and off.

*Example:* `Set TREELOCK=toggle`
</td></tr><tr><td>
TREESHOWPATHTOSEL</td><td>
/K</td><td>

**on**</td><td>

Turns the folder tree's **Highlight path to selected folder** option on. This is a global setting and so affects all Listers. When turned on, the additional options on the **[Folder Tree / Appearance](/Manual/preferences/preferences_categories/folder_tree/appearance.md)** Preferences page apply.

*Example:* `Set TREESHOWPATHTOSEL=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns tree path highlighting off.

*Example:* `Set TREESHOWPATHTOSEL=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles tree path highlighting on or off.

*Example:* `Set TREESHOWPATHTOSEL=toggle`
</td></tr><tr><td>
UTILITY</td><td>
/K</td><td>

**find**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in [Find Files](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) mode. The panel will open in its Simple or Advanced state, depending on which was used the last time the panel was closed.

*Example:* `Set UTILITY=find`
</td></tr><tr><td>
</td><td>
</td><td>

**findsimple**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in [Find Files](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) (Simple) mode.

*Example:* `Set UTILITY=findsimple`
</td></tr><tr><td>
</td><td>
</td><td>

**findadvanced**</td><td>

Displays the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md) in [Find Files](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) (Advanced) mode.

*Example:* `Set UTILITY=findadvanced`
</td></tr><tr><td>
</td><td>
</td><td>

**sync**</td><td>

Displays the utility panel in [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) mode.

*Example:* `Set UTILITY=sync`
</td></tr><tr><td>
</td><td>
</td><td>

**dupe**</td><td>

Displays the utility panel in [Duplicate File Finder](/Manual/additional_functionality/duplicate_file_finder.md) mode.

*Example:* `Set UTILITY=dupe`
</td></tr><tr><td>
</td><td>
</td><td>

**undo**</td><td>

Displays the utility panel showing the undo list (file operations that can be undone).

*Example:* `Set UTILITY=undo`
</td></tr><tr><td>
</td><td>
</td><td>

**filelog**</td><td>

Displays the utility panel showing the [file operations log](/Manual/file_operations/tracking_and_undoing_file_operations.md).

*Example:* `Set UTILITY=filelog`
</td></tr><tr><td>
</td><td>
</td><td>

**ftplog**</td><td>

Displays the utility panel showing the [FTP logs](/Manual/ftp/ftp_log.md).

*Example:* `Set UTILITY=ftplog`
</td></tr><tr><td>
</td><td>
</td><td>

**scriptlog**</td><td>

Displays the utility panel showing the "script log" page.

*Example:* `Set UTILITY=scriptlog`

(You may see **otherlog** used in older toolbars and commands. This still works but is deprecated.)
</td></tr><tr><td>
</td><td>
</td><td>

**email**</td><td>

Displays the utility panel showing the outgoing email log.

*Example:* `Set UTILITY=email`
</td></tr><tr><td>
</td><td>
</td><td>

**on**</td><td>

Turns the utility panel on in the active Lister.

*Example:* `Set UTILITY=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the utility panel off.

*Example:* `Set UTILITY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the utility panel on or off in the active Lister.

*Example:* `Set UTILITY=ftplog,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

Gives focus to the utility panel if it's open. If used with **toggle**, the utility panel will only be toggled closed if it has focus.

*Example:* `Set UTILITY=find,toggle,focus`
</td></tr><tr><td>
</td><td>
</td><td>

**expand**</td><td>

If the utility panel is in a shrunken state, this argument in conjunction with **toggle** will cause the panel to expand rather than close.

*Example:* `Set UTILITY=find,toggle,expand`
</td></tr><tr><td>
</td><td>
</td><td>

**noexpand**</td><td>

When used with **toggle** (or other keywords that turn the panel on), **noexpand** prevents the utility panel from being expanded if it was previously saved in a shrunken state. That is, it will turn on but remain shrunken.

*Example:* `Set UTILITY=find,toggle,noexpand`
</td></tr><tr><td>
VIEW</td><td>
/K</td><td>

*\<mode\>\[,\<mode\>\]*</td><td>

Changes the [view mode](/Manual/basic_concepts/the_lister/view_modes.md) in the current file display. The valid mode keywords are **largeicons**, **smallicons**, **list**, **details**, **power**, **thumbnails** and **tiles**.

You can specify two different view modes to create a command that toggles from one mode to the other. With this usage, you can append an asterisk (\*) to the view mode keyword to specify that the button should appear highlighted when in that mode.

The **cycle** keyword can be used to cycle through more than two modes.

*Example:* `Set VIEW=details,thumbnails`\*

Note that the change does not take place until after the whole command (not just this line) has completed. This usually does not matter, but does if you want to change the view mode and also save it as the folder's new format. Running `Set VIEW=thumbnails` and then `Set SAVEFORMAT=folder` in the same command will not work. However, you can combine them into a single line which will work correctly:

*Example:* `Set VIEW=thumbnails SAVEFORMAT=folder`
</td></tr><tr><td>
</td><td>
</td><td>

**cycle**</td><td>

Cycles through the view modes. If used by itself, this will cycle through all the available view modes - otherwise, combine with the appropriate view mode keywords to create a command that cycles through specific modes.

*Example:* `Set VIEW=largeicons,smallicons,details,cycle`
</td></tr><tr><td>
VIEWERTOOLBAR</td><td>
/O</td><td>

*\<name\>*</td><td>

This command lets you change which toolbar is used for the [Viewer Toolbar](/Manual/additional_functionality/viewing_images/viewer_keys_and_toolbar.md). If you don't specify a name the default Viewer Toolbar is selected.

*Example:* `Set VIEWERTOOLBAR "My Viewer Toolbar"`
</td></tr><tr><td>
VIEWPANE</td><td>
/K</td><td>

**on**</td><td>

Turns the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md) on in the currently active Lister.

*Example:* `Set VIEWPANE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns the viewer pane off in the active Lister.

*Example:* `Set VIEWPANE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the viewer pane on or off in the active Lister.

*Example:* `Set VIEWPANE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

Forces the viewer pane to horizontal layout when it is opened.

*Example:* `Set VIEWPANE=toggle,horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

Specifies vertical layout for the viewer pane.

*Example:* `Set VIEWPANE=on,vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

Toggles the layout of the viewer pane between vertical and horizontal.

*Example:* `Set VIEWPANE=togglelayout`
</td></tr><tr><td>
VIEWPANELOCK</td><td>
/K</td><td>

**on**</td><td>

Turns on the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md) lock in the current Lister. When the viewer pane lock is turned on, it will continue to display its current image even if the file selection is changed in the Lister.

*Example:* `Set VIEWPANELOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Turns off the viewer pane lock.

*Example:* `Set VIEWPANELOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles the viewer pane lock on or off.

*Example:* `Set VIEWPANELOCK=toggle`
</td></tr><tr><td>
VIEWPANESHELLICONS</td><td>
/K</td><td>

**on**</td><td>

Enables shell icons in the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md). See **[Preferences / Viewer / Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md) / Display shell icons**.

*Example:* `Set VIEWPANESHELLICONS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Disables shell icons in the viewer pane.

*Example:* `Set VIEWPANESHELLICONS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles shell icons in the viewer pane on or off.

*Example:* `Set VIEWPANESHELLICONS=toggle`
</td></tr><tr><td>
VIEWPANESHELLTHUMBS</td><td>
/K</td><td>

**on**</td><td>

Enables shell thumbnails in the [viewer pane](/Manual/basic_concepts/the_lister/viewer_pane.md). See **[Preferences / Viewer / Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md) / Display shell thumbnails**.

*Example:* `Set VIEWPANESHELLTHUMBS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

Disables shell thumbnails in the viewer pane.

*Example:* `Set VIEWPANESHELLTHUMBS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

Toggles shell thumbnails in the viewer pane on or off.

*Example:* `Set VIEWPANESHELLTHUMBS=toggle`
</td></tr><tr><td>
VIEWPANESIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*</td><td>

Adjusts the size of the viewer pane in the active Lister. The size is given as a percentage of the total size of the Lister, and applies in the appropriate dimension based on the current layout of the viewer pane (so for example, when the pane is horizontal this affects its height).

It is also possible to specify two separate sizes, and the command will toggle between them.

*Example:* `Set VIEWPANESIZE 25,50`
</td></tr></tbody>
</table>

