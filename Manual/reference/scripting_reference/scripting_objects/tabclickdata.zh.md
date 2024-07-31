# TabClickData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnTabClick](../scripting_events/ontabclick.zh.md)** 事件，当用户按住限定键点击标签页时，该方法将收到一个 **TabClickData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按住的任何限定键。  
该字符串可以包含以下任何或所有内容： *shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果没有按住限定键，该字符串将为： *none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示被点击的标签页。
</td></tr></tbody>
</table>