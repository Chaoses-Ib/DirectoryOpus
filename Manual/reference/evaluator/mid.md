\<evalcmd\> Mid && string && Specified portion of the string. && string && string && Input string to return a portion of. && start && int && Starting position to return (0 is the left-most position). && \[length\] && int && Length of string to return. \</evalcmd\>

Returns *length* characters from *string* starting at position *start*. If *length* is -1 or omitted, returns from *start* to the end of the string.

//<Example://>

    Output( Mid("Hello To You", 6, 2) );
    --> To

*See also:*  
[left](left.md)  
[right](right.md)  
