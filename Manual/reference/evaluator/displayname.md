\<evalcmd\> DisplayName && string && Display name of the file or folder. && path && path && Path to query the display name of. && \[flags\] && string && The optional flags are:

|       |                                               |
|-------|-----------------------------------------------|
| **f** | Return file part (final component)            |
| **p** | Return parsing path                           |
| **r** | Resolve to true location (e.g. library files) |

\</evalcmd\>

Returns the display name of the file or folder.

//<Example://>

    Output(DisplayName("/desktop"));
    --> Desktop

    Output(DisplayName("/desktop", "p"));
    --> C:\Users\jon\Desktop

*See also:* [resolve](resolve.md)
