\<evalcmd\> MakeLegal && string && Processed string. && string && string && Input string. && \[flags\] && string && Optional flags are:

|       |                                                                                |
|-------|--------------------------------------------------------------------------------|
| **f** | forward slashes: convert separators to **/** instead of **\\**                 |
| **n** | name instead of path: replace separators with **\_** (implies **s**)           |
| **s** | subdirectory mode: replace **:** with **;** and remove **\\\\** from UNC paths |

\</evalcmd\>

Returns *string* with any illegal path characters removed or replaced.

//<Example://>

    Output( MakeLegal("*File<?>Name*.txt") )
    --> #File(!)Name#.txt

    Output( MakeLegal("C:\Program Files", "n") )
    --> C;_Program Files

    Output( MakeLegal("\\Server\\Share", "sf") )
    --> Server/Share
