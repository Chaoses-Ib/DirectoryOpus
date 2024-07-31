# FlatViewChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnFlatViewChange](../scripting_events/onflatviewchange.zh.md)** 事件，当一个标签的 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 模式改变时，方法会收到一个 **FlatViewChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
mode</td><td>

*字符串*</td><td>

返回一个 *字符串* 表示新的平面视图模式。将是 *off*、*grouped*、*mixed* 或 *mixednofolders* 之一。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串表示触发事件时用户按住的任何限定键。
该字符串可以包含以下任何或所有内容： *shift* *ctrl*、*alt*、*lwin*、*rwin*
如果没有按住任何限定键，则字符串将为： *none*
</td></tr><tr><td>
tab</td><td>

*对象：***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示平面视图模式改变的标签。
</td></tr></tbody>
</table>