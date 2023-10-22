# Toolbar Filter Fields

The **File Filter Field** is a field that you can add to your toolbars that lets you filter the current file display. Normally it's recommended that you use the [filter bar](filter_bar.md) rather than the toolbar field, simply to save space on your toolbars, but if you prefer to have a filter field always visible adding it to your toolbars is straightforward. Use the **[Customize](/Manual/customize/RAEDME.md)** dialog to add the field to a toolbar - you'll find the **File Filter Field** listed in the [View](/Manual/customize/the_customize_dialog/commands/view_category_pre-defined_commands.md) category on the [Commands](/Manual/customize/the_customize_dialog/commands/RAEDME.md) tab.

![](/Manual/images/media/filter_field_1.png)

When you leave Customize mode you'll see the filter field appear. The current filter string is displayed in the field - if you click in the field and edit this string, the displayed files in the list will update to reflect the new filter string. The drop-down list attached to the field contains (by default) an entry for every file type present in the current folder - this provides a quick way to filter on a specific file extension.

If you click the icon on the left of the field, a pop-up menu opens that lets you configure exactly how the filter field behaves.

![](/Manual/images/media/filter_field_2.png) 

By default, the filter field edits the quick filter (the same as the [filter bar](filter_bar.md)). This filter is applied on top of the filters set via the [Folder Options](../folder_options/RAEDME.md) system, and the global filtering options on the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md)** Preferences page. It doesn't override these filters - so any files hidden via these other methods will stay hidden no matter what the quick filter is set to. Note that you can clear the quick filter at any time by pressing the **Escape** key.

The **Files**, **Folders** and **Files and Folders** options let you set the field to control the Folder Options filters rather than the quick field. When one of these options is chosen, the **Show** and **Hide** options also become available. These options work together to control exactly which of the Folder Options filters the field affects:

![](/Manual/images/media/folder_options_-_tabs_-_filters.png)

- **Files** and **Show** - affects the **Show Filter / Filename** field
- **Folders** and **Show** - affects the **Show Filter / Folders** field
- **Files and Folders** and **Show** - affects both the **Show Filter / Filename** and **Folders** fields
- **Files** and **Hide** - affects the **Hide Filter / Filename** field
- **Folders** and **Hide** - affects the **Hide Filter / Folders** field
- **Files and Folders** and **Hide** - affects both the **Hide Filter / Filename** and **Folders** fields

The other options in the filter field menu are:

- **Filter in Real Time**: If this is enabled, the list in the current file display is updated as you edit the filter. Normally this is preferable as you can see exactly how your filter is affecting the files that are displayed, but with a very large number of files you may find the real-time update a little slow - in this case, you can turn it off.
- **Partial Match**: With this option enabled, the pattern you enter must only match a sub-string of a filename, rather than the entire filename. It is functionally equivalent to always putting asterisks around the string you enter (e.g. **\*cow**\* instead of **cow**), and in fact this is how this feature is implemented internally.
- **Auto-content**: This option controls what is displayed in the drop-down list attached to the filter field. If auto-content is turned on the drop-down list contains a wildcard entry for every file type present in the current folder (as described above). If you turn this off the drop-down list instead displays a history of previously used filter patterns.

The **Clear Filters** command clears all filters currently in force in the current file display (except for global filters from the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md)** Preferences page). The **Clear History** command clears the filter history that's displayed in the drop-down list (if auto-content is disabled).

Changes you make to the behaviour of the filter field via the menu are not permanent - if you close the Lister and open a new one, the field will be reset to its default settings. You can change these defaults by [editing the definition of the filter field](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/filter_field_configuration.md).
