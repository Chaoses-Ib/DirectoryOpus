# Results

**Results** 对象提供有关由 **[Command](command.zh.md)** 对象运行的函数结果的信息。它从 **Command.results** 属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
result</td><td>

*int*</td><td>
指示命令是否成功运行。零表示命令无法运行或被中止；任何其它数字表示命令至少对某些文件运行。（注意，这不是外部命令的“退出代码”。对于外部命令，它只指示 Opus 是否启动了该命令。如果您需要外部命令的退出代码，请使用 WScript.Shell 的 Run 或 Exec 方法来运行该命令。）
</td></tr><tr><td>
newtabs</td><td>

*collection:***[Tab](tab.zh.md)**</td><td>

此属性返回一个 **[Tab](tab.zh.md)** 对象集合，代表命令创建的任何新标签页。
</td></tr><tr><td>
newlisters</td><td>

*collection:***[Lister](lister.zh.md)**</td><td>

此属性返回一个 **[Lister](lister.zh.md)** 对象集合，代表命令创建的任何新的文件窗口。
</td></tr><tr><td>
newviewers</td><td>

*collection:***[Viewer](viewer.zh.md)**</td><td>

此属性返回一个 **[Viewer](viewer.zh.md)** 对象集合，代表命令创建的任何新的图像查看器。（这仅适用于独立查看器，而不是查看器窗格。）
</td></tr></tbody>
</table>