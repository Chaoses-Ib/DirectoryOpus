# Toolbar Filter Fields

The **file filter field** is a field that you can add to your toolbars that lets you filter the current file display. Normally it's recommended that you use the [filter bar](filter_bar.md) rather than the toolbar field, simply to save space on your toolbars, but if you prefer to have a filter field always visible adding it to your toolbars is straightforward.

##### Adding the file filter field to your toolbars

Use the **[Customize](/Manual/customize/README.md)** dialog to add the field to a toolbar - you'll find **File Filter Field** listed in the *File Lists* category on the [Commands](/Manual/customize/the_customize_dialog/commands.md) tab. Simply drag it from that list and drop it on your toolbars somewhere.

When you leave Customize mode you'll see the filter field appear.

##### Using the file filter field

The current filter string is displayed in the field - if you click in the field and edit this string, the displayed files in the list will update to reflect the new filter string.

![](/Manual/images/media/13/filter_field_1.png)

By default, the filter field edits the quick filter (the same as the [filter bar](filter_bar.md)). This filter is applied on top of the filters set via the [Folder Options](../folder_options/README.md) system, and the global filtering options on the **[Global Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.md)** Preferences page. It doesn't override these filters - so any files hidden via these other methods will stay hidden no matter what the quick filter is set to.

The drop-down list attached to the field contains (by default) an entry for every file type present in the current folder - this provides a quick way to filter on a specific file extension.

##### Clearing the filter

You can clear the quick filter at any time by pressing the <kbd>Esc</kbd> key.

##### Folder format filters rather than quick filter

<img src="/media/13/filter_field_2.png" class="align-right" data-query="?nolink" />If you click the icon on the left of the field, a pop-up menu opens that lets you configure exactly how the filter field behaves.

The **Files**, **Folders** and **Files and Folders** options let you set the field to control the [folder format](/Manual/basic_concepts/folder_options/README.md) filters rather than the quick field. When one of these options is chosen, the **Show** and **Hide** options also become available. These options work together to control exactly which of the folder format filters the field affects:

| Files | Folders | Show | Hide | Folder Format filter                    |
|-------|---------|------|------|-----------------------------------------|
| ✓     |         | ✓    |      | Show Filter / Filename                  |
|       | ✓       | ✓    |      | Show Filter / Folders                   |
| ✓     | ✓       | ✓    |      | both Show Filter / Filename and Folders |
| ✓     |         |      | ✓    | Hide Filter / Filename                  |
|       | ✓       |      | ✓    | Hide Filter / Folders                   |
| ✓     | ✓       |      | ✓    | both Hide Filter / Filename and Folders |

##### Other filter field options

- **Filter in Real Time**: The list in the current file display will be updated as you edit the filter. Normally this is preferable as you can see exactly how your filter is affecting the files that are displayed, but with a very large number of files you may find the real-time update a little slow - in this case, you can turn it off.
- **Partial Match**: The pattern you enter must only match a sub-string of a filename, rather than the entire filename. It is functionally equivalent to always putting asterisks around the string you enter (e.g. **\*cow**\* instead of **cow**), and in fact this is how this feature is implemented internally.
- **Auto-content**: Controls what is displayed in the drop-down list attached to the filter field. If auto-content is turned on the drop-down list contains a wildcard entry for every file type present in the current folder (as described above). If you turn this off the drop-down list instead displays a history of previously used filter patterns.
- **Clear Filters**: Clears all filters currently in force in the current file display (except for [global filters](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.md) from Preferences).
- **Clear History**: Clears the filter history that's displayed in the drop-down list (if auto-content is disabled).

##### Making configuration changes permanent

Changes you make to the behaviour of the filter field via the menu are not permanent - if you close the Lister and open a new one, the field will be reset to its default settings. You can change these defaults by [editing the definition of the filter field](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/filter_field_configuration.md).
