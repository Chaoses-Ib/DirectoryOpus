\<evalcmd\> Truncate && string && The truncated string. && string && string && Input string to truncate. && length && int && Number of characters to truncate to. && \[type\] && int && Truncation type. Options are:

|     |                        |
|-----|------------------------|
| 0   | truncate on the right  |
| 1   | truncate on the left   |
| 2   | truncate in the middle |

\</evalcmd\>

Truncates the string to the specified number of characters.

If the truncation type isn't specified, the default is **2** if the input value is a *path* - otherwise the default is **0**.

If the input value is a *path* and middle truncation is selected, the function takes path separators into account correctly.

//<Example://>

    Output( Truncate("C:\Program Files\GPSoftware\Directory Opus\dopus.exe" as path, 32, 2) );
    --> C:\Program Files\GP...\dopus.exe
