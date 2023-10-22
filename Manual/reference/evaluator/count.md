\<evalcmd\> Count && int && Number of path components. && path && path && Any path. \</evalcmd\>

Returns the number of components in the path.

//<Example://>

    p: path = "C:\Windows\System32";
    Output( Count(p) );
    --> 3

*See also:*  
[isparent](isparent.md)  
[parent](parent.md)  
  

------------------------------------------------------------------------

  
\<evalcmd\> Count && int && Number of substring matches. && string && str && String to search. && substring && str && Sub-string to search for. && \[flags\] && str && Flags. \</evalcmd\>

Returns the number of times *substring* is found in *string*.

The optional flag **c** makes the search case-sensitive.

//<Example://>

    str = "Hello world";
    Output( Count(str, "l") );
    --> 3

*See also:*  
[instr](instr.md)  
