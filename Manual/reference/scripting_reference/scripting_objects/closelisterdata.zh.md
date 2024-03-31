如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了**[OnClose文件窗口](../scripting_events/oncloselister.zh.md)**事件，则在关闭文件窗口之前，该方法会收到一个**Close文件窗口Data**对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
lister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回表示正在关闭的文件窗口的**[文件窗口](lister.zh.md)**对象。
</td></tr><tr><td>
prevent_save</td><td>

*bool*</td><td>

将其设置为 **True** 以阻止关闭的文件窗口被保存为新的默认文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示触发事件时用户按下的任何限定键。  
字符串可以包含以下任何内容或全部内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果没有按限定键，字符串将为：*none*
</td></tr><tr><td>
shutdown</td><td>

*bool*</td><td>

如果文件窗口因 Opus 关闭而关闭，则返回 **True**。
</td></tr></tbody>
</table>