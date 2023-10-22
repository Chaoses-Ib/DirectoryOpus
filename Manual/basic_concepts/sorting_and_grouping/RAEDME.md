# Sorting and Grouping

You can control the order files and folders are displayed in several different ways. The primary way is by defining the *sort order*. A file list can be sorted by any column that is currently displayed. You can also use [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) to arbitrarily arrange the contents of your folders.

In details and power mode, you can change the sort order by clicking the desired sort field in the column header. You can also display the column header in the other view modes, by turning on the *[File Displays / Options / Show sort header in icon modes](/Manual/preferences/preferences_categories/file_displays/file_display_options.md) option* in Preferences*.*

![](/Manual/images/media/column_header.png)

If the field you want to sort by is not currently displayed in the list, use the **[Folder Options](folder_options/RAEDME.md)** dialog to add the desired column. This applies even in the non-column based view modes - even if the column is not displayed, it must still be added to the folder format before you can sort by it.

Clicking on a field will sort the list by that field. If you click the same field again, the sort order will be reversed. You can go straight to the reverse order for the field by holding the **Shift** key down when you click it. You can sort by multiple fields (as shown in the image above) by holding the **Ctrl** key down. Select the first (primary) sort field by clicking normally, then hold the **Ctrl** key and click on the second field, third field, fourth field and so on. The direction for supplementary sort fields can be modified on an individual basis in the same way as for the primary field.

In the non-column based view modes, the easiest way to change the sort order is to right-click on the background of the file display (an empty area - or right-click on the status bar if you can't find an empty area) and select the desired sort field from the context menu. You can also use the **Folder Options** dialog to change the sort order. There are several other options in the **[Folder Options](folder_options/RAEDME.md)** dialog that affect the order of items in the list - for example, you can choose whether files should come before or after folders, or if the two should be mixed together.

Grouping lets you split the list of files into multiple groups (fairly obviously!). You can group by the same column that you sort by, or by a completely different column. Unlike sorting, the column you group by doesn't have to be currently displayed - although the grouping context menus described below will only display those columns that are currently enabled. To group by a non-displayed column you need to use the internal **[Set GROUPBY](/Manual/reference/command_reference/internal_commands/set.md)** command.

![](/Manual/images/media/grouping.png) 

In this screenshot, the list has been grouped by last modified date. Each group has a heading that identifies the content of the group and displays the number of items in the group. You can collapse (hide) or expand (reveal) the contents of the group by clicking the little ![](/Manual/images/media/group_expand.png) glyph (or with the keyboard, place the focus on the group header and press the **Cursor Left** key to collapse it, or **Cursor Right** to expand it).

To group (or ungroup) the list, right click on the column header (or, in a non-column based view mode, right-click an empty area of the file display or the status bar) and select the desired field from the **Group By** menu. You can also use the column header to set the grouping field by holding the **Alt** key down and clicking the desired field. If you click it a second time (with the **Alt** key down) the grouping direction will be reversed. Grouping can be disabled altogether by holding **Shift+Alt** and clicking any field in the header.

Clicking a group header will automatically select all files in that group. If you right-click a group header, a number of grouping-related commands are displayed in the context menu.

![](/Manual/images/media/group_context.png) 

**Collapse group** (or **Expand group**) lets you collapse (or expand) the group you clicked on. **Expand all groups** , **Collapse all groups** and **Collapse other groups** affect all groups at once.

As an alternative to the group appearance shown above (with headers separating each group vertically), the *Group* column can be added to the file display (via the **[Folder Options](folder_options/RAEDME.md)** dialog). When this column is present in a grouped file display, the column itself displays the headings, making for a much more compact display.

 

![](/Manual/images/media/grouping_old.png)        ![](/Manual/images/media/grouping_new.png) 

*Traditional group headings                                                                                     Group column*

The colors used for the *Group* column can be configured on the **[Display / Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md)** Preferences page. You can define different colors for source and destination file display if desired. You can also configure Opus to add the *Group* column automatically whenever the file display is grouped with the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md) / Add 'Group' column automatically when file display is grouped** option.

 

More:

[Manual Sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md)  
