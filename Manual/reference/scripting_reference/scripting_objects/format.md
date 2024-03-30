# Format

The **Format** object represents the current display format of a tab. It is obtained from the **[Tab](tab.md).format** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
alpha_folders</td><td>

*bool*</td><td>

Returns **True** if folders are always sorted alphabetically, **False** if otherwise.
</td></tr><tr><td>
autosize</td><td>

*bool*</td><td>

Returns **True** if column width auto-sizing is enabled, **False** if otherwise.
</td></tr><tr><td>
checkboxes</td><td>

*bool*</td><td>

Returns **True** if [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) is turned on, **False** if otherwise.
</td></tr><tr><td>
columns</td><td>

*collection:***[Column](column.md)**</td><td>

Returns a collection of **[Column](column.md)** objects that represent all the individual columns currently added to the display.
</td></tr><tr><td>
format_explain</td><td>

**[Vector](vector.md)**:*string*</td><td>

Returns a **[Vector](vector.md)**of strings representing the explanation of the current folder format (the same text visible when hovering the mouse over the format lock icon in the status bar).
</td></tr><tr><td>
frozen</td><td>

*int*</td><td>
Returns the number of frozen columns. Columns are always frozen from the left so this also tells you which columns are frozen (if any).
</td></tr><tr><td>
getsizes</td><td>

*string*</td><td>

Returns a string that indicates the state of the option to automatically calculate folder sizes. The string returned will be one of *default*, *on* or *off*.
</td></tr><tr><td>
group_by</td><td>

*string*</td><td>
If grouping is enabled, returns the name of the column that the list is grouped by.
</td></tr><tr><td>
group_combine</td><td>

*string*</td><td>

Returns a string indicating the current group combining mode. Possible values are **normal**, **never** and **other**.
</td></tr><tr><td>
group_individual</td><td>

*bool*</td><td>

Returns **True** if the group combining mode is set to **Never combine**. Note that this option is deprecated, you should use **group_combine** instead.
</td></tr><tr><td>
group_reverse</td><td>

*bool*</td><td>

Returns **True** if the groups are sorted in reverse order.
</td></tr><tr><td>
hide_attr</td><td>

*object:***[FileAttr](fileattr.md)**</td><td>

Returns a **[FileAttr](fileattr.md)** object indicating the file attributes that are hidden (any items with these attributes set will be hidden from the display).
</td></tr><tr><td>
hide_dirs</td><td>

*string*</td><td>
Returns the wildcard pattern of folders that are hidden from the display.
</td></tr><tr><td>
hide_dirs_regex</td><td>

*bool*</td><td>

Returns **True** if the current **hide_dirs** pattern is using regular expressions.
</td></tr><tr><td>
hide_ext</td><td>

*bool*</td><td>

Returns **True** if filename extensions are hidden, or **False** if they are displayed.
</td></tr><tr><td>
hide_files</td><td>

*string*</td><td>
Returns the wildcard pattern of files that are hidden from the display.
</td></tr><tr><td>
hide_files_regex</td><td>

*bool*</td><td>

Returns **True** if the current **hide_files** pattern is using regular expressions.
</td></tr><tr><td>
hide_folder_attr</td><td>

*object:***[FileAttr](fileattr.md)**  
or *string*</td><td>

Returns a **[FileAttr](fileattr.md)** object indicating the folder attributes that are hidden (any folders with these attributes set will be hidden from the display). If the separate folder attribute filter is disabled this property will return the string **"off"**.
</td></tr><tr><td>
ignore_prefix</td><td>

*string*</td><td>
Returns the filename prefixes that are ignored when sorting the list.
</td></tr><tr><td>
locked</td><td>

*bool*</td><td>

Returns **True** if the folder format is locked in the tab.
</td></tr><tr><td>
manual_sort</td><td>

*bool*</td><td>

Returns **True** if [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is enabled.
</td></tr><tr><td>
manual_sort_name</td><td>

*string*</td><td>
If manual sorting is active, returns the name of the current sort order (if it has one).
</td></tr><tr><td>
manual_sort_order</td><td>

*object:***[SortOrder](sortorder.md)**</td><td>

If manual sort is active, returns a **[SortOrder](sortorder.md)** object which lets you query and change the sort order.
</td></tr><tr><td>
mix_type</td><td>

*string*</td><td>

Returns a string indicating the current file/folder mixing type. The string returned will be one of *mixed*, *files* (files first) or *dirs* (folders first).
</td></tr><tr><td>
name_ext</td><td>

*bool*</td><td>

Returns **True** if filenames and extensions are sorted separately.
</td></tr><tr><td>
numeric_name</td><td>

*bool*</td><td>

Returns **True** if numeric name sorting is enabled.
</td></tr><tr><td>
reverse_sort</td><td>

*bool*</td><td>

Returns **True** if the over-all sort order is reversed.
</td></tr><tr><td>
show_attr</td><td>

*object:***[FileAttr](fileattr.md)**</td><td>

Returns a **[FileAttr](fileattr.md)** object indicating the file attributes that are shown (only items with these attributes set will be shown in the display).
</td></tr><tr><td>
show_dirs</td><td>

*string*</td><td>
Returns the wildcard pattern of folders that are shown (only folders matching this pattern will be shown).
</td></tr><tr><td>
show_dirs_regex</td><td>

*bool*</td><td>

Returns **True** if the current **show_dirs** pattern is using regular expressions.
</td></tr><tr><td>
show_files</td><td>

*string*</td><td>
Returns the wildcard pattern of files that are shown.
</td></tr><tr><td>
show_files_regex</td><td>

*bool*</td><td>

Returns **True** if the current **show_files** pattern is using regular expressions.
</td></tr><tr><td>
show_folder_attr</td><td>

*object:***[FileAttr](fileattr.md)**  
or *string*</td><td>

Returns a **[FileAttr](fileattr.md)** object indicating the folder attributes that are shown (only folders with these attributes set will be shown in the display). If the separate folder attribute filter is disabled this property will return the string **"off"**.
</td></tr><tr><td>
sort_ext</td><td>

*bool*</td><td>

Returns **True** if the name column is sorted by filename extension rather than filename.
</td></tr><tr><td>
sort_field</td><td>

*object:***[Column](column.md)**</td><td>

Returns a **[Column](column.md)** object representing the current sort field.
</td></tr><tr><td>
thumb_size</td><td>

*int*</td><td>
Returns the custom thumbnail size, or 0 if no custom size is set.
</td></tr><tr><td>
thumb_stretch</td><td>

*string*</td><td>

If the format overrides the global thumbnail stretch mode, returns one of *FitReduce*, *FitSmooth*, *FitPixelated*, *FillCropSmooth*, or *FillCropPixelated*. Otherwise, returns *none*.
</td></tr><tr><td>
view</td><td>

*string*</td><td>

Returns the current [view mode](/Manual/basic_concepts/the_lister/view_modes.md) as a string. The returned string will be one of *large*\_*icons*, *small*\_*icons*, *list*, *details*, *power*, *thumbnails* or *tile.*
</td></tr><tr><td>
word_sort</td><td>

*bool*</td><td>

Returns **True** if word sorting is enabled.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

The first time a script accesses a particular **Format** object, a snapshot is taken of the tab's format. If the script then makes changes to that tab (e.g. it changes the sort field, etc), these changes will not be reflected by the object. To re-synchronize the object with the tab, call the **Format.Update** method.
</td></tr></tbody>
</table>

