\<evalcmd\> ClipFormat && string or bool && Clipboard contents format. && \[type\] && string && Content type to test for. \</evalcmd\>

With no arguments, returns a string identifying the type of data currently on the clipboard.

You can also test whether a particular type of data is on the clipboard, in which case the return value is **True** or **False**.

Clipboard data types are *files*, *image*, *text*, *other* and *none*.

//<Example://>

    if (ClipFormat("text")) { ... }
