\<evalcmd\> PathType && string && Type of specified path. && path && path && Path to query the type of. \</evalcmd\>

Returns the type of the specified path. Types are:

|             |                                       |
|-------------|---------------------------------------|
| **filesys** | Normal filesystem path (e.g. C:\\     |
| **shell**   | Non-filesystem path like This PC      |
| **coll**    | File collection                       |
| **ftp**     | FTP path                              |
| **lib**     | Library                               |
| **mtp**     | Portable device (phone, tablet)       |
| **plugin**  | Plugin filesystem (e.g. 7zip archive) |
| **zip**     | Zip archive                           |

//<Example://>

    Output(PathType("/thispc"));
    --> shell
