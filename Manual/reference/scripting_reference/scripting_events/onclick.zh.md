# OnClick

**OnClick** 事件是 [脚本函数](/Manual/scripting/script_functions.zh.md) 的主要入口点。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnClick
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ClickData](../scripting_objects/clickdata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

当包含 [脚本函数](/Manual/scripting/script_functions.zh.md) 的按钮或热键被执行时，此方法被调用。**ClickData** 对象提供了关于命令环境的有用信息，包括源和目标标签和路径、任何选定的文件、命令行参数、任何按下的修饰键等。所有这些信息都可以通过 **ClickData.func** 属性访问（它返回一个 **[Func](../scripting_objects/func.zh.md)** 对象）。  
请注意，当一个脚本函数被执行时，任何不包含在函数内部的指令都会先执行，然后再调用 **OnClick**。这意味着 **OnClick** 方法在技术上是可选的（因为你可以在函数外部实现整个脚本），尽管建议你实现它仅仅是为了接收 **ClickData** 对象的益处。
</td></tr></tbody>
</table>