# AboutData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 提供了 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 方法，当用户在偏好设置中点击 *关于* 按钮时，它将被传递一个 **AboutData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
window</td><td>

*int*</td><td>

这是一个指向父窗口的句柄，脚本应该在使用 **[Dialog](dialog.zh.md)** 对象显示对话框时使用它。即使它不是一个 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**，它仍然可以被分配到 **Dialog.window** 属性来设置对话框的父窗口。
</td></tr></tbody>
</table>