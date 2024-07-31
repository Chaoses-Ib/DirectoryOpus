# OnCloseTab

**OnCloseTab** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在文件窗口中关闭标签时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnCloseTab
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[CloseTabData](../scripting_objects/closetabdata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*bool*
</td></tr><tr><td>

**描述:**</td><td>

**CloseTabData.tab** 属性标识正在关闭的标签。您可以从此事件返回 **True** 以阻止标签关闭，或返回 **False**（默认值）以允许其关闭。

请注意，当文件窗口关闭时，此事件不会为其每个标签触发 - **[OnCloseLister](oncloselister.zh.md)** 事件会在文件窗口关闭时提供通知，并且所有在该文件窗口中的标签都可以通过 **CloseListerData.lister.tabs** 属性发现。
</td></tr></tbody>
</table>