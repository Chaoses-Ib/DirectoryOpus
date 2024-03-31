**DialogOption** 对象可与 **[Dialog](dialog.zh.md)**对象的 options 属性一起使用。此对象提供了 5 个集合，你可以初始化任何一个对象，用户会将其视为物理复选框控件显示。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
label</td><td>

*string*</td><td>
将其设置为复选框所需的标签。
</td></tr><tr><td>
state</td><td>

*bool*</td><td>

将其设置为复选框所需的初始状态。当 **Dialog.Show** 方法返回时，你可以读取该属性来查找用户选择的 state 状态。
</td></tr></tbody>
</table>