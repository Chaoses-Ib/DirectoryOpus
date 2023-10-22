\<evalcmd\> Exists && bool && **True** if the specified path exists, otherwise **false**. && path && path && Path to test for existence of. && \[flags\] && string && The optional flags are:

|       |                                               |
|-------|-----------------------------------------------|
| **w** | Support wildcards in the final path component |

\</evalcmd\>

Tests if the specified path exists (or optionally, if any file or folder matching the wildcard exists in the specified path).

//<Example://>

    if (Exists("c:\\log\\error*.txt", "w")) { ... }
