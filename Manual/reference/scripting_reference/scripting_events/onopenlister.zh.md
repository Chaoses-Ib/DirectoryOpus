**OnOpen文件窗口** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以在打开新文件窗口时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnOpen文件窗口
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[Open文件窗口Data](../scripting_objects/openlisterdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

**Open文件窗口Data.lister** 属性标识新打开的文件窗口。

此事件最初在创建文件窗口后立即调用，在读取任何文件夹或打开任何标签页之前。如果从此事件返回 **True**，则它将在创建完所有标签页后再次调用。你可以使用 Open文件窗口Data.after 属性来区分这些调用。
</td></tr></tbody>
</table>