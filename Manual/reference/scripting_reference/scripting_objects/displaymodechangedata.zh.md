# DisplayModeChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnDisplayModeChange](../scripting_events/ondisplaymodechange.zh.md)** 事件，则该方法会在标签页的 [显示模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 发生改变时收到一个 **DisplayModeChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
mode</td><td>

*字符串*</td><td>

返回一个指示新显示模式的 *字符串*。将是 *largeicons*、*smallicons*、*list*、*details*、*power*、*thumbnails* 或 *tiles* 之一。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，指示事件触发时用户按下的任何限定符键。  
该字符串可以包含以下任何或所有项：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有任何限定符被按下，则该字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*对象：***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示发生显示模式更改的标签页。
</td></tr></tbody>
</table>