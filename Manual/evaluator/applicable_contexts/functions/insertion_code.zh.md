# 求值插入代码

你可以使用 `{= ... =}` 插入代码将求值表达式结果插入到命令行中。

表达式可以插入变量值（例如 `{=source=}`）或执行复杂计算并返回其值。

![](page>standard_variables&nodate&nouser&nofooter)

在此上下文中，求值器还可以访问各种 [外部控制代码](/Manual/reference/command_reference/external_control_codes/README.zh.md) 的值作为表达式内的变量。

例如，当前文件路径可用作变量 `filepath`。

求值表达式中的返回值将插入到命令行中。