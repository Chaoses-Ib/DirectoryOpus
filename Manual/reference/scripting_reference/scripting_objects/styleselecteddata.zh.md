# StyleSelectedData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnStyleSelected](../scripting_events/onstyleselected.zh.md)** 事件，当用户选择新的 [文件窗口风格](/Manual/basic_concepts/the_lister/styles.zh.md)时，该方法会接收一个 **StyleSelectedData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
lister</td><td>

*object:***[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象，表示正在更改风格的文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示用户触发事件时按下的任何限定键。  
该字符串可以包含以下任何或全部内容： *shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果没有任何限定键按下，该字符串将为： *none*
</td></tr><tr><td>
style</td><td>

*string*</td><td>
返回新选定风格的名称。
</td></tr></tbody>
</table>