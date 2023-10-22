\<evalcmd\> InStr && int && Position of the match, or -1 for no match. && string && string && String to search. && search && string && String to search for. && \[start\] && int && Position to begin search at. If not specified the entire *string* is searched, otherwise:

- When searching forward, any match must start at or after *start*.
- When searching backward, any match must start (not end) at or before *start*.

&& \[flags\] && string && The optional flags are:

|       |                                                           |
|-------|-----------------------------------------------------------|
| **c** | Consider case when performing the search (case-sensitive) |
| **r** | Reverse search for the last match instead of the first    |
| **i** | Ignore diacritics                                         |
| **w** | Only match whole words                                    |
| **s** | Only match exactly at the specified *start* position      |

\</evalcmd\>

Returns the position that *search* was found within *string*, or **-1** if not found.

//<Example://>

    Output(InStr("The quick brown fox", "quick"))
    --> 4

*See also:*  
[count](count.md)  
