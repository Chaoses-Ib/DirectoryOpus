# Open文件窗口Data

如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnOpen文件窗口](../scripting_events/onopenlister.zh.md)** 事件，当新的文件窗口打开时，方法接收一个 **Open文件窗口Data** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
after</td><td>

*bool*</td><td>

最初设置为 **False**，表示在创建任何标签前已调用该事件。如果从 **[OnOpen文件窗口](../scripting_events/onopenlister.zh.md)** 事件中返回 **True**，那么将再次调用它，并将 **after** 设置为 **True** 以指示已创建所有标签。
</td></tr><tr><td>
lister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个代表新打开的文件窗口的 **[文件窗口](lister.zh.md)** 对象。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何限定键。  
字符串可以包含以下任何内容： *shift* *ctrl*，*alt*，*lwin*，*rwin*  
如果未按下任何限定键，则字符串为：*none*
</td></tr></tbody>
</table>