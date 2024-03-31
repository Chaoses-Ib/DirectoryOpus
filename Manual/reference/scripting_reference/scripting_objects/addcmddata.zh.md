**AddCmdData** 对象会传递给脚本插件中的 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 事件。脚本可以使用它在 **AddCommand** 方法的作用下 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
AddCommand</td><td>

*无*</td><td>

*对象:***[脚本命令](scriptcommand.zh.md)**</td><td>

向 Opus 添加新的内部命令。返回的 **[脚本命令](scriptcommand.zh.md)** 对象必须正确初始化。脚本插件可以根据需要向 Opus 的内部命令集添加任意数量的内部命令。
</td></tr></tbody>
</table>