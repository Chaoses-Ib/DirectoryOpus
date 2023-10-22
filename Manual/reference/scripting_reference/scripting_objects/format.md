# Format

The **Format** object represents the current display format of a tab. It is obtained from the **[Tab](tab.md).format** property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| alpha_folders | *bool* | Returns **True** if folders are always sorted alphabetically, **False** if otherwise. |
| autosize | *bool* | Returns **True** if column width auto-sizing is enabled, **False** if otherwise. |
| checkboxes | *bool* | Returns **True** if [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) is turned on, **False** if otherwise. |
| columns | *collection:***[Column](column.md)** | Returns a collection of **[Column](column.md)** objects that represent all the individual columns currently added to the display. |
| format_explain | **[Vector](vector.md)**:*string* | Returns a **[Vector](vector.md)**of strings representing the explanation of the current folder format (the same text visible when hovering the mouse over the format lock icon in the status bar). |
| frozen | *int* | Returns the number of frozen columns. Columns are always frozen from the left so this also tells you which columns are frozen (if any). |
| getsizes | *string* | Returns a string that indicates the state of the option to automatically calculate folder sizes. The string returned will be one of *default*, *on* or *off*. |
| group_by | *string* | If grouping is enabled, returns the name of the column that the list is grouped by. |
| group_combine | *string* | Returns a string indicating the current group combining mode. Possible values are **normal**, **never** and **other**. |
| group_individual | *bool* | Returns **True** if the group combining mode is set to **Never combine**. Note that this option is deprecated, you should use **group_combine** instead. |
| group_reverse | *bool* | Returns **True** if the groups are sorted in reverse order. |
| hide_attr | *object:***[FileAttr](fileattr.md)** | Returns a **[FileAttr](fileattr.md)** object indicating the file attributes that are hidden (any items with these attributes set will be hidden from the display). |
| hide_dirs | *string* | Returns the wildcard pattern of folders that are hidden from the display. |
| hide_dirs_regex | *bool* | Returns **True** if the current **hide_dirs** pattern is using regular expressions. |
| hide_ext | *bool* | Returns **True** if filename extensions are hidden, or **False** if they are displayed. |
| hide_files | *string* | Returns the wildcard pattern of files that are hidden from the display. |
| hide_files_regex | *bool* | Returns **True** if the current **hide_files** pattern is using regular expressions. |
| hide_folder_attr | *object:***[FileAttr](fileattr.md)**  <br />or *string* | Returns a **[FileAttr](fileattr.md)** object indicating the folder attributes that are hidden (any folders with these attributes set will be hidden from the display). If the separate folder attribute filter is disabled this property will return the string **"off"**. |
| ignore_prefix | *string* | Returns the filename prefixes that are ignored when sorting the list. |
| locked | *bool* | Returns **True** if the folder format is locked in the tab. |
| manual_sort | *bool* | Returns **True** if [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is enabled. |
| manual_sort_name | *string* | If manual sorting is active, returns the name of the current sort order (if it has one). |
| manual_sort_order | *object:***[SortOrder](sortorder.md)** | If manual sort is active, returns a **[SortOrder](sortorder.md)** object which lets you query and change the sort order. |
| mix_type | *string* | Returns a string indicating the current file/folder mixing type. The string returned will be one of *mixed*, *files* (files first) or *dirs* (folders first). |
| name_ext | *bool* | Returns **True** if filenames and extensions are sorted separately. |
| numeric_name | *bool* | Returns **True** if numeric name sorting is enabled. |
| reverse_sort | *bool* | Returns **True** if the over-all sort order is reversed. |
| show_attr | *object:***[FileAttr](fileattr.md)** | Returns a **[FileAttr](fileattr.md)** object indicating the file attributes that are shown (only items with these attributes set will be shown in the display). |
| show_dirs | *string* | Returns the wildcard pattern of folders that are shown (only folders matching this pattern will be shown). |
| show_dirs_regex | *bool* | Returns **True** if the current **show_dirs** pattern is using regular expressions. |
| show_files | *string* | Returns the wildcard pattern of files that are shown. |
| show_files_regex | *bool* | Returns **True** if the current **show_files** pattern is using regular expressions. |
| show_folder_attr | *object:***[FileAttr](fileattr.md)**  <br />or *string* | Returns a **[FileAttr](fileattr.md)** object indicating the folder attributes that are shown (only folders with these attributes set will be shown in the display). If the separate folder attribute filter is disabled this property will return the string **"off"**. |
| sort_ext | *bool* | Returns **True** if the name column is sorted by filename extension rather than filename. |
| sort_field | *object:***[Column](column.md)** | Returns a **[Column](column.md)** object representing the current sort field. |
| thumb_size | *int* | Returns the custom thumbnail size, or 0 if no custom size is set. |
| thumb_stretch | *string* | If the format overrides the global thumbnail stretch mode, returns one of *FitReduce*, *FitSmooth*, *FitPixelated*, *FillCropSmooth*, or *FillCropPixelated*. Otherwise, returns *none*. |
| view | *string* | Returns the current [view mode](/Manual/basic_concepts/the_lister/view_modes.md) as a string. The returned string will be one of *large*\_*icons*, *small*\_*icons*, *list*, *details*, *power*, *thumbnails* or *tile.* |
| word_sort | *bool* | Returns **True** if word sorting is enabled. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Update | *none* | *none* | The first time a script accesses a particular **Format** object, a snapshot is taken of the tab's format. If the script then makes changes to that tab (e.g. it changes the sort field, etc), these changes will not be reflected by the object. To re-synchronize the object with the tab, call the **Format.Update** method. |

