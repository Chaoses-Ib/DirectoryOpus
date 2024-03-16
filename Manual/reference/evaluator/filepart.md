\<evalcmd\> FilePart && string && Filename component of specified path. && path && path && File or folder path. && \[components\] && int && Number of components to return. \</evalcmd\>

Returns the filename (trailing) component or components of the specified path. If *components* isn't specified, the final component is returned.

//<Example://>

    Output(FilePart("C:\one\two\file.jpg"));
    --> file.jpg

*See also:*  
[fileext](fileext.md)  
[parent](parent.md)  
[root](root.md)  
[stem](stem.md)
