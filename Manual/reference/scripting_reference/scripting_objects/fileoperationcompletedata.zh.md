如果某个[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.zh.md)** 事件，则该方法会在支持的文件操作开始时接收一个 **FileOperationCompleteData** 对象。如果返回 **True** 以指示你想收到关于操作的通知，在操作完成时你还会收到另一个调用。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

返回一个表示文件操作类型字符串。目前唯一支持的值为 **“重命名”**。
</td></tr><tr><td>
cmdline</td><td>

*string*</td><td>
返回一个提供启动此操作的完整命令行的字符串。
</td></tr><tr><td>
data</td><td>

*variant*</td><td>

当 **query** 属性为 **False** 时提供关于所完成操作的更多信息。  
对于“重命名”，这是返回一个提供所有重命名项目とその新しい名前映射的 **[Map](map.zh.md)** 对象。
</td></tr><tr><td>
dest</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个表示操作目标路径的 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个表示操作启动时用户按下的任何限定键的字符串。  
该字符串可以包含任何以下内容或全部内容：*shift* *ctrl*, *alt*, *lwin*, *rwin*  
如果没有按任何限定键，字符串将为：*none*
</td></tr><tr><td>
query</td><td>

*bool*</td><td>

第一次调用 **[OnFileOperationComplete](../scripting_events/onfileoperationcomplete.zh.md)** 事件时返回 **True**。你应该检查操作和其他属性，如果你决定要接收关于此操作的通知，则返回 **True**。在你第二次被调用时，操作完成后，这将为 **False**。
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个表示操作源路径的 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个表示源文件夹标签页的 **[Tab](tab.zh.md)** 对象。
</td></tr></tbody>
</table>