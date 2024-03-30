# Rename Control Keys

The [Control Keys](/Manual/preferences/preferences_categories/file_operations/renaming_files/control_keys.md) Preferences page lets you define <kbd>Ctrl</kbd> key sequences for [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) that use the evaluator to select, replace or delete text, or to move the cursor.

The evaluation expression is called every time its defined key is pressed.

In this evaluation context, the following variables are available:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dir</td><td>

*bool*</td><td>

**True** if the item being renamed is a directory, **false** for a file.
</td></tr><tr><td>
exthidden</td><td>

*bool*</td><td>

**True** if the filename extension is currently hidden.
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

**True** if the item being renamed is a directory, **false** for a file (same as *dir*).
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>
Original name of the file.
</td></tr><tr><td>
name</td><td>

*str*</td><td>
Original name of the file.
</td></tr><tr><td>
nameext</td><td>

*str*</td><td>
Original filename extension of the file.
</td></tr><tr><td>
namestem</td><td>

*str*</td><td>
Original filename stem (i.e. without the extension).
</td></tr><tr><td>
path</td><td>

*path*</td><td>
Path the file is located in (does not include the filename).
</td></tr><tr><td>
selend</td><td>

*int*</td><td>
Current selection range end position.
</td></tr><tr><td>
selstart</td><td>

*int*</td><td>
Current selection range start position.
</td></tr><tr><td>
valext</td><td>

*str*</td><td>
Filename extension of the current value in the edit field.
</td></tr><tr><td>
valstem</td><td>

*str*</td><td>
Filename stem of the current value in the edit field.
</td></tr><tr><td>
valleft</td><td>

*str*</td><td>
The part of the current value to the left of the current selection range.
</td></tr><tr><td>
valright</td><td>

*str*</td><td>
The part of the current value to the right of the current selection range.
</td></tr><tr><td>
valsel</td><td>

*str*</td><td>
The part of the current value that is currently selected.
</td></tr><tr><td>
value</td><td>

*str*</td><td>
The current value in the edit field.
</td></tr></tbody>
</table>

The evaluator has a function that's specific to this context - `RestoreExt()`. The expression can call this function to reveal the filename extension if its currently hidden from the edit field (i.e. if `exthidden` is **true**).

The evaluation expression can return a string to update the value in the edit field.

It can also modify the selection range by changing the values of the `selstart` and `selend` variables.

To update the selection range without changing the contents of the string, simply return `true` instead of a string.

It can also return `false` if it doesn't want to make any changes to the value or selection.
