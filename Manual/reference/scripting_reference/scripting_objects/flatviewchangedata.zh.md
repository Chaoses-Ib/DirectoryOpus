# FlatViewChangeData

如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 执行 **[OnFlatViewChange](../scripting_events/onflatviewchange.zh.md)** 事件，当标签中的 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 模式更改时，该方法会接收一个 **FlatViewChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
mode</td><td>

*字符串*</td><td>

返回一个表示新平面视图模式的 *字符串*。应该是 *off*, *grouped*, *mixed* 或 *mixednofolders* 之一。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，表示触发事件时用户按下的任何修饰键。  
该字符串可以包含以下任何或全部内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果未按下任何修饰键，则字符串为：*none*
</td></tr><tr><td>
tab</td><td>

*对象：***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示发生平面视图模式更改的标签。
</td></tr></tbody>
</table>