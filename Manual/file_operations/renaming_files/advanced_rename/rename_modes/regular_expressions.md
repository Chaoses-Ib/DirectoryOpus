# Regular Expressions

The *Regular Expressions* mode lets you perform batch renaming using regular expressions to specify search and replace patterns.

![](/Manual/images/media/regular_expression_rename.png)

The example above shows a very simple regular expression that has been used to remove the underscore from the original filenames. The **Old name** pattern of *(.\*)\_(.\*)* uses parentheses to tag two "match anything" expressions, and the *\1\2* in the **New name** pattern inserts the values of the two tagged expressions in the new name.

An extension Directory Opus provides is the ability to perform a repeating search and replace using regular expressions. The above example will only remove a single underscore, but if you wanted to remove all underscores from the source name, you can append a \# (pound/hash) sign to the **Old name** pattern. This causes Opus to repeat the search and replace until the new filename no longer changes.

See the [Regular Expression Syntax](/Manual/reference/wildcard_reference/regular_expression_syntax.md) reference page for more information about using regular expressions. Additional information can be found in  [Microsoft's introduction to TR1 ECMAScript](http://msdn.microsoft.com/en-us/library/bb982727.aspx) (the flavor of regular expressions that Opus uses by default) for more information, and you can ask on the [Opus Resource Centre](http://resource.dopus.com/) if you need help.
