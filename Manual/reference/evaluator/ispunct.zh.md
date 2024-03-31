\<evalcmd\> IsPunct && bool && **True** 如果 *string* 只包含标点符号。 && string && string && 要测试的字符串。 \</evalcmd\>

如果 *string* 全部由标点字符组成，则返回 **True**，否则返回 **False**。

//<Example://>

    Output(IsPunct("!.,;:"))
    --> true

    Output(IsPunct("!.,j:"))
    --> false

*另请参阅：*  
[isalpha](isalpha.zh.md)  
[isdigit](isdigit.zh.md)  
[islower](islower.zh.md)  
[isspace](isspace.zh.md)  
[isupper](isupper.zh.md)