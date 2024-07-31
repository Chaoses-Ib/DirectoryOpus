# ActivateTabData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnActivateTab](../scripting_events/onactivatetab.zh.md)** 事件，则该方法会在标签页激活状态发生变化时收到一个 **ActivateTabData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
closing</td><td>

*bool*</td><td>

如果激活变化是由于旧标签页关闭，则返回 **True**。
</td></tr><tr><td>
newtab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示已成为活动状态的标签页。
</td></tr><tr><td>
oldtab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示已变为非活动状态的标签页。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何修饰键。  
该字符串可以包含以下任何或所有内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果未按下任何修饰键，则该字符串将为：*none*
</td></tr></tbody>
</table>