可由 [脚本外接程序](/Manual/scripting/script_add-ins/README.zh.md) 实现 **OnFilesystemChange** 事件，以在监视的文件或文件夹更改时接收通知。通过调用 **[FSUtil](../scripting_objects/fsutil.zh.md).WatchChanges** 方法来建立监视。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnFilesystemChange
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[FilesystemChangeData](../scripting_objects/filesystemchangedata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**id** 属性指示哪个观察程序检测到更改。请注意，并非明确指出哪些内容已更改，而只是说明符合指定条件的内容已更改。
</td></tr></tbody>
</table>