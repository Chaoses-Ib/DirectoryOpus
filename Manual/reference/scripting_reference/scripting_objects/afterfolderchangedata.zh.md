如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnAfterFolderChange](../scripting_events/onafterfolderchange.zh.md)** 事件，该方法会在文件夹读取完成后收到一个 **AfterFolderChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
操作</td><td>

*字符串*</td><td>

返回一个字符串，表示触发文件夹读取的操作。该字符串将为以下内容之一：*normal*、*refresh*、*refreshsearch*、*refreshsub*、*parent*、*root*、*back*、*forward*、*dblclk*。  
*refreshsub* 操作表示文件夹（和子文件夹）正在刷新而平面视图已打开。其他操作名称应不言自明。
</td></tr><tr><td>
路径</td><td>

*对象：***[路径](path.zh.md)**</td><td>

*如果读取失败*，这将返回一个 **[路径](path.zh.md)** 对象，表示 Opus 尝试读取的路径。  
*如果读取成功，则不提供此属性* - 相反，**制表符** 属性提供对这些信息的访问权限。  
使用 **结果** 属性了解读取是否成功。
</td></tr><tr><td>
限定符</td><td>

*字符串*</td><td>

返回一个字符串，表示触发事件时用户按下的任何限定符键。  
此字符串可以包含以下任何或全部内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有限定符，该字符串将为：*none*
</td></tr><tr><td>
结果</td><td>

*布尔值*</td><td>

如果成功读取文件夹，则返回 **True**，如果失败则返回 **False**。
</td></tr><tr><td>
制表符</td><td>

*对象：***[制表符](tab.zh.md)**</td><td>

返回一个 **[制表符](tab.zh.md)** 对象，表示读取文件夹的制表符。
</td></tr></tbody>
</table>