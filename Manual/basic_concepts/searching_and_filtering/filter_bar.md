# Filter Bar

The filter bar is a small text field that pops up at the bottom of the file display, and makes it easy to quickly filter the current file list. By default you press the asterisk (the \* key) to display the filter bar, although this key can be modified through the **[File Displays / Filter Bar](filter_bar.md)** Preferences page.

![](/Manual/images/media/filter_bar.png) 

The filter bar appears as soon as you press the activation key (\*) and you can continue typing immediately to begin filtering the list.

In the above screenshot, we have filtered the C:\Windows\System32 directory to show all files that end in **.msc**. You can see from the status bar that this resulted in 3,943 items being hidden from the display, leaving only 21 .msc files visible. The filter bar displays these statistics as well, in slightly more detail (it breaks the hidden item count into hidden files and hidden folders). The various icons on the filter bar are actually buttons that you can click to quickly enable or disable that element of the filter. From left to right, the filter bar elements are:

- ![](/Manual/images/media/filter_bar_-_displayed_files.png) **Displayed file count**: Shows the number of files that are displayed by the filter (i.e. those that aren't hidden). Click this icon to temporarily ***hide all*** files.
- ![](/Manual/images/media/filter_bar_-_displayed_folders.png) **Displayed folder count**: Shows the number of folders that are displayed by the filter. Click this icon to temporarily ***hide all*** folders.
- ![](/Manual/images/media/filter_bar_-_hidden_files.png) **Hidden file count**: Shows the number of files that are hidden by the filter. Click this icon to temporarily ***show all*** files.
- ![](/Manual/images/media/filter_bar_-_hidden_folders.png) **Hidden folder count**: Shows the number of folders that are hidden by the filter. Click this icon to temporarily ***show all*** folders.
- ![](/Manual/images/media/filter_bar_-_filter.png) **Filter**: Click this icon to temporarily disable the filter (all files and folders will be shown).
- ![](/Manual/images/media/filter_bar_-_close.png) **Close**: Click this to close the filter and restore the display of all items in the list. You can also press **Escape** to do this. (If you are editing a previously-set filter, the first time you push **Escape** it will reset the filter to how it was. Push **Escape** a second time to clear the filter entirely.)
- **Filter folders in Flat view**: When the file display you are filtering is in **[Flat View\*\* mode](../flat_view.md)** this option appears and lets you control whether the filter applies to folders or only to files. When a folder is filtered out of the display in Flat View mode, all files within that folder (and its sub-folders) are also filtered out. This behavior may or may not be desirable and it can be confusing to have a whole lot of files suddenly disappear unexpectedly, which is which this option is available (and off by default). The default state of this option can be changed by modifying the **flatview_folder_filters** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

The filter string uses the [standard pattern matching syntax](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).

By default, *partial matching* is used, which means the pattern you enter only has to match a sub-string of the filename. For example, the pattern **opus** will match **dopus.exe**. If you turn partial matching off through Preferences, the filter pattern must match the filename exactly (so, instead of just **opus** you would need to use **\*opus**\* to match **dopus.exe**). Note that if you explicitly add a \* at the start or end of the pattern then Opus will assume you do not wish to use partial matching even if it is switched on. This allows you the convenience of partial matching most of the time while still being able to filter by the start or end of things when you need to.

The **Show everything** option provides a quick toggle for the *[Show Everything](show_everything.md)* mode - a way to temporarily disable filters and display all files and folders in the current folder.

Other options that you can control through the [Preferences page](filter_bar.md) include when the filter bar should stay visible, and whether the filter is cleared automatically whenever you change folders, and whether to ignore diacritics (which means filtering on e would also show files containing **é**, for example.)

![](/Manual/images/media/filter_dropdown.png)

The drop-down attached to the filter field provides a quick way to filter on the various file types that are actually present in the current folder. As you turn extensions on in the drop-down list they are automatically added to the filter wildcard pattern. The drop-down will also list your [file type groups](/Manual/file_types/file_type_groups.md), which is a very quick way to quickly filter (for example) out everything that's not an image file.

The filter bar affects what is called the "quick filter". This filter is applied on top of the filters set via the [Folder Options](../folder_options/RAEDME.md) system, and the global filtering options on the **[Folders / Folder Display](/Manual/preferences/preferences_categories/folders/folder_display.md)** Preferences page. It doesn't override these filters - so any files hidden via these other methods will stay hidden no matter what the quick filter is set to. You can clear the quick filter at any time by pressing the **Escape** key. (If you are editing a previously-set filter, the first time you push **Escape** it will reset the filter to how it was. Push **Escape** a second time to clear the filter entirely.)

You can also use the [find-as-you-type](../the_lister/find-as-you-type_field.md) field to edit the quick filter (although it doesn't have the additional functionality the filter bar does). To do this you need to assign an activation key for the **Filter** mode on the **[File Displays / Find-As-You-Type](/Manual/preferences/preferences_categories/file_displays/fayt_and_filter_bar_keys.md)** Preferences page. See the documentation for the find-as-you-type field for more information on this.

If desired you can configure the file display to display a different background color whenever the quick filter is active, using the File display background settings on the **[Display / Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md)** page in Preferences.
