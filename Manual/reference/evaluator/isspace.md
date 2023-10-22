\<evalcmd\> IsSpace && bool && **True** if *string* consists only of space characters. && string && string && String to test. \</evalcmd\>

Returns **True** if *string* consists entirely of space characters (spaces, tabs, newlines), otherwise returns **False**.

//<Example://>

    Output(IsSpace("     "))
    --> true

    Output(IsSpace("_____"))
    --> false

*See also:*  
[isalpha](isalpha.md)  
[isdigit](isdigit.md)  
[islower](islower.md)  
[ispunct](ispunct.md)  
[isupper](isupper.md)  
