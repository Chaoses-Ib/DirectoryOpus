# Filters

The **Hide Filters** and **Show Filters** tabs of the Folder Format dialog look identical. They can be used to control which files and folders are shown and which are hidden when the format is applied to a folder.

- The settings on the **Show Filters** tab causes items to be hidden if they **don't** match the filter.
- The settings on the **Hide Filters** tab causes items to be hidden if they **do** match.

The **File names** and **Folder names** fields both take a wildcard string expressed using either [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) or [regular expression syntax](/Manual/reference/wildcard_reference/regular_expression_syntax.md) (if the **Use regular expression** option is turned on).

The **Attributes** fields let you filter files and folders based on their attributes - if any of the selected attributes are set on the item, it will match the filter and be shown or hidden as applicable.

Both the Show and Hide Filters have the option of separate attribute filters for folders. If these separate filters are enabled, then the first **Attributes** field in each group only applies to files - otherwise, it applies to both files and folders.

These filters stack on top of the [global filters](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.md).

All filtering can be quickly disabled in a folder tab by toggling [Show Everything](../../searching_and_filtering/show_everything.md) mode.
