# Folder Options

The Folder Options dialog is used to change the appearance and presentation of the files currently displayed in the file display (this is known as the *[folder format](/Manual/basic_concepts/folder_options/folder_formats.md)*). It includes things like the [view mode](the_lister/view_modes.md) (icons, thumbnails, details, etc), the columns shown (in details and power mode), the [sort and grouping options](sorting_and_grouping/RAEDME.md), filters that can hide or show files and folders based on wildcard patterns and other options that affect the display of the file list.

There are a number of other ways that the display can be modified that don't require using the [Folder Options dialog](/Manual/basic_concepts/folder_options/folder_options_dialog/RAEDME.md), which are worth mentioning at this point:

- In details and power mode (and optionally the other modes), you can change the sort order by clicking the desired sort field in the column header. Clicking on a field will sort the list in the default order for that field. The default order can be changed for individual fields on the [Fields](/Manual/preferences/preferences_categories/display/fields.md) page in preferences. If you click the same field again, the sort order will be reversed.

You can go straight to the reverse order for the field by holding the **Shift** key down when you click it. For the **Name** column only, **Shift**-clicking the column puts it into a special mode that lets you sort by file extension as well as by name. When the **Name** column is sorted by extension rather than name, the sort arrow will change to point to the left or right:

![](/Manual/images/media/sort_by_extension.png) (*sorted by file extension*)

You can sort by multiple fields (as shown in the image below) by holding the **Ctrl** key down. Select the first (primary) sort field by clicking normally, then hold the **Ctrl** key and click on the second field, third field, fourth field and so on. The direction for supplementary sort fields can be modified on an individual basis in the same way as for the primary field.

![](/Manual/images/media/column_header.png)

You can also use the column header to set the [grouping](sorting_and_grouping/RAEDME.md) field by holding the **Alt** key down and clicking the desired field. If you click it a second time (with the **Alt** key down) the grouping direction will be reversed. Grouping can be disabled altogether by holding **Shift+Alt** and clicking any field in the header.

The column header also displays a [context menu](/Manual/customize/the_customize_dialog/context_menus.md) if you click it with the right button. By default this menu contains a list of columns that can be displayed in the lister, and you can turn individual columns on and off using this menu. You can also change the sorting and grouping options using the context menu, as well as access the Folder Options dialog.

If [manual sorting](sorting_and_grouping/manual_sorting.md) is enabled, an additional button is shown in the column header letting you control the manual sort options.

![](/Manual/images/media/image030.png)

The column header is always displayed in details and power modes. You can display the column header in the other view modes, by turning on the *[File Displays / Options / Show sort header in icon modes](/Manual/preferences/preferences_categories/file_displays/file_display_options.md) option* in Preferences*.*

- In all view modes, you can right-click on the background (any empty area that's not a file or folder) of the file display to display the Lister [context menu](/Manual/customize/the_customize_dialog/context_menus.md). By default this context menu contains sub-menus like **View** (change view mode, and access Folder Options), **Sort By** (change sort field) and **Group By** (change grouping field). If you can't find an empty area in the file display (because you have full-row selection enabled, for instance) you can also right-click on the status bar.

- There are a number of drop-down menus on the default toolbars that can affect the file display.

The **View** menu contains options to change the current view mode, sort field and grouping field.  
The **Folder** menu contains options to access your [favorite folder formats](/Manual/preferences/preferences_categories/folders/folder_formats/RAEDME.md) (which can instantly change multiple file display parameters) and also gives you a way to access the Folder Options dialog.  
The **Lister** menu displays a list of your configured [lister styles](the_lister/styles.md), which as well as doing things like opening the viewer or closing the tree are also able to change the folder format.   
When you make a change to the file display with the Folder Options dialog, the changes you make will persist in that file display until something else changes them (either you making another manual change, or an automatic change triggered by the [Folder Formats system](/Manual/basic_concepts/folder_options/folder_formats.md).

More:

[Folder Options Dialog](/Manual/basic_concepts/folder_options/folder_options_dialog/RAEDME.md)  
[Folder Formats](/Manual/basic_concepts/folder_options/folder_formats.md)  
[Content Types](/Manual/basic_concepts/folder_options/content_types.md)  
[Locking the Format](/Manual/basic_concepts/folder_options/locking_the_format.md)  
[Identifying the current format](/Manual/basic_concepts/folder_options/identifying_the_current_format.md)  
