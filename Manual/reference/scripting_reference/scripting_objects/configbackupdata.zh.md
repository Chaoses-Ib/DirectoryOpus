# ConfigBackupData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnConfigBackup](../scripting_events/onconfigbackup.zh.md)** 事件，当 Opus 配置备份时，该方法会收到一个 **ConfigBackupData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
location</td><td>

*object*:**[Path](path.zh.md)**</td><td>
返回 Opus 配置写入的暂存区域的路径。配置备份文件将从该文件夹中的文件创建。您的脚本对暂存文件夹中的文件所做的任何更改都将包含在备份中。
</td></tr><tr><td>
output_dir</td><td>

*object*:**[Path](path.zh.md)**</td><td>
返回正在保存配置备份的路径。
</td></tr><tr><td>
output_name</td><td>

*string*</td><td>
返回正在保存的配置备份的名称。
</td></tr></tbody>
</table>