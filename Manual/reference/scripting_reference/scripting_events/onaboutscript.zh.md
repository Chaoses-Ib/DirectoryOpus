**OnAboutScript** 事件可由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以向用户显示“关于”对话框。当用户在 **[脚本管理](/Manual/scripting/script_management/README.zh.md)** 对话框中单击脚本的 *关于* 按钮时，将触发此事件。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAboutScript
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[AboutData](../scripting_objects/aboutdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

此事件的通常实现将使用 **AboutData.window** 参数来使用 **[Dialog](../scripting_objects/dialog.zh.md)** 对象显示对话框。
</td></tr></tbody>
</table>