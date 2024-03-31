\<evalcmd\> IsAlpha && bool && **True** 如果 *string* 仅由字母组成。 && string && string && 要测试的字符串。 \</evalcmd\>

如果 *string* 完全由字母组成，则返回 **True**，否则返回 **False**。

//<Example://>

    Output(IsAlpha("abcde"))
    --> true

    Output(IsAlpha("ab3de"))
    --> false

*另请参见：*

[isdigit](isdigit.zh.md)  
[islower](islower.zh.md)  
[ispunct](ispunct.zh.md)  
[isspace](isspace.zh.md)  
[isupper](isupper.zh.md)