\<evalcmd\> Match && bool && **True** if *string* matches the *pattern*. && string && string && String to compare. && pattern && string && Pattern to compare against. && \[flags\] && string && Optional flags are:

|       |                                                                   |
|-------|-------------------------------------------------------------------|
| **c** | consider case when performing the operation                       |
| **x** | simple matching against multiple file extensions                  |
| **d** | support DOS wildcard characters only                              |
| **r** | use regular expression                                            |
| **h** | easy handling for file paths (\\\\ and / are considered the same) |
| **a** | "any word" mode                                                   |
| **i** | ignore diacritics                                                 |
| **f** | support filetype groups                                           |
| **p** | partial matching                                                  |

\</evalcmd\>

Returns **True** if the input *string* matches the specified wildcard *pattern*. By default this uses [standard pattern matching](../wildcard_reference/pattern_matching_syntax.md) - specify the **r** flag to use [regular expressions](../wildcard_reference/regular_expression_syntax.md) instead.

//<Example://>

    if (Match(name, "*.txt")) { ... } // does file have a .txt extension?
