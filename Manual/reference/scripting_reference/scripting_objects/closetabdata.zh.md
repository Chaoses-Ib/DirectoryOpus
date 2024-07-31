# CloseTabData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnCloseTab](../scripting_events/onclosetab.zh.md)** 事件，当一个标签被关闭时，该方法会收到一个 **CloseTabData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何限定键。  
该字符串可以包含以下任何或所有内容：*shift* *ctrl*，*alt*，*lwin*，*rwin*  
如果没有按下限定键，则字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示正在关闭的标签。
</td></tr></tbody>
</table>