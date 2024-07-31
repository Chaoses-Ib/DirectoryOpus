# OnListerUIChange

**OnListerUIChange** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，用于在文件窗口中某些用户界面元素的状态发生变化时接收通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnListerUIChange
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ListerUIChangeChangeData](../scripting_objects/listeruichangedata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**ListerUIChangeChangeData.lister** 属性标识文件窗口，**change** 属性是一个 *string*，指示发生变化的元素。可以使用 **[Command](../scripting_objects/command.zh.md).IsSet** 方法发现元素的实际状态。
</td></tr></tbody>
</table>