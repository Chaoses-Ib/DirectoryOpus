# Label Assignments

This page shows a list of all files and folders that have [labels](/Manual/file_operations/labels.md) assigned to them. You can label files and folders using this interface; another way to do it is to use the *Set Label* command in the *Properties* drop-down on the default Operations toolbar. Note that if the label is stored in the file system (depending on the options on the [Options](options.md) page), they will not appear in this list.

The **New** dropdown lets you assign labels in a few ways:

- **File label**: Assign a label to a file by its path. That is, the label will be attached to the path and name of the file, not the file itself.
- **Folder label**: Lets you assign a label to a folder by its path. That is, the label will be attached to the path and name of the folder, not the folder itself.
- **Wildcard label**: Labels files and folders based on their names or locations. You can specify a pattern using standard [Opus wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) or [regular expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md), and choose whether to restrict the assignment to files, folders or both.
- **Filter label**: You can use [filters](/Manual/file_operations/filtered_operations/README.md) to assign labels based on attributes other than filename or location - they can be based on [any criteria supported by the filter system](/Manual/file_operations/filtered_operations/filter_clause_types.md), although you should keep in mind that the filter will be compared against every file in every directory you visit - potentially slow filter clauses like *Contains* should be used with caution.

By default filter and wildcard labels assignments will "stack" on top of each other. One label could change the color of an icon, and another could change the icon itself. You can use the **Stop on match** option on both wildcard labels and label filters to prevent this from happening.

Note that filter and wildcard label assignments can be rearranged to control their priority.

### Wildcard labels

![](/Manual/images/media/13/label_wildcard.png)

When creating a wildcard label, the following options are available:

- **Name**: You can assign a name to the filter, which will be shown in the list.
- **Wildcard**: The wildcard pattern to match. Turn on the **Use Regular Expression** option to use a regex. Wildcards here can also use the `grp:` syntax to match file extensions against members of a [file type group](/Manual/file_types/file_type_groups.md) (e.g. `grp:Images`).
- **Match Full Path**: Decides if the pattern needs to match the whole path or just the folder or file name at the end of the path. This doesn't matter for a wildcard like `*.(doc|docx)` for matching **.doc** and **.docx** files, since the extension is going to be at the end of both the full path and the name. It can matter with a wildcard like `A*.doc` where in full-path mode it would only match **.doc** files on **A:\\** whose names start with any letter, and in name-only mode it would match **.doc** files whose names start with the letter **A** in any drive or folder.
- **Type**: Select if you want to match files only, folders only, or both files and folders.
- **Label**: The actual label to assign to files that match the filter.
- **Stop on match**: If a file matches this wildcard, stop here and don't go on trying to match other wildcards as well.
