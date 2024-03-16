# Regular Expressions + Find and Replace

The *Regular Expressions + Find and Replace* mode lets you combine the power of the *Regular Expressions* mode with the simplicity of *Find and Replace*. Rather than having to construct a regular expression that matches the whole filename, and use `\1` style tags to preserve the parts of the old name that you want to keep, you can specify a regular expression to match a sub-string or part of the filename. Opus will replace any matching sub-strings with the new text you provide, and leave untouched any parts of the filename that didn't match.

![](/Manual/images/media/13/rename_-_regexpfindreplace.png)

The example above shows a very simple regular expression that has been used to remove the years from the original filenames.

The **Old name** pattern of `- \d+( - )*` matches the initial hyphen and space following it, then any number of digits, then optionally a subsequent hyphen surrounded by spaces. The replace string is left empty since we just want to remove the year - you could, of course, replace it with something else if you wanted.

See the [Regular Expression Syntax](/Manual/reference/wildcard_reference/regular_expression_syntax.md) reference page for more information about using regular expressions. Additional information can be found in  [Microsoft's introduction to TR1 ECMAScript](http://msdn.microsoft.com/en-us/library/bb982727.aspx) (the flavor of regular expressions that Opus uses by default) for more information, and you can ask on the [Opus Resource Centre](http://resource.dopus.com/) if you need help.
