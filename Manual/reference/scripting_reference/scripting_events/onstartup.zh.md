# OnStartup

**OnStartup** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在 Opus 启动时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnStartup
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[StartupData](../scripting_objects/startupdata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

此事件仅在 Opus 启动时触发，因此只有已安装的脚本加载项才能收到它。如果在 Opus 正在运行时安装脚本，它将不会收到 **OnStartup**，直到下次启动 Opus。
</td></tr></tbody>
</table>