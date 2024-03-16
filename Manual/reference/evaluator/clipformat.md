\<evalcmd\> ClipFormat && string or bool && Clipboard contents format. && \[type\] && string && Content type to test for. && \[wantcut\] && bool && Pass **True** to differentiate cut and copied files. \</evalcmd\>

With no arguments, returns a string identifying the type of data currently on the clipboard.

Possible clipboard data types are:

|     |              |     |                                          |     |
|-----|--------------|-----|------------------------------------------|-----|
|     | *files*      |     | (if **wantcut** is **False** or omitted) |     |
|     | *files_copy* |     | (if **wantcut** is **True**)             |     |
|     | *files_cut*  |     | (if **wantcut** is **True**)             |     |
|     | *image*      |     |                                          |     |
|     | *text*       |     |                                          |     |
|     | *other*      |     |                                          |     |
|     | *none*       |     |                                          |     |

You can also test whether a particular type of data is on the clipboard, by passing a string with the type to test as the first argument, in which case the return value is **True** or **False**.

*Examples:*

    Output(ClipFormat());
    Output(ClipFormat(True));
    if (ClipFormat("text")) { ... }
    if (ClipFormat("files")) { ... }
    if (ClipFormat("files_cut",True)) { ... }
