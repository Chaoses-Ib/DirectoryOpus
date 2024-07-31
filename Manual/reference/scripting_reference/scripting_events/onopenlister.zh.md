# OnOpenLister

**OnOpenLister** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，用于在打开新的文件窗口时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnOpenLister
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[OpenListerData](../scripting_objects/openlisterdata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

**OpenListerData.lister** 属性标识新打开的文件窗口。

此事件最初在文件窗口创建后立即调用，在任何文件夹被读取或任何标签被打开之前。如果从该事件返回 **True**，则在所有标签创建后将再次调用它。可以使用 OpenListerData.after 属性来区分这些调用。
</td></tr></tbody>
</table>