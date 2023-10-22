\<evalcmd\> RegEx && bool or string && Match or replacement result. && string && string && String to match. && pattern && string && Pattern to match against. && \[replace\] && string && Optional replace pattern. && \[pattern...\] && string && Optional additional match pattern... && \[replace...\] && string && Optional additional replace string... && \[0\] && value && Literal value 0. This is only needed in order to specify *flags* without *replace*. && \[flags\] && string && Optional flags are:

|       |                                                              |
|-------|--------------------------------------------------------------|
| **c** | consider case when performing the operation (case-sensitive) |

\</evalcmd\>

Performs a regular expression **match** against the provided string. The pattern must match the string exactly.

If a *replace* pattern is **not** specified, this function returns **True** if the provided *string* matches the *pattern*, and otherwise returns **False**.

If a *replace* pattern is specified, the result of the replacement is returned. You can specify multiple *string/pattern* pairs, to perform multiple replacements at once. If the input string doesn't match the pattern it is returned unchanged. You can also add **\#** to the end of each search pattern to repeat the search and replace as many times as possible (i.e. "replace all").

The optional *flags* argument must be specified last. If no *replace* pattern is provided and you want to provide *flags*, you must pass a literal **0** for the third argument.

//<Example://>

    path = "C:\Projects\contoso_staging\2023\June";
    Output(RegEx(path, "(.*)_staging\\(.*)", "\1\\\2"));
    --> C:\Projects\contoso\2023\June

*See also:*  
[regexs](regexs.md)
