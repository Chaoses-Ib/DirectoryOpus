# OpenTabData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnOpenTab](../scripting_events/onopentab.zh.md)** 事件，当新标签页打开时调用该方法，会接收一个 **OpenTabData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，表示用户触发事件时按下的任何限定符键。  
该字符串可以包含以下任何或所有内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果没有按下限定符，该字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示新打开的标签页。
</td></tr></tbody>
</table>