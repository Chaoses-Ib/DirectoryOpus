# OnScriptFAYTCommand

**OnScriptFAYTCommand** 事件是 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的入口点，该插件 [扩展了即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。事件的实际名称由脚本本身定义，当命令通过 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 方法添加时 - **OnScriptFAYTCommand** 只是一个占位符名称。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnScriptFAYTCommand
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ScriptFAYTCommandData](../scripting_objects/scriptfaytcommanddata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

当脚本通过使用 **ScriptInitData.AddCommand** 添加新的内部命令来扩展即时查找字段时，它使用 **ScriptCommand.method** 属性指定其入口点的名称。当即时查找扩展被触发时，Opus 将在你的脚本中调用该方法。

**[ScriptFAYTCommandData](../scripting_objects/scriptfaytcommanddata.zh.md)** 对象提供有关用户输入的内容以触发你的扩展的信息。
</td></tr></tbody>
</table>