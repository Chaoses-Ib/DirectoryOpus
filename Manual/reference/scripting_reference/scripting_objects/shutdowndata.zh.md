# ShutdownData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnShutdown](../scripting_events/onshutdown.zh.md)** 事件，当 Opus 关闭时调用该方法，会收到一个 **ShutdownData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
endsession</td><td>

*bool*</td><td>

如果 Windows 会话即将结束（也就是说，Opus 因为系统关闭而关闭），则返回 **True**，否则（如果只是 Opus 退出），则返回 **False**。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示触发事件时用户按下的任何修饰键。
该字符串可以包含以下任何或所有内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*
如果没有按下修饰键，则该字符串将为：*none*
</td></tr></tbody>
</table>