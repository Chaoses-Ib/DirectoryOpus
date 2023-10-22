# Evaluator Groups

The [Evaluator Groups](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.md) Preferences page lets you create your own file grouping schemes that extend or replace the built-in grouping rules.

When the file display is set to group using a grouping scheme, its evaluation expression is invoked once per file or folder. In this evaluation context, the following variables are available:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ \<nobr\>*column name*\</nobr\> \$\$ *varies* \$\$ Most [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) in the **Date and Time**, **Name and Path**, **File Size**, and \*\*General \*\* categories are available as variables in this evaluation context. Note that only basic information intrinsic to the file itself is provided - any columns referring to metadata that needs to be extracted from the file are not supported. \$\$ is_dir \$\$ *bool* \$\$ **True** if the expression is being run for a folder, **false** if it's being run for a file. \$\$ scheme \$\$ *str* \$\$ Contains the name of the grouping scheme. \$\$ value \$\$ *varies* \$\$ This provides the value that the item is being grouped by. Its type varies depending on the column selected for grouping. For example, if grouping by filename, \`value\` would be a *str* string type and contain the item's filename. \</commandtable\>

The return value from the evaluation expression defines the group the item will be placed into.

- If the group scheme uses static groups, this should be the group index (as an *int*) as shown in Preferences.
- If the group scheme uses dynamic groups, this should be the name of the group (as a *str*).

For dynamic groups you can also return a *value collection* which defines both the group name and the group order. This lets you have dynamic groups that are sorted other than alphabetically.

For example, say you wanted groups "A" and "B", but for some reason wanted group "B" to come first.

To place an item in group "B" you might do this:

    return [ name = "B"; order = 0; ];

And to place an item in group "A" you might do this:

    return [ name = "A"; order = 1; ];

Group "B" would be sorted before group "A" because its \`order\` value is lower.
