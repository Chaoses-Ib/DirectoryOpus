# 参数类型

以下限定词用于内部命令模板中以指示每个参数的类型。请记住，使用参数时您**永远**不要输入限定词 - 它们仅仅是对参数类型的线索。

<table>
<thead><tr><th>
限定词</th><th>
类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
/S</td><td>
开关</td><td>
表示开关参数（既可以是开启又可以是关闭的布尔选项）。
</td></tr><tr><td>
/K</td><td>
关键字</td><td>
表示值参数（提供值后必须在参数关键字后跟随）。
</td></tr><tr><td>
/O</td><td>
可选</td><td>
表示可选参数（既可单独用作开关，又可用于跟随值）。
</td></tr><tr><td>
/N</td><td>
数字</td><td>
参数的值必须是数字。
</td></tr><tr><td>
/M</td><td>
多重</td><td>
参数可以接受多个值（例如文件列表）。
</td></tr><tr><td>
/R</td><td>
原始</td><td>

参数接受“原始”值。对于这些参数，命令行后跟的参数名称的其余部分将被视为值。
此类型的参数是唯一不需要在包含空格的值周围添加引号的参数。
</td></tr></tbody>
</table>

请参阅[内部命令参数](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md)页面，了解有关各种参数类型的完整说明。