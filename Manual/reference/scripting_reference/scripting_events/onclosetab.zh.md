**OnCloseTab** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，当在文件窗口中关闭标签页时会收到通知。

<table>
<thead><tr><th>

**方法名：**</th><th>
OnCloseTab
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[CloseTabData](../scripting_objects/closetabdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**说明：**</td><td>

**CloseTabData.tab** 属性标识正在关闭的标签页。可以从该事件返回 **True** 以阻止标签页关闭或返回 **False**（这是默认值）以允许其关闭。

请注意，当文件窗口关闭时，不会针对其每个标签页触发此事件 - **[OnClose文件窗口](oncloselister.zh.md)** 事件会在文件窗口关闭时提供通知，并且可以通过 **Close文件窗口Data.lister.tabs** 属性发现该文件窗口中的所有标签页。
</td></tr></tbody>
</table>