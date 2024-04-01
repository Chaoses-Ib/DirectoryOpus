# File Info Tips and Tiles

You can use the evaluator in the definitions for [file info tips](/Manual/file_types/filetype_editor/info_tip.md) and [tiles mode](/Manual/file_types/filetype_editor/tiles_mode.md) to insert text returned by the evaluation.

Use the `{= ... =}` code to insert an evaluation expression. The expression between the `{=` and the `=}` markers can span multiple lines if needed. The return value of the expression is inserted into the info tip or tile.

You can also implement hide sections using the evaluator - use `{!= ... =}` to open the hide section with an evaluation expression. If the expression returns **false**, everything within the hide section will be hidden. Close the hide section with `{!}` as normal.

In this evaluation context, the following variables are available:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

<nobr>*column name*</nobr></td><td>

*varies*</td><td>

All the [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) are available as variables in this evaluation context.

Note that some keywords may use characters like a `:` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function.

Additionally, the keywords **foldersize**, **foldercontents** and **infotip** are also supported.
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>

Returns the full name of the file the expression is being run for. This may be different from **file** which (as a column keyword), returns the value of the *Name* column (which e.g. may have file extensions hidden).
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

**True** if the expression is being run for a folder, **false** if it's being run for a file.
</td></tr></tbody>
</table>

The return value should either be a *str* for an insertion, or a *bool* for a hide section.

- If the expression is an insertion (using the `{= ... =}` code), the return value from the evaluation expression will be inserted into the info tip or tile at the point where the code appeared.
- If the expression is for a hide section (using the `{!= ... =}` code), it should return **true** to show the contents of the hide section, or **false** to hide them.
