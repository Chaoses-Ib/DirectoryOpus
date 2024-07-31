# ConfigRestoreData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现了 **[OnConfigRestore](../scripting_events/onconfigrestore.zh.md)** 事件，当从备份中恢复配置时，该方法会收到一个 **ConfigRestoreData** 对象。

该方法将被调用两次；一次在恢复开始之前，另一次在 Opus 重新启动并使用新配置之后。`step` 属性告诉您这是哪一次调用。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
location</td><td>

*object*:**[Path](path.zh.md)**</td><td>

返回已提取备份 Opus 配置的暂存区域的路径。您的脚本对暂存文件夹中的文件所做的任何更改都将被导入到 Opus 配置中。请注意，此属性仅在 `step` 等于 "before" 时提供。
</td></tr><tr><td>
step</td><td>

*string*</td><td>
返回 "before" 或 "after"，以指示这是事件的哪一次调用。
</td></tr></tbody>
</table>