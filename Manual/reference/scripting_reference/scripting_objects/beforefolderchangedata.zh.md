# BeforeFolderChangeData

如果一个[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了**[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.zh.md)** 事件，则该方法会在读取新文件夹之前收到一个**BeforeFolderChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

返回一个字符串，指示触发文件夹读取的操作。字符串将是以下之一：*normal*、*refresh*、*refreshsearch*、*refreshsub*、*parent*、*root*、*back*、*forward*、*dblclk*。
*refreshsub* 操作表示在平板视图打开时刷新文件夹（及其子文件夹）。其它操作名称应该不言自明。
</td></tr><tr><td>
initial</td><td>

*bool*</td><td>

如果这是第一个要读取到此标签的路径（即之前标签为空），则返回**True**。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个**[Path](path.zh.md)** 对象，表示要读取的新路径。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何限定键。
字符串可以包含以下任何或所有内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果没有按下限定键，字符串将为：*none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)** 对象，表示正在更改文件夹的标签。
</td></tr></tbody>
</table>