# OnFilesystemChange

**OnFilesystemChange** 事件可由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，用于在监视的文件或文件夹发生更改时接收通知。 监视是通过调用 **[FSUtil](../scripting_objects/fsutil.zh.md).WatchChanges** 方法建立的。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnFilesystemChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[FilesystemChangeData](../scripting_objects/filesystemchangedata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**id** 属性指示哪个观察器检测到更改。 请注意，您不会被告知发生了什么更改，只会知道符合指定条件的内容发生了更改。
</td></tr></tbody>
</table>