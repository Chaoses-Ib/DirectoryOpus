**OnScript即时查找Command** 事件是 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的入口点，该事件 [扩展即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。事件的实际名称由脚本本身定义，当通过 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).AddCommand** 方法添加该命令时 - **OnScript即时查找Command** 只是一个占位符名称。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnScript即时查找Command
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[Script即时查找CommandData](../scripting_objects/scriptfaytcommanddata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*none*
</td></tr><tr><td>

**描述：**</td><td>

当脚本通过添加新内部命令使用 **ScriptInitData.AddCommand** 来扩展即时查找字段时，它使用 **ScriptCommand.method** 属性指定其入口点的名称。触发即时查找扩展时，Opus 将在您的脚本中调用该方法。

**[scriptfaytcommanddata](../scripting_objects/scriptfaytcommanddata.zh.md)** 对象提供有关用户输入了哪些内容来触发您的扩展的信息。
</td></tr></tbody>
</table>