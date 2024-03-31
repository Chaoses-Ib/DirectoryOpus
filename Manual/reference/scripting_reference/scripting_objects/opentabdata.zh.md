如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnOpenTab](../scripting_events/onopentab.zh.md)** 事件，则在打开新标签页时调用该方法时会接收一个 **OpenTabData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个指示用户在事件触发时按下的任何限定符键的字符串。  
此字符串可以包含以下全部或部分内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果未按下任何限定符，则字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[标签页](tab.zh.md)**</td><td>

返回一个表示新打开标签页的 **[标签页](tab.zh.md)** 对象。
</td></tr></tbody>
</table>