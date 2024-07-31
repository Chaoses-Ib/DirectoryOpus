# SourceDestData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnSourceDestChange](../scripting_events/onsourcedestchange.zh.md)** 事件，该方法会收到一个 **SourceDestData** 对象来指示哪个标签页的状态发生了改变。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
dest</td><td>

*bool*</td><td>

如果该标签页现在是目标，则返回 **True**。
</td></tr><tr><td>
source</td><td>

*bool*</td><td>

如果该标签页现在是源，则返回 **True**。如果 **source** 和 **dest** 都返回 False，则表示该标签页现在处于 "关闭" 状态。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户触发事件时按下的任何修饰键。
该字符串可以包含以下任何或全部内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*
如果没有按下修饰键，则字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示该标签页。
</td></tr></tbody>
</table>