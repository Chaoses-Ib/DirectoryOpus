\<evalcmd\> Running && bool && Returns **True** if *procname* is currently running. && procname && string && Name of process to look for. \</evalcmd\>

Queries whether a specified process is currently running.

//<Example://>

    if (Running("excel.exe")) { ... } // is Excel currently open?
