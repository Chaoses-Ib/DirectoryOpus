# ShutdownData

如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnShutdown](../scripting_events/onshutdown.zh.md)** 事件，则在 Opus 关闭时调用的方法会接收一个 **ShutdownData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明</th></tr></thead><tbody><tr><td>
endsession</td><td>

*bool*</td><td>

返回 **True**（如果 Windows 会话正在结束，即，如果 Opus Shut Down 是因为系统正在 Shut Down），否则返回 **False**（如果只是 Opus 退出）。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回指示当事件被触发时用户按下的任何限定键的字符串。  
该字符串可以包含以下任意内容或所有内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有限定键被按住，该字符串将是：*none*
</td></tr></tbody>
</table>