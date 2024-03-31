如果 [script 加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现**[OnDisplayModeChange](../scripting_events/ondisplaymodechange.zh.md)** 事件，则在标签页中更改[显示模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 时该方法会接收 **DisplayModeChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明</th></tr></thead><tbody><tr><td>
mode</td><td>

*string*</td><td>

返回一个表示新的显示模式的 *string*。将为 *largeicons*、*smallicons*、*list*、*details*、*power*、*thumbnails* 或 *tiles* 之一。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个表示触发事件时用户按下的任何限定键的字符串。
字符串可以包含以下任意或全部内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果未按下任何限定键，则字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回表示在其中更改显示模式的标签页的 **[Tab](tab.zh.md)** 对象。
</td></tr></tbody>
</table>