# FileOperationCompleteData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现了 **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.zh.md)** 事件，该方法会在每次支持的文件操作开始时收到一个 **FileOperationCompleteData** 对象。如果返回 **True** 表示要接收操作通知，则操作完成后会收到另一个调用。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

返回一个字符串，表示文件操作的类型。目前唯一支持的值是 **"rename"**。
</td></tr><tr><td>
cmdline</td><td>

*string*</td><td>
返回一个字符串，提供启动此操作的完整命令行。
</td></tr><tr><td>
data</td><td>

*variant*</td><td>

当 **query** 属性为 **False** 时，此属性提供有关已完成操作的更多信息。  
对于 "rename"，此属性返回一个 **[Map](map.zh.md)** 对象，提供所有已重命名项及其新名称的映射。
</td></tr><tr><td>
dest</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示操作的目标路径。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，表示用户在启动操作时按下的任何限定键。  
字符串可以包含以下任何或所有项： *shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果未按下任何限定键，则字符串将为： *none*
</td></tr><tr><td>
query</td><td>

*bool*</td><td>

第一次调用 **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.zh.md)** 事件时，返回值为 **True**。应检查 action 和其它属性，并返回 **True** 如果决定要接收此操作的通知。当第二次调用（操作完成时）时，此属性将为 **False**。
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示操作的源路径。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示源文件夹标签页。
</td></tr></tbody>
</table>