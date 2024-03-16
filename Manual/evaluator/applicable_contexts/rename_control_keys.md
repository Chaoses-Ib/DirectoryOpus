# Rename Control Keys

The [Control Keys](/Manual/preferences/preferences_categories/file_operations/renaming_files/control_keys.md) Preferences page lets you define <kbd>Ctrl</kbd> key sequences for [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) that use the evaluator to select, replace or delete text, or to move the cursor.

The evaluation expression is called every time its defined key is pressed.

In this evaluation context, the following variables are available:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ dir \$\$ *bool* \$\$ **True** if the item being renamed is a directory, **false** for a file. \$\$ exthidden \$\$ *bool* \$\$ **True** if the filename extension is currently hidden. \$\$ is_dir \$\$ *bool* \$\$ **True** if the item being renamed is a directory, **false** for a file (same as *dir*). \$\$ file_name \$\$ *string* \$\$ Original name of the file. \$\$ name \$\$ *str* \$\$ Original name of the file. \$\$ nameext \$\$ *str* \$\$ Original filename extension of the file. \$\$ namestem \$\$ *str* \$\$ Original filename stem (i.e. without the extension). \$\$ path \$\$ *path* \$\$ Path the file is located in (does not include the filename). \$\$ selend \$\$ *int* \$\$ Current selection range end position. \$\$ selstart \$\$ *int* \$\$ Current selection range start position. \$\$ valext \$\$ *str* \$\$ Filename extension of the current value in the edit field. \$\$ valstem \$\$ *str* \$\$ Filename stem of the current value in the edit field. \$\$ valleft \$\$ *str* \$\$ The part of the current value to the left of the current selection range. \$\$ valright \$\$ *str* \$\$ The part of the current value to the right of the current selection range. \$\$ valsel \$\$ *str* \$\$ The part of the current value that is currently selected. \$\$ value \$\$ *str* \$\$ The current value in the edit field. \</commandtable\>

The evaluator has a function that's specific to this context - `RestoreExt()`. The expression can call this function to reveal the filename extension if its currently hidden from the edit field (i.e. if `exthidden` is **true**).

The evaluation expression can return a string to update the value in the edit field.

It can also modify the selection range by changing the values of the `selstart` and `selend` variables.

To update the selection range without changing the contents of the string, simply return `true` instead of a string.

It can also return `false` if it doesn't want to make any changes to the value or selection.
