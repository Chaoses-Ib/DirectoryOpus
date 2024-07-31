# CloseListerData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnCloseLister](../scripting_events/oncloselister.zh.md)** 事件，该方法会在文件窗口关闭之前收到一个 **CloseListerData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
lister</td><td>

*对象:* **[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象，表示正在关闭的文件窗口。
</td></tr><tr><td>
prevent_save</td><td>

*布尔值*</td><td>

设置为 **True** 以阻止关闭的文件窗口保存为新的默认文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，表示用户在触发事件时按下的任何限定符键。
该字符串可以包含以下任何或所有内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*
如果没有按下任何限定符，则该字符串将为：*none*
</td></tr><tr><td>
shutdown</td><td>

*布尔值*</td><td>

如果文件窗口是因为 Opus 关闭而关闭，则返回 **True**。
</td></tr></tbody>
</table>