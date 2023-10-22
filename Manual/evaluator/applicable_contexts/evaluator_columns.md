# Evaluator Columns

The [Evaluator Columns](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.md) Preferences page lets you create columns that generate their contents using the evaluator.

When the column is displayed, the evaluation expression is invoked once per file or folder. In this evaluation context, the following variables are available:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ \<nobr\>*column name*\</nobr\> \$\$ *varies* \$\$ All the [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) are available as variables in this evaluation context.

Note that some keywords may use characters like a \`:\` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function. \$\$ is_dir \$\$ *bool* \$\$ **True** if the expression is being run for a folder, **false** if it's being run for a file. \</commandtable\>

The return value from the evaluation expression will be used as the data for the column. The way this value is shown in the column depends on the **Type** setting in the [column definition](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.md).
