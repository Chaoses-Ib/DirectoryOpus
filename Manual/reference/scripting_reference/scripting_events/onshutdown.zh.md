# OnShutdown

**OnShutdown** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，用于在 Opus 关闭时接收通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnShutdown
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ShutdownData](../scripting_objects/shutdowndata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*bool*
</td></tr><tr><td>

**描述:**</td><td>

当 Opus 关闭时，它会调用此事件。如果 Opus 是因为 Windows 关闭而退出，则 **ShutdownData.endsession** 属性将为 **True**。如果 **endsession** 为 **False**，则可以从此事件返回 **True** 来阻止 Opus 退出 - 如果 Windows 也在关闭，则返回值将被忽略。
</td></tr></tbody>
</table>