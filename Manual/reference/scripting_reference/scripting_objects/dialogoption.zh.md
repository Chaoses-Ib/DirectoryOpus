# DialogOption

**DialogOption** 对象与 **[Dialog](dialog.zh.md)** 对象的 options 属性一起使用。提供了五个这样的集合，您初始化的任何集合都将以物理复选框控件的形式显示给用户。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
label</td><td>

*string*</td><td>
将此设置为复选框所需的标签。
</td></tr><tr><td>
state</td><td>

*bool*</td><td>

将此设置为复选框所需的初始状态。当 **Dialog.Show** 方法返回时，您可以读取此属性以找出用户选择的 state。
</td></tr></tbody>
</table>