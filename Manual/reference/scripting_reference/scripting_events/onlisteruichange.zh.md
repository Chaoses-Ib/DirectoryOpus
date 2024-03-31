**On文件窗口UIChange** 事件可由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实施，以便在文件窗口中某些用户界面元素的状态更改时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
On文件窗口UIChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[文件窗口UIChangeData](../scripting_objects/listeruichangedata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*none*
</td></tr><tr><td>

**描述：**</td><td>

**文件窗口UIChangeData.lister** 属性标识文件窗口，**change** 属性是一个 *string*，指示已更改的元素。可以使用 **[Command](../scripting_objects/command.zh.md).IsSet** 方法发现元素的实际状态。
</td></tr></tbody>
</table>