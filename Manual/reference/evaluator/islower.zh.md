\<evalcmd\> IsLower && bool && **True** 如果 *string* 只包含小写字母。 && string && string && 要测试的字符串。 \</evalcmd\>

如果 *string* 全部由小写字母组成，则返回 **True**，否则，返回 **False**。

//<Example://>

    Output(IsLower("abcde"))
    --> true

    Output(IsLower("abCde"))
    --> false

*另请参见：*  
[isalpha](isalpha.zh.md)  
[isdigit](isdigit.zh.md)  
[ispunct](ispunct.zh.md)  
[isspace](isspace.zh.md)  
[isupper](isupper.zh.md)