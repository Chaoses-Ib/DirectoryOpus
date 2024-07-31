# OnScriptCommand

**OnScriptCommand** 事件是 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的入口点，该命令由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加。事件的实际名称由脚本本身定义，当命令通过 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 方法添加时 - **OnScriptCommand** 只是一个占位符名称。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnScriptCommand
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ScriptCommandData](../scripting_objects/scriptcommanddata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*bool*
</td></tr><tr><td>

**描述:**</td><td>

当脚本加载项使用 **ScriptInitData.AddCommand** 添加一个新的内部命令时，它会使用 **ScriptCommand.method** 属性指定其入口点的名称。当内部命令运行时，Opus 会在你的脚本中调用该方法。  
**ScriptCommandData.func** 属性提供有关命令环境的信息（包括任何解析后的参数），**cmdline** 属性提供调用你的命令的原始命令行。  
如果此事件返回 **True**，则该函数将被中止 - 如果你遇到错误并且用户选择中止操作，你可能会这样做。
</td></tr></tbody>
</table>