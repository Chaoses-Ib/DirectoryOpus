\<evalcmd\> IsPunct && bool && **True** if *string* consists only of punctuation characters. && string && string && String to test. \</evalcmd\>

Returns **True** if *string* consists entirely of punctuation characters, otherwise returns **False**.

//<Example://>

    Output(IsPunct("!.,;:"))
    --> true

    Output(IsPunct("!.,j:"))
    --> false

*See also:*  
[isalpha](isalpha.md)  
[isdigit](isdigit.md)  
[islower](islower.md)  
[isspace](isspace.md)  
[isupper](isupper.md)  
