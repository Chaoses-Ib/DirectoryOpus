# Filters

![](/Manual/images/media/image056.png)

The **Show Filters** and **Hide Filters** tabs of the Folder Options dialog look identical. They can be used to control which files and folders are shown and which are hidden when the format is applied to a folder. The settings on the **Show Filters** tab causes files to be hidden if they **don't** match the filter, and the settings on the **Hide Filters** tab causes files to be hidden if they **do** match.

The **File names** and **Folder names** fields both take a wildcard string expressed using either [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) or [regular expression syntax](/Manual/reference/wildcard_reference/regular_expression_syntax.md) (if the **Use regular expression** option is turned on).

The **Attributes** field lets you filter files and folders based on their attributes - if any of the selected attributes are set on the item, it will match the filter and be shown or hidden as applicable.

Both the Show and Hide Filters have the option of separate attribute filters for folders. If these separate filters are enabled, then the first **Attributes** field in each group only applies to files - otherwise, it applies to both files and folders.

In the screenshot above, the folder format is set to hide any files that end in **.ini** or **.bak**, and any folder called **.svn** (no wildcards are used for the folder name, so only that exact name will match). Any files marked as **Hidden** or **Offline** will also be hidden.

These filters stack on top of the [global filters](/Manual/preferences/preferences_categories/folders/global_filters.md).

All filtering can be quickly disabled in a folder tab by toggling [Show Everything](../../searching_and_filtering/show_everything.md) mode.
