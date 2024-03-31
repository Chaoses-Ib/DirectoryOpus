# TabClickData

如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnTabClick](../scripting_events/ontabclick.zh.md)** 事件，则在按住限定键单击标签页时，该方法会接收一个 **TabClickData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任意限定键。  
该字符串可以包含以下任意内容或全部内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果未按下任何限定键，则字符串为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回表示已单击标签页的 **[Tab](tab.zh.md)** 对象。
</td></tr></tbody>
</table>