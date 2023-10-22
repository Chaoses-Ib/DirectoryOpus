\<evalcmd\> Parent && path && Parent of specified path. && path && path && File or folder path. && \[levels\] && int && Number of levels up to go. \</evalcmd\>

Returns the parent of the specified path (i.e. the input *path* with the final component removed).

The optional *levels* argument lets you go up more than one level.

//<Example://>

    Output(Parent("C:\one\two\file.jpg"));
    --> C:\one\two

*See also:*  
[count](count.md)  
[fileext](fileext.md)  
[filepart](filepart.md)  
[isparent](isparent.md)  
[root](root.md)  
[stem](stem.md)
