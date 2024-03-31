如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnSourceDestChange](../scripting_events/onsourcedestchange.zh.md)** 事件，则此方法会收到一个 **SourceDestData** 对象以指示哪个标签页的状态发生更改。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
dest</td><td>

*bool*</td><td>

如果标签页现在是目标，则返回 **True**。
</td></tr><tr><td>
source</td><td>

*bool*</td><td>

如果标签页现在是源，则返回 **True**。如果 **source** 和 **dest** 都返回 False，则表示标签页现在为“关闭”。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何限定键。
此字符串可以包含以下任意或全部内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果没有限定键被按下，则字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[标签页](tab.zh.md)**</td><td>

返回表示标签页的 **[标签页](tab.zh.md)** 对象。
</td></tr></tbody>
</table>