\<evalcmd\> Parent && 给定路径的父路径 && path && 路径 && path && 文件或文件夹路径 && \[levels\] && int && 向上返回的层数。 \</evalcmd\>

返回给定路径的父路径（即移除最后一个组件后的输入 *path*）。

可选的 *levels* 参数允许您向上返回多层。

//<Example://>

    Output(Parent("C:\one\two\file.jpg"));
    --> C:\one\two

*另请参阅：*  
[count](count.zh.md)  
[fileext](fileext.zh.md)  
[filepart](filepart.zh.md)  
[isparent](isparent.zh.md)  
[root](root.zh.md)  
[stem](stem.zh.md)