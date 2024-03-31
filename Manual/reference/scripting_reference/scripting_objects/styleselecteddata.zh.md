如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnStyleSelected](../scripting_events/onstyleselected.zh.md)** 事件，当用户选择新的 [文件窗口样式](/Manual/basic_concepts/the_lister/styles.zh.md) 时，该方法将收到一个 **StyleSelectedData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
lister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示正在更改样式的文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示触发事件时用户按下的任何修饰键。  
此字符串可以包含以下内容中的任何一个或全部内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有按修饰键，则字符串将为：*none*
</td></tr><tr><td>
style</td><td>

*string*</td><td>
返回新选择的样式名称。
</td></tr></tbody>
</table>