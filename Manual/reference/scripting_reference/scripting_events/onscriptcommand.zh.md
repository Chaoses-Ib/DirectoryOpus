除了用 "**" 包装的关键字和代码，保留 HTML 标记外，将以下英语文本翻译成中文： # OnScriptCommand

**OnScriptCommand** 事件是添加的 [内部命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 的进入点 [脚本加载项](/Manual/scripting/script_add-ins/README).zh.md)。事件实际名称由脚本本身定义，当通过 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 方法添加命令时 - **OnScriptCommand** 仅仅是一个占位符名称。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnScriptCommand
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ScriptCommandData](../scripting_objects/scriptcommanddata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**说明：**</td><td>

当一个脚本加载项使用 **ScriptInitData.AddCommand** 添加一个新的内部命令时，它用 **ScriptCommand.method** 属性指定了它的进入点名称。当运行内部命令时，Opus 将在你的脚本中调用那个方法。  
**ScriptCommandData.func** 属性提供了关于命令环境的信息（包括任何已解析的参数），**cmdline** 属性提供了调用了你的命令的原始命令行。  
如果此事件返回 **True** 则函数将被中止 - 如果发生错误并且用户选择中止操作，你可能这么做。
</td></tr></tbody>