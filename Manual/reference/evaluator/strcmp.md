\<evalcmd\> StrCmp && int && Returns **0** if the strings are the same, **\< 0** if *string1* is less than *string2*, and **\> 0** if *string1* is greater than *string2*.&& string1 && string && First string to compare. && string2 && string && Second string to compare. && \[length\] && int && Number of characters to compare. By default the full lengths of the strings will be compared; shorter strings will be considered to be less than longer strings. && \[flags\] && string && The optional flags are:

|       |                                                               |
|-------|---------------------------------------------------------------|
| **c** | Consider case when performing the comparison (case-sensitive) |

\</evalcmd\>

Compares two strings. While you can compare strings using the **==**, **\<** and **\>** operators, using the **StrCmp** function lets you make the comparison case sensitive if desired. You can also choose the number of characters of each string to compare.

//<Example://>

    if (StrCmp(name, "backup-", 7) == 0) { ... } // name begins with "backup-"
