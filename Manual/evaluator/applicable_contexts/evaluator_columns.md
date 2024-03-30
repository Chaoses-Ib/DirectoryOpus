# Evaluator Columns

The [Evaluator Columns](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.md) Preferences page lets you create columns that generate their contents using the evaluator.

When the column is displayed, the evaluation expression is invoked once per file or folder. In this evaluation context, the following variables are available:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

\<nobr\>*column name*\</nobr\></td><td>

*varies*</td><td>

All the [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) are available as variables in this evaluation context.

Note that some keywords may use characters like a `:` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function.
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>

Returns the full name of the file the column is being invoked for. This may be different from **file** which (as a column keyword), returns the value of the *Name* column (which e.g. may have file extensions hidden).
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

**True** if the expression is being run for a folder, **false** if it's being run for a file.
</td></tr><tr><td>
operation</td><td>

*string*</td><td>

Returns "sort" if the column is being used for sorting (in case you want to control the sort order). Returns "group" if the column is being used for grouping (the **Custom grouping** option must be enabled in the column definition). Otherwise returns "display".
</td></tr></tbody>
</table>

The return value from the evaluation expression will be used as the data for the column. The way this value is shown in the column depends on the **Type** setting in the [column definition](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.md).

Columns can control their sort order by returning a different value when they're being called to establish sort order. For example, your column might want to sort in proper date order (e.g. based on the `modifieddate` column) but return a text string for display. The `operation` value will be set to `"sort"` when the evaluation is being used for sorting.

Columns can also choose their default groups if the **Custom grouping** option is turned on in the column definition. The `operation` value will be set to `"group"` and you should return the name of the group you want the item placed in.
