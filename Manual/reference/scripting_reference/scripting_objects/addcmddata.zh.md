# AddCmdData

**AddCmdData** 对象在 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 事件中传递。脚本可以使用它通过 **AddCommand** 方法 [添加内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddCommand</td><td>

*无*</td><td>

*对象:***[ScriptCommand](scriptcommand.zh.md)**</td><td>

向 Opus 添加一个新的内部命令。返回的 **[ScriptCommand](scriptcommand.zh.md)** 对象必须正确初始化。脚本加载项可以向 Opus 内部命令集添加任意数量的内部命令。
</td></tr></tbody>
</table>