\<evalcmd\> IsPath && bool && **True** if *path* is a fully-qualified pathname. && path && path && Path to test. \</evalcmd\>

Returns **True** if *path* is a fully-qualified pathname, otherwise returns **False**.

//<Example://>

    Output(IsPath("C:\Windows\System32"))
    --> true

    Output(IsPath("System32"))
    --> false
