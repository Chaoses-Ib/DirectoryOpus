[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 可通过实现 **[OnFilesystemChange](../scripting_events/onfilesystemchange.zh.md)** 事件和调用 **[FSUtil](fsutil.zh.md).WatchChanges** 方法来建立对文件和文件夹更改的监控机制。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
id</td><td>

*string*</td><td>

返回检测到文件或文件夹更改的观察者的 ID。在调用 **[FSUtil](fsutil.zh.md).WatchChanges** 创建观察者时会分配此 ID。
</td></tr></tbody>
</table>