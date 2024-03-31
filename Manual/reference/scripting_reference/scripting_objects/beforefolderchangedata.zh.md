如果 [脚本插件](/Manual/scripting/script_add-ins/README.zh.md)实施了 **[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.zh.md)** 事件，则该方法会在读取新文件夹前接收到 **BeforeFolderChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
action</td><td>

*字符串*</td><td>

返回一个字符串，用于表示触发文件夹读取的动作。该字符串将是下列值之一：*normal*、*refresh*、*refreshsearch*、*refreshsub*、*parent*、*root*、*back*、*forward*、*dblclk*。  
*refreshsub* 动作表示在开启平面视图时刷新文件夹（和子文件夹）。其他动作名称应该不言自明。
</td></tr><tr><td>
initial</td><td>

*布尔值*</td><td>

如果这是要读取到此标签中的第一个路径（即，之前的标签是空的），则返回 **True**。
</td></tr><tr><td>
path</td><td>

*对象：***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示要读取的新路径。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，用于表示当触发该事件时用户按下的任何限定键。  
该字符串可以包含下列值中的任何一个或全部：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有按下限定键，则字符串为：*none*
</td></tr><tr><td>
tab</td><td>

*对象：***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示正在更改文件夹的标签。
</td></tr></tbody>
</table>