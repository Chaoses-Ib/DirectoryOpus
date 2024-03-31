**DialogListGroup** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中 *列表视图* 控件中的一个组。它由 **[Control](control.zh.md).GetGroupById** 方法返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
expanded</td><td>

*bool*</td><td>

返回或设置此组的展开状态。该组必须通过 **Control.AddGroup** 方法添加为 “可折叠”。
</td></tr><tr><td>
id</td><td>

*int*</td><td>
返回此组的 ID。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回此组的名称。
</td></tr></tbody>
</table>