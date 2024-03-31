**ScriptCommandData** 对象传递给由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加的任何 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的脚本定义入口点。事件的方法名称是由脚本本身定义的，但通常称为 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)** 。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>

这将返回用于调用命令的原始命令行。如果命令行中提供了任何参数，则可以通过 **func.args** 属性以解析好的形式获取它们。
</td></tr><tr><td>
fayt</td><td>

*string*  
或 *bool*</td><td>

如果这是一个字符串，这意味着它正被作为一个 [即时查找扩展](scriptfaytcommanddata.zh.md) 命令调用。如果设置为 **False**，则它是一个常规命令。
</td></tr><tr><td>
func</td><td>

*对象:***[Func](func.zh.md)**</td><td>

返回与该函数相关的 **[Func](func.zh.md)** 对象。这提供了对函数环境（来源和目标标签页等）以及任何变量和已解析命令行参数的信息访问。
</td></tr></tbody>
</table>