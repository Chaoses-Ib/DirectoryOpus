# Sorting and Grouping

You can control the order files and folders are displayed in several different ways. The primary way is by defining the *sort order*. A file list can be sorted by any column that is currently displayed. You can also use [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) to arbitrarily arrange the contents of your folders.

### Columns must be turned on to sort by them

If the field you want to sort by is not currently displayed in the file display, use the **[Folder Format](folder_options/README.md)** dialog to add the desired column. This applies even in the non-column based view modes (e.g. *list mode*) - even if the column is not displayed, it must still be added to the folder format before you can sort by it.

### Sorting via the column header

In details and power mode, you can change the sort order by clicking the desired sort field in the column header. You can also display the column header in the other view modes, by turning on the *Show sort header in icon modes* option on the [File Displays / Options](/Manual/preferences/preferences_categories/file_displays/options/README.md) page in Preferences.

- Click a button in the column header to sort the list by that field
- Click the same button again to reverse the sort order
- Hold <kbd>Shift</kbd> when you click the header button to go straight to reverse order
- Right-click the column header to change the sort order via the context menu

![](/Manual/images/media/13/column_header.png)

The current sort field and direction (ascending or descending) is indicated in the column header by an arrow.

### Sorting by multiple fields

Using the column header, you can sort by multiple fields by holding the <kbd>Ctrl</kbd> key down. Select the first (primary) sort field by clicking normally, then hold the <kbd>Ctrl</kbd> key and click on the second field, third field, fourth field and so on.

![](/Manual/images/media/13/column_header_multi.png)

The image above shows a list sorted first by size and then by name.

When multiple column sorting is in effect, an additional arrow button appears on the left of the column header. This lets you reverse the overall sort order. The direction for each sort field can be modified on an individual basis by holding <kbd>Ctrl+Shift</kbd> and clicking the column header buttons for each field.

### Sorting without using the column header

If the column header isn't visible, the easiest way to change the sort order is to right-click on the background of the file display (an empty area - or right-click on the status bar if you can't find an empty area) and select the desired sort field from the context menu.

You can also use the [Folder Format](folder_options/README.md) dialog to change the sort order. There are several other options in the Folder Format dialog that affect the order of items in the list - for example, you can choose whether files should come before or after folders, or if files and folders should be mixed together.

### Grouping

Grouping lets you split the list of files into multiple groups. You can group by the same column that you sort by, or by a completely different column.

![](/Manual/images/media/13/grouping.png) 

In this screenshot, the list has been grouped by last modified date. Each group has a heading that identifies the content of the group and displays the number of items in the group.

### You can group by non-enabled fields

Unlike sorting, the column you group by doesn't have to be currently displayed - although the grouping context menus described below will only display those columns that are currently enabled.

To group by a non-displayed column you need to use the [Folder Format](folder_options/README.md) dialog, or the internal `Set GROUPBY` command.

### Grouping via the column header

To group (or ungroup) the list, right click on the column header and select the desired field from the **Group By** menu.

You can also hold <kbd>Alt</kbd> and click the column header button corresponding to the desired group field. If you click the button a second time (with the <kbd>Alt</kbd> key still down) the grouping direction will be reversed.

Grouping can be disabled altogether by holding <kbd>Shift+Alt</kbd> and clicking any field in the header.

### Grouping without using the column header

As with sorting, you can also control grouping from the file display context menu, or the Folder Format dialog.

### Working with groups

Basic group controls are:

- You can collapse (hide) or expand (reveal) the contents of a group by clicking the little arrow glyph to the left of the group label.
- With the keyboard, place the focus on the group header and press <kbd>Left</kbd> to collapse it, or <kbd>Right</kbd> to expand it.
- Clicking a group header will automatically select all files in that group.
- Right-clicking a group header selects all files in that group and then shows a context menu for them.

  
A number of grouping-related commands are added to the top of the context menu when you right-click a group header:

- **Collapse group**: Collapse the group you clicked on.
- **Expand group**: Expand a collapsed group.
- **Expand all groups**: Expand all collapsed groups.
- **Collapse all groups**: Collapse all groups that are currently expanded.
- **Collapse other groups**: Collapse all groups except the one you clicked on.

### Group column

As an alternative to the group appearance shown above (with headers separating each group vertically), the *Group* column can be added to the file display (via the **[Folder Format](folder_options/README.md)** dialog).

When this column is present in a grouped file display, the column itself displays the headings, making for a much more compact display.

![](/Manual/images/media/13/grouping_new.png) 

You can configure Opus to add the *Group* column automatically whenever the file display is grouped with the **Add 'Group' column automatically when file display is grouped** option on the [File Display Columns / Options](/Manual/preferences/preferences_categories/file_display_columns/options.md) Preferences page.

### Group colors

From the **[Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md)** Preferences page you can configure the colors used for group headers and also the *Group* column.

### Grouping schemes

Using the [Evaluator](/Manual/evaluator/README.md) you can define *grouping schemes*, which can alter or replace the default grouping logic for specific columns.

Grouping schemes are configured through the [Evaluator Groups](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.md) Preferences page.

More:  
[Manual Sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md)  
