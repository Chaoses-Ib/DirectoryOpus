# Activate文件窗口Data

如果[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)生成了**[OnActivate文件窗口](../scripting_events/onactivatelister.zh.md)**事件，则该方法在文件窗口的窗口激活状态发生改变时接收 **Activate文件窗口Data**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
active</td><td>

*布尔值*</td><td>

如果此文件窗口正在激活，则返回 **True**，如果停用，则返回 **False**。 注意，如果激活直接从一个文件窗口转到另一个文件窗口，则脚本将被调用两次。
</td></tr><tr><td>
lister</td><td>

*对象:***[文件窗口](lister.zh.md)**</td><td>

返回一个表示正在关闭的文件窗口的**[文件窗口](lister.zh.md)** 对象。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，指示用户在触发事件时按下哪些限定键。  
字符串可以包含以下任何或所有内容：*shift* *ctrl*，*alt*，*lwin*，*rwin*  
如果没有按任何限定符，字符串将为：*none*
</td></tr></tbody>
</table>