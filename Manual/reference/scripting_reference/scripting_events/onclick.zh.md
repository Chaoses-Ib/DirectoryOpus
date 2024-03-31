**OnClick** 事件是 [脚本函数](/Manual/scripting/script_functions.zh.md) 的主要进入点。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnClick
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ClickData](../scripting_objects/clickdata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*没有*
</td></tr><tr><td>

**描述:**</td><td>

此方法将在包含 [脚本函数](/Manual/scripting/script_functions.zh.md) 的按钮或热键运行时被调用。**ClickData** 对象提供了有关命令环境的有用信息，包括源和目标标签和路径、选定的文件、命令行参数、按下的任何限定键等。可以通过 **ClickData.func** 属性（返回一个 **[Func](../scripting_objects/func.zh.md)** 对象）访问所有这些信息。  
请注意，当运行脚本函数时，函数外部的任何指令都将首先执行，然后才会调用 **OnClick**。这意味着 **OnClick** 方法在技术上是可选的（因为您可以在函数外部实现整个脚本），尽管建议您仅为其接收的 **ClickData** 对象而实施它。
</td></tr></tbody>
</table>