# OnAboutScript

**OnAboutScript** 事件可以由[脚本加载项](/Manual/scripting/script_add_ins/README.zh.md) 实现，以便向用户显示“关于”对话框。 当用户单击**[脚本管理](/Manual/scripting/script_management/README.zh.md)**对话框上脚本的*关于*按钮时，会触发此事件。

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

**描述：**</td><td>

此事件的常见实现方式是使用 **AboutData.window** 参数通过 **[Dialog](../scripting_objects/dialog.zh.md)** 对象显示对话框。
</td></tr></tbody>
</table>