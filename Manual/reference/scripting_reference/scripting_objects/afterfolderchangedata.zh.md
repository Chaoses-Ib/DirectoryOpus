# AfterFolderChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnAfterFolderChange](../scripting_events/onafterfolderchange.zh.md)** 事件，当文件夹读取完成后，该方法会收到一个 **AfterFolderChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

返回一个字符串，指示触发文件夹读取的操作。该字符串将是以下之一：*normal*，*refresh*，*refreshsearch*，*refreshsub*，*parent*，*root*，*back*，*forward*，*dblclk*。
*refreshsub* 操作表示在平面视图打开时，文件夹（以及子文件夹）正在刷新。其它操作名称应该不言自明。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

*如果读取失败*，这将返回一个 **[Path](path.zh.md)** 对象，表示 Opus 尝试读取的路径。
*如果读取成功，则不会提供此属性* - 相反，**tab** 属性提供对此信息的访问。
使用 **result** 属性来判断读取是否成功。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户触发事件时按下的任何限定符键。
该字符串可以包含以下任何或所有内容：*shift* *ctrl*，*alt*，*lwin*，*rwin*
如果没有按下限定符，该字符串将为：*none*
</td></tr><tr><td>
result</td><td>

*bool*</td><td>

如果文件夹读取成功，则返回 **True**，如果失败则返回 **False**。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示读取该文件夹的标签页。
</td></tr></tbody>
</table>