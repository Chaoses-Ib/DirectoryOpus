# Generated File Names

The evaluator can be used to generate filenames in two different situations:

1.  When you make a copy of a file e.g. by pressing <kbd>Ctrl+C</kbd>,<kbd>Ctrl+V</kbd>.
2.  When you make a shortcut to a file or folder.

Opus will use your evaluator clause to generate a new filename both for the initial copy/shortcut, and subsequently when the desired filename is already in use.

The evaluator clauses for these are configured via Preferences:

1.  [File Operations / Copying Files / Copy of template](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)
2.  [File Operations / Options / Use template when creating shortcuts](/Manual/preferences/preferences_categories/file_operations/options.md)

To specify an evaluation clause, begin it with a `=` character. Your clause needs to return the new filename to use for the operation.

In this evaluation context, the following variables are available:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

Returns the generation count. For example, if you select a file and pressing <kbd>Ctrl+C</kbd>,<kbd>Ctrl+V</kbd>, `count` would initially be set to 0. If you press <kbd>Ctrl+V</kbd> again to make another copy of the same file, `count` would be set to 1. You would usually include the `count` in the generated filename itself to make the new filename unique.
</td></tr><tr><td>
ext</td><td>

*string*</td><td>
Returns the file extension of the file in question (if any). This is for informational purposes only and doesn't need to be added to the name of the generated filename (Opus will do that for you automatically).
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of the file or folder in question. The file extension (if any) is removed from this string.
</td></tr></tbody>
</table>

