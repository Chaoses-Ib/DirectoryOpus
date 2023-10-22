# Rename Modes

The top section of the Rename dialog is where you define the rename **mode** - which determines the way the two input fields, **old name** and **new name** are interpreted. 

![](/Manual/images/media/rename_mode.png)

Use the **mode** drop-down to select the rename mode.

- *[Standard Wildcard Rename](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/standard_wildcard_rename.md)*: enter a new name literally or rename using a simple wildcard system.
- *[Find And Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/find_and_replace.md)*: specify a text string to search for and another to replace it with (this works just like search and replace in a text editor).
- *[Regular Expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md)*: enter a new name literally or rename using a regular expressions search and replace.
- *[Regular Expressions + Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions_and_find_and_replace.md)*: enter a regular expression to search for and the text to replace it with (combines the above two modes).

The **reset** button provides a quick way to clear out the other fields of the Rename dialog and revert to a "blank slate".

The **old name** field specifies the input pattern that's applied to each old (original) filename. When renaming using wildcards or *Regular Expressions*, this field is used to specify the "from" or "search" pattern. When using *Find And Replace* mode this field specifies the find string.

The **new name **field specifies the output pattern that's applied to generate each new filename. When using *Find And Replace* mode this field specifies the replacement string.

The **case sensitive** option is used to specify case sensitive pattern matching or *Find And Replace* searching*.* When it's turned on, the upper/lower case of an existing filename has to match the supplied pattern exactly - for example, *"d\*"* won't match *"Dog"* if the **case sensitive** option is turned on.

The **ignore extension** option is used to totally exclude the file extension from the rename operation - if it's turned on, the file extension won't be modified, and you don't have to (and shouldn't) account for it in any wildcard patterns. You should normally leave this option enabled since it makes wildcards (particularly regular expressions) a lot simpler, and it's rare to need to modify filename extensions.

More:

[Standard Wildcard Rename](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/standard_wildcard_rename.md)  
[Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/find_and_replace.md)  
[Regular Expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.md)  
[Regular Expressions + Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions_and_find_and_replace.md)  
