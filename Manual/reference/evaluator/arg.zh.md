\<evalcmd\> Arg && string && 命名参数的值。&& argname && string && 用户命令参数的名称。\</evalcmd\>

返回 [用户命令](/Manual/customize/the_customize_dialog/user_commands.zh.md) 参数的值。因此，用户命令可以用求值器基于提供的参数值，修改其行为。

//<示例：//>

    @if:=(Arg("NAME")=="jon")
    echo嗨，乔恩！
    @if:else
    echo你是谁？