**OnShutdown** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现，以在 Opus 关闭时接收通知。

<table>
<thead><tr><th>

**方法名：**</th><th>

OnShutdown
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ShutdownData](../scripting_objects/shutdowndata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**说明：**</td><td>

当 Opus 关闭时，Opus 会调用此事件。如果 Opus 退出是因为 Windows 正在关闭，则 **ShutdownData.endsession** 属性将为 **True**。如果 **endsession** 为 **False**，则您可以从此事件返回 **True** 以防止 Opus 退出——如果 Windows 也正在关闭，则将忽略返回值。
</td></tr></tbody>
</table>