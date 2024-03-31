**On** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以在打开新标签页时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnOpenTab
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[OpenTabData](../scripting_objects/opentabdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**OpenTabData.tab** 属性标识新打开的标签页。请注意，此方法不会在打开新文件窗口时调用，与该文件窗口中包含多少个标签页无关 - 相反，你可以通过实现 **OnOpen文件窗口** 事件来识别新打开文件窗口中的所有标签页。
</td></tr></tbody>
</table>