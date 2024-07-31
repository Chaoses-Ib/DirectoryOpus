# OnCloseLister

**OnCloseLister** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在任何文件窗口关闭时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnCloseLister
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[CloseListerData](../scripting_objects/closelisterdata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*bool*
</td></tr><tr><td>

**描述:**</td><td>

**CloseListerData.lister** 属性标识正在关闭的文件窗口。**shutdown** 属性在文件窗口由于 Opus (或 Windows) 关闭而关闭时为 **True**。  
如果 shutdown 为 **False**，则可以通过从该事件返回 **True** 来阻止文件窗口关闭（或返回 **False** 以允许关闭，这是默认值）。如果 Opus 或 Windows 正在关闭，则无法阻止文件窗口关闭。
</td></tr></tbody>
</table>