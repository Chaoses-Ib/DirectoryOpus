\<evalcmd\> MakeLegal && string && Processed string. && string && string && Input string. && \[flags\] && string && Optional flags are:

|       |                                                                                                                                                                                       |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **f** | forward slashes: convert separators to \<ib:inline-code\>`/`\</ib:inline-code\> instead of \<ib:inline-code\>`\`\</ib:inline-code\>                                                   |
| **n** | name instead of path: replace separators with \<ib:inline-code\>`_`\</ib:inline-code\> (implies **s**)                                                                                |
| **s** | subdirectory mode: replace \<ib:inline-code\>`:`\</ib:inline-code\> with \<ib:inline-code\>`;`\</ib:inline-code\> and remove \<ib:inline-code\>`\\`\</ib:inline-code\> from UNC paths |

\</evalcmd\>

Returns *string* with any illegal path characters removed or replaced.

//<Example://>

    Output( MakeLegal("*File<?>Name*.txt") )
    --> #File(!)Name#.txt

    Output( MakeLegal("C:\Program Files", "n") )
    --> C;_Program Files

    Output( MakeLegal("\\Server\\Share", "sf") )
    --> Server/Share
