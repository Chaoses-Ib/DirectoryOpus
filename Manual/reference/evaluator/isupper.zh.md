\<evalcmd\> IsUpper && 布尔 && **True**，前提是 *string* 中仅包含大写字母。 && string && string && 要测试的字符串。 \</evalcmd\>

如果 *string* 全部由大写字母组成，则返回 **True**，否则返回 **False**。

//<Example://>

    Output(IsUpper("ABCDE"))
    --> ture

    Output(IsUpper("ABcDE"))
    --> false

*另请参见：*
[isalpha](isalpha.zh.md)  
[isdigit](isdigit.zh.md)  
[islower](islower.zh.md)  
[ispunct](ispunct.zh.md)  
[isspace](isspace.zh.md)