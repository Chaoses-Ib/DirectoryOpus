\<evalcmd\> 正在运行 &&  bool && 如果 *procname* 当前正在运行，返回 **True**。 && procname && 字符串 && 要查找的进程的名称。\</evalcmd\>

查询指定的进程当前是否正在运行。

//<Example://>

    if (Running("excel.exe")) { ... } // Excel 当前是否已打开？