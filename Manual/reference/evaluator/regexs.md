\<evalcmd\> RegExS && bool or string && Search or replacement result. && string && string && String to search. && pattern && string && Pattern to search for. && \[replace\] && string && Optional replace pattern. && \[pattern...\] && string && Optional additional search pattern... && \[replace...\] && string && Optional additional replace string... && \[0\] && value && Literal value 0. This is only needed in order to specify *flags* without *replace*. && \[flags\] && string && Optional flags are:

|       |                                                                          |
|-------|--------------------------------------------------------------------------|
| **c** | consider case when performing the operation (case-sensitive)             |
| **e** | if pattern doesn't match for a replace operation, return an empty string |

\</evalcmd\>

Performs a regular expression **search** in the provided string. The pattern does not need to match the string exactly.

If a *replace* pattern is **not** specified, this function returns **True** if the provided *string* contains the *pattern*, and otherwise returns **False**.

If a *replace* pattern is specified, the result of the replacement is returned. You can specify multiple *string/pattern* pairs, to perform multiple replacements at once. If the input string doesn't contain the pattern it is returned unchanged. You can also add **\#** to the end of each search pattern to repeat the search and replace as many times as possible (i.e. "replace all"). In the replacement string, use the \<ib:inline-code\>`\1`\</ib:inline-code\>, \<ib:inline-code\>`\2`\</ib:inline-code\>, ... syntax to refer to bracketed parts of the pattern.

The optional *flags* argument must be specified last. If no *replace* pattern is provided and you want to provide *flags*, you must pass a literal **0** for the third argument.

//<Example://>

    name = "FamilyPhoto.jpeg";

    Output(RegExS(name, "\.jpeg", ".jpg"));
    --> FamilyPhoto.jpg

    Output(RegExS(name, "(.+)Photo(.+)", "\1-Original\2"));
    --> Family-Original.jpeg

*See also:*  
[regex](regex.md)
