# Filters and Find

You can use the evaluator with filters (including the Find tool) in several ways:

- In the [filter control](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/RAEDME.md) you can define a [textual filter](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/textual_filters.md), and this uses the evaluator if it begins with \`=\`.
- Similarly, various commands let you define a textual filter from the command line (e.g. \`Find FILTERDEF\`), and these use the evaluator if they begin with \`=\`.
- If the [search field](/Manual/basic_concepts/searching_and_filtering/windows_search.md) is set to use Opus Find, you can enter an evaluation expression into it directly, beginning with a \`=\`.

  
The evaluation expression can be called in one of two modes:

- *Filter mode*: In this mode, the evaluation expression will be invoked once per file or folder to determine whether they match or are rejected by the filter.
- *Recurse mode*: In this mode, the expression will be invoked to determine whether the operation should recurse into that folder.

The special variable \`subfolder\` tells you which mode the expression is being called for. Handling the second mode is optional - if the expression never queries the value of the \`subfolder\`, Opus will simply recurse into all subfolders and won't call you in that mode again.

  
The variables available to the evaluator in this context are:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ \<nobr\>*column name*\</nobr\> \$\$ *varies* \$\$ All the [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) are available as variables in this evaluation context.

Note that some keywords may use characters like a \`:\` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function. \$\$ is_dir \$\$ *bool* \$\$ Returns **true** if the expression is being run for a folder, **false** if it's being run for a file. \$\$ subfolder \$\$ *bool* \$\$ Returns **true** if the expression is being called in *recurse mode*, **false** if it's being called in *filter mode*. \</commandtable\>

The return value from the evaluation expression depends on the mode it was called in, although in both cases it must return a *bool*:

- In *Filter mode* it should return **true** if the item matches the filter, or **false** if it doesn't match.
- In *Recurse mode* it should return **true** if Opus should recurse into the folder, or **false** if it should skip over it.
