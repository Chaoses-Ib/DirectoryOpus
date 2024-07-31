# ScriptCommandData

**ScriptCommandData** 对象被传递给任何由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加的 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的脚本定义的入口点。这些事件的函数名由脚本本身定义，但一般称为 **[OnScriptCommand](../scripting_events/onscriptcommand.zh.md)**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>

此属性返回调用该命令的原始命令行。如果命令行上提供了任何参数，则可以通过 **func.args** 属性以解析后的形式获得。
</td></tr><tr><td>
fayt</td><td>

*string*  
或 *bool*</td><td>

如果这是一个字符串，则表示它作为 [即时查找扩展](scriptfaytcommanddata.zh.md) 命令被调用。如果设置为 **False**，则为普通命令。
</td></tr><tr><td>
func</td><td>

*object:***[Func](func.zh.md)**</td><td>

返回与该函数相关的 **[Func](func.zh.md)** 对象。它提供了对函数环境（源和目标标签页等）以及任何变量和解析后的命令行参数的访问。
</td></tr></tbody>
</table>