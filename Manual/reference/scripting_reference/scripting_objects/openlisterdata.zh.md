# OpenListerData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnOpenLister](../scripting_events/onopenlister.zh.md)** 事件，当一个新的文件窗口打开时，该方法会接收到一个 **OpenListerData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
after</td><td>

*bool*</td><td>

最初设置为 **False**，表示事件在任何标签页创建之前就被调用了。如果您从 **[OnOpenLister](../scripting_events/onopenlister.zh.md)** 事件返回 **True**，它将再次被调用，并且 **after** 将被设置为 **True** 以表示所有标签页都已创建。
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象，表示新打开的文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示用户在触发事件时按下的任何修饰键。  
该字符串可以包含以下任意或所有项：*shift* *ctrl*，*alt*，*lwin*，*rwin*  
如果没有按下修饰键，该字符串将为：*none*
</td></tr></tbody>
</table>