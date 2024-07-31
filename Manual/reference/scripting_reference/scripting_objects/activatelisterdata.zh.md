# ActivateListerData

如果一个[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnActivateLister](../scripting_events/onactivatelister.zh.md)** 事件，则该方法会在文件窗口窗口激活状态发生变化时接收一个 **ActivateListerData**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
active</td><td>

*bool*</td><td>

如果该文件窗口正在激活，则返回**True**，如果正在停用，则返回**False**。注意，如果激活从一个文件窗口直接转移到另一个文件窗口，脚本将被调用两次。
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.zh.md)**</td><td>

返回一个**[Lister](lister.zh.md)**对象，表示正在关闭的文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示触发事件时用户按下的任何限定键。
该字符串可以包含以下任何或所有内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*
如果没有按下限定符，字符串将是：*none*
</td></tr></tbody>
</table>