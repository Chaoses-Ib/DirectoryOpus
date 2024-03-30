# Filter Bar

The filter bar is a small text field that pops up at the bottom of the file display, and makes it easy to quickly filter the current file list. By default you press `*` to display the filter bar, although this key can be modified through the [File Displays / Quick Keys](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md) Preferences page.

![](/Manual/images/media/13/filter_bar.png) 

The filter bar appears as soon as you press the activation key and you can continue typing immediately to begin filtering the list.

##### Filtering the file display

In the above screenshot, we have filtered the `C:\Windows\System32` directory to show all files that end in `.msc`. You can see from the status bar that this resulted in 4,671 items being hidden from the display, leaving only 21 .msc files visible.

The filter bar displays these statistics as well, in slightly more detail (it breaks the hidden item count into hidden files and hidden folders).

The filter bar affects what is called the "quick filter". This filter is applied on top of the filters set via the [Folder Formats](../folder_options/README.md) system, and the global filtering options on the **[Global Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.md)** Preferences page. It doesn't override these filters - so any files hidden via these other methods will stay hidden no matter what the quick filter is set to.

##### Clearing the filter

To clear the filter, press <kbd>Esc</kbd> or click the X button on the filter bar.

By default the filter bar will disappear automatically when the filter is cleared, but there's an option on the [Filter Bar](/Manual/preferences/preferences_categories/filtering_and_sorting/filter_bar.md) Preferences page to keep it open all the time if you prefer.

##### Indicating when a quick filter is active

You can configure the file display to display a different background color whenever the quick filter is active, using the File display background settings on the **[Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md)** page in Preferences.

##### Quickly hiding or showing files and folders

The "file" and "folder" icons on the filter bar that show the file and folder totals are clickable:

- Click the first file / folder icons to temporarily **hide** all files / folders.
- Click the second file / folder icons to temporarily **show** all files / folders.

##### Filter options

![](/Manual/images/media/13/filter_bar_menu.png)

The options button shows a menu that lets you control how the filter is applied:

- **Ignore diacritics**: Ignore accent characters when filtering.
- **Match any word**: Activates "any word" mode, which works kind of like a search engine. A file will match if it contains any of the words you enter. You can prefix a word with `+`, which means it **must** be present, and `-` which means it **must not** be present.
- **Partial matching**: If this is turned on, words you enter only need to match part of a word to be considered a match. For example, searching for "quint" would match "quintuplet".
- **Use regular expression**: Lets you specify the search pattern using [regular expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md). If turned off, the pattern uses the [standard pattern matching syntax](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) instead.

Use the **Save as default** command to save the current settings as the defaults.

##### Filetype filtering

![](/Manual/images/media/13/filter_bar_filetypes.png)

The filetypes button shows a menu that lets you quickly filter by file extension or filetype group, based on the actual contents of the folder.

The top part of the menu refers to filetype groups - in this example, there is one file from the Documents group, five from the Images group, and so on.

The bottom part of the menu lists the file extensions that appear in the current folder.

Select a group or extension from the menu to quickly filter on that type (you can also select more than one at once).

##### Show everything

The **Show everything** option provides a quick toggle for the *[Show Everything](show_everything.md)* mode - a way to temporarily disable filters and display all files and folders in the current folder.

##### Filtering in Flat View

When the file display you are filtering is in [Flat View mode](../flat_view.md) the **Filter folders in Flat view** option appears.

This lets you control whether the filter applies to folders or only to files. When a folder is filtered out of the display in Flat View mode, all files within that folder (and its sub-folders) are also filtered out. This behavior may or may not be desirable and it can be confusing to have a whole lot of files suddenly disappear unexpectedly, which is which this option is available (and off by default).

The default state of this option can be changed by modifying the **flatview_folder_filters** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

##### Using the FAYT for quick filtering

You can also use the [find-as-you-type](../the_lister/find-as-you-type_field.md) field for quick filtering (although it doesn't have the additional functionality the filter bar does).

To do this you need to assign an activation key for the **Filter** mode on the **[Quick Keys](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md)** Preferences page. See the documentation for the find-as-you-type field for more information on this.
