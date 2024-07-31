# OnActivateTab

**OnActivateTab** 事件可以由 [脚本加载项](/Manual/scripting/script_add_ins/README.zh.md) 实现，以便在每次标签页变为活动状态时（即在同一个文件列表中位于另一个标签页的前面）接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnActivateTab
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ActivateTabData](../scripting_objects/activatetabdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**ActivateTabData.oldtab** 属性标识先前处于活动状态的标签页，**newtab** 属性标识新的活动标签页。
</td></tr></tbody>
</table>