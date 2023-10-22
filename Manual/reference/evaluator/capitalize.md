\<evalcmd\> Capitalize && string && Capitalized string. && string && string && Input string to capitalize. && type && int && Optional capitalization type. Valid types are:

|     |                                                |
|-----|------------------------------------------------|
| 0   | capitalize first letter                        |
| 1   | capitalize all words                           |
| 2   | capitalize all words including file extensions |

\</evalcmd\>

Returns the capitalized version of *string*. By default, just the first letter is capitalized. Use the optional *type* parameter to select a different capitalization method.

//<Example://>

    Output( Capitalize("hello world", 1) );
    --> Hello World

*See also:*  
[lcase](lcase.md)  
[ucase](ucase.md)  
