**OnStartup** 事件可由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在 Opus 启动时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnStartup
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[StartupData](../scripting_objects/startupdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*none*
</td></tr><tr><td>

**描述：**</td><td>

此事件仅在 Opus 启动时触发，因此只有已安装的脚本加载项才会收到它。如果在 Opus 运行时安装脚本，则它在下次启动 Opus 之前不会收到 **OnStartup**。
</td></tr></tbody>
</table>