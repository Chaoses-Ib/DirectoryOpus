如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnActivateTab](../scripting_events/onactivatetab.zh.md)** 事件，则该方法将在标签页激活状态更改时接收一个 **ActivateTabData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
closing</td><td>

*bool*</td><td>

如果激活更改是由于关闭旧标签页，则返回 **True**。
</td></tr><tr><td>
newtab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回表示已激活的标签页的 **[Tab](tab.zh.md)** 对象。
</td></tr><tr><td>
oldtab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回表示已变为非激活状态的标签页的 **[Tab](tab.zh.md)** 对象。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户触发事件时按下的任何限定键。  
该字符串可以包含以下内容中的任何或全部内容：*shift*，*ctrl*，*alt*，*lwin*，*rwin*  
如果未按下限定键，则字符串将为：*none*
</td></tr></tbody>
</table>