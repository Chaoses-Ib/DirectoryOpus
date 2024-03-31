 \<evalcmd\> IsSet && bool && 如果所有指定的变量存在，则为 **True**。&& name && var && 要测试的变量名称。&& \[name...\] && var && 其他变量名称... \</evalcmd\>

如果此求值中存在所有指定的变量，则返回 **True**。如果任何变量不存在，则返回 **False**。

//<Example://>

    if (IsSet("j")) { ... } // 是否存在名为“j”的变量？
    if (IsSet("name", "ext")) { ... } // 变量“name”和“ext”是否同时存在？

*另请参阅:* [val](val.zh.md)