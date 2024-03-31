\<evalcmd\> Count && int && 路径分量的数目。 && 路径 && 路径 && 任意路径。\</evalcmd\>

返回路径中组件的数目。

//<Example://>

    p: path = "C:\Windows\System32";
    Output( Count(p) );
    --> 3

*另请参阅：*  
[isparent](isparent.zh.md)  
[parent](parent.zh.md)  

------------------------------------------------------------------------

  
\<evalcmd\> Count && int && 子字符串匹配的数目。 && 字符串 && str && 搜索的字符串。 && 子字符串 && str && 要搜索的子字符串。 && \[标志\] && str && 标志。\</evalcmd\>

返回找到 *substring* 在 *string* 中的次数。

可选标志 **c** 使搜索区分大小写。

//<Example://>

    str = "Hello world";
    Output( Count(str, "l") );
    --> 3

*另请参阅：*  
[instr](instr.zh.md)