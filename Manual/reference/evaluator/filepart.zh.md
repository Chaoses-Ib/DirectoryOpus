\<evalcmd\> FilePart && 字符串 && 指定路径的文件名部分。 && 路径 && 路径 && 文件或文件夹路径。 && \[components\] && int && 要返回的部分的数目。 \</evalcmd\>

返回指定路径的文件名（尾部）部分或部分。如果未指定 *components*，则返回最终部分。

//<Example://>

    Output(FilePart("C:\one\two\file.jpg"));
    --> file.jpg

*另请参阅：*  
[fileext](fileext.zh.md)  
[parent](parent.zh.md)  
[root](root.zh.md)  
[stem](stem.zh.md)