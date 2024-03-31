如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnGetCopyQueueName](../scripting_events/ongetcopyqueuename.zh.md)** 事件，则该方法会在开始使用自动管理的复制队列（即配置中 **[复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 页上的 *自动管理文件复制队列* 选项已启用）的复制操作时收到一个 **GetCopyQueueNameData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
dest</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示复制操作的目标路径。
</td></tr><tr><td>
desttab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示目标文件夹标签页。
</td></tr><tr><td>
dest_drives</td><td>

*字符串*</td><td>

返回一个二进制字符串，指示目标路径所在的物理驱动器索引（如果存在）。例如，00100000000000000000000000 表示目标驱动器是 C:。
</td></tr><tr><td>
move</td><td>

*布尔值*</td><td>

如果操作是移动而不是复制，则返回 **True**。
</td></tr><tr><td>
name</td><td>

*字符串*</td><td>

返回此操作的默认队列名称。
</td></tr><tr><td>
source</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示复制操作​​的源路径。
</td></tr><tr><td>
sourcetab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示源文件夹标签页。
</td></tr><tr><td>
source_drives</td><td>

*字符串*</td><td>

返回一个二进制字符串，指示源路径所在的物理驱动器索引（如果存在）。例如，00001000000000000000000000 表示源驱动器是 E:。
</td></tr></tbody>
</table>