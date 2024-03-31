如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[On文件窗口UIChange](../scripting_events/onlisteruichange.zh.md)** 事件，当文件窗口中的多个用户界面元素打开或关闭时，该方法会接收一个 **文件窗口UIChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
更改</td><td>

*字符串*</td><td>

返回一个 *字符串*，指示更改了哪些 UI 元素。它将包含下列一个或多个字符串：*双重*、*树*、*元数据窗格*、*查看器*、*实用工具*、*双重布局*、*元数据窗格布局*、*查看器布局*、*工具栏*、*工具栏集*、*自动工具栏*、*最小/最大化*。
</td></tr><tr><td>
文件窗口</td><td>

**[文件窗口](lister.zh.md)** *对象*</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示正在更改的文件窗口。
</td></tr><tr><td>
限定符</td><td>

*字符串*</td><td>

返回一个字符串，指示用户在触发事件时按下哪些限定符键。
该字符串可以包含下列任何或所有字符：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果未按下任何限定符，则该字符串将为：*无*
</td></tr></tbody>
</table>