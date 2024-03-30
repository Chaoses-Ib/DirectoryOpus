# Rename

You can use the evaluator in the [advanced rename](/Manual/file_operations/renaming_files/advanced_rename/README.md) tool to insert text returned by the evaluation.

Use the `{= ... =}` code to insert an evaluation expression. The return value of the expression is inserted into the new filename.

In this evaluation context, the following variables are available:

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

Additionally, the [rename-specific keywords](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md) like **parent** and **parentbase** are supported.
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>

Returns the full name of the file the expression is being run for. This may be different from **file** which (as a column keyword), returns the value of the *Name* column (which e.g. may have file extensions hidden).
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

**True** if the expression is being run for a folder, **false** if it's being run for a file.
</td></tr><tr><td>
oldname</td><td>

*str*</td><td>
The value of the "old name" field.
</td></tr><tr><td>
newname</td><td>

*str*</td><td>
The value of the "new name" field.
</td></tr></tbody>
</table>

The return value should be a *str* that will be inserted into the new filename.
