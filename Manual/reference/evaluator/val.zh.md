\<evalcmd\> Val && 变量 && 命名参数的值。 && varname && 字符串 && 参数的名称。 \</evalcmd\>

返回变量的值； *varname* 作为带引号的字符串提供。对于包含会使 Evaluator 的解析器混淆的字符的变量（例如，如果名称以数字开头），这非常有用。

//<Example://>

    flag = Val("35mmfocallength"); // 获取 35mmfocallength 字段的值