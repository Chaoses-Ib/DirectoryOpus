# FilesystemChangeData

一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 可以通过实现 **[OnFilesystemChange](../scripting_events/onfilesystemchange.zh.md)** 事件并调用 **[FSUtil](fsutil.zh.md).WatchChanges** 方法来监控文件和文件夹的更改。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
id</td><td>

*string*</td><td>

返回检测到文件或文件夹更改的观察器的 ID。此 ID 在您调用 **[FSUtil](fsutil.zh.md).WatchChanges** 创建观察器时分配。
</td></tr></tbody>
</table>