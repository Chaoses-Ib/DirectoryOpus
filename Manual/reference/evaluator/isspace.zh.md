\<evalcmd\> IsSpace && bool && **True** 仅当 *string* 仅由空格字符组成时。 && string && string && 要测试的字符串。 \</evalcmd\>

如果 *string* 完全由空格字符（空格、制表符、换行符）组成，则返回 **True**，否则返回 **False**。

//<Example://>

    Output(IsSpace("     "))
    --> true

    Output(IsSpace("_____"))
    --> false

*请参见：*  
[isalpha](isalpha.zh.md)  
[isdigit](isdigit.zh.md)  
[islower](islower.zh.md)  
[ispunct](ispunct.zh.md)  
[isupper](isupper.zh.md)