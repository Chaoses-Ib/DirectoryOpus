# Filters and Find

You can use the evaluator with filters (including the Find tool) in several ways:

- In the [filter control](/Manual/file_operations/filtered_operations/README.md) you can define a [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md), and this uses the evaluator if it begins with `=`.
- Similarly, various commands let you define a textual filter from the command line (e.g. `Find FILTERDEF`), and these use the evaluator if they begin with `=`.
- If the [search field](/Manual/basic_concepts/searching_and_filtering/windows_search.md) is set to use Opus Find, you can enter an evaluation expression into it directly, beginning with a `=`.
- (Opus 13.3.4 and above) Quick filters (via the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) or [FAYT field](/Manual/basic_concepts/the_lister/find-as-you-type_field.md)) can run evaluator code directly, and they can also invoked pre-defined filters and pass arguments to them if they use evaluator code.

  
The evaluation expression can be called in one of three modes:

- *Filter mode*: In this mode, the evaluation expression will be invoked once per file or folder to determine whether they match or are rejected by the filter.
- *Recurse mode*: In this mode, the expression will be invoked to determine whether the operation should recurse into that folder.
- *Quick filter mode*: The expression is invoked once per file or folder to determine if it should be shown in the file display or not.

The special variables `subfolder` and `quick_filter` tell you which mode the expression is being called for. Handling recurse mode (when `subfolder` is true) is optional - if the expression never queries the value of the `subfolder` value, Opus will simply recurse into all subfolders and won't call you in that mode again.

  
The variables available to the evaluator in this context are:

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
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>

Returns the full name of the file the filter is being run for. This may be different from **file** which (as a column keyword), returns the value of the *Name* column (which e.g. may have file extensions hidden).
</td></tr><tr><td>
filter_args</td><td>

*string*</td><td>

In *quick filter mode*, this returns the value of the argument string that follows the pre-defined filter name in the quick filter. For example a quick filter of `?bigfiles:5` would invoke a filter called "bigfiles", and (if it was an evaluation filter) pass it the value "5" in this variable.
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

Returns **true** if the expression is being run for a folder, **false** if it's being run for a file.
</td></tr><tr><td>
opt_anyword</td><td>

*bool*</td><td>

In *quick filter mode*, returns **true** if the "any word" option is enabled.
</td></tr><tr><td>
opt_ignore</td><td>

*bool*</td><td>

In *quick filter mode*, returns **true** if the "ignore diacritics" option is enabled.
</td></tr><tr><td>
opt_partial</td><td>

*bool*</td><td>

In *quick filter mode*, returns **true** if the "partial match" option is enabled.
</td></tr><tr><td>
opt_regex</td><td>

*bool*</td><td>

In *quick filter mode*, returns **true** if the "regular expression" option is enabled.
</td></tr><tr><td>
quick_filter</td><td>

*bool*</td><td>

Returns **true** if the expression is being called for a quick filter.
</td></tr><tr><td>
subfolder</td><td>

*bool*</td><td>

Returns **true** if the expression is being called in *recurse mode*.
</td></tr></tbody>
</table>

The return value from the evaluation expression depends on the mode it was called in, although in all cases it must return a *bool*:

- In *Filter mode* it should return **true** if the item matches the filter, or **false** if it doesn't match.
- In *Recurse mode* it should return **true** if Opus should recurse into the folder, or **false** if it should skip over it.
- In *Quick filter mode* it should return **true** if the item should be shown, or **false** if it shoudl be hidden.
