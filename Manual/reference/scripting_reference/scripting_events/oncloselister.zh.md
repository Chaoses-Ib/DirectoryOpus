**OnClose文件窗口** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 来实现，以在文件窗口关闭时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnClose文件窗口
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[Close文件窗口Data](../scripting_objects/closelisterdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

**Close文件窗口Data.lister** 属性识别关闭的文件窗口。如果文件窗口因 Opus（或 Windows）关闭而关闭，则 **shutdown** 属性为 **True**。  
如果 **shutdown** 为 **False**，则可以通过从此事件返回 **True** 来阻止文件窗口关闭（或 **False** 允许关闭，这是默认值）。如果 Opus 或 Windows 正在关闭，那么您将不能阻止文件窗口关闭。
</td></tr></tbody>
</table>