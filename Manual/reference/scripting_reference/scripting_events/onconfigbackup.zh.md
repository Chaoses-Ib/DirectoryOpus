# OnConfigBackup

**OnConfigBackup** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以在 Opus 配置被备份时接收通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnConfigBackup
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ConfigBackupData](../scripting_objects/configbackupdata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**ConfigBackupData.location** 属性标识 Opus 配置已写入的暂存文件夹。您可以在返回之前对该文件夹中的文件进行更改，您所做的任何修改都将包含在配置备份中。
</td></tr></tbody>
</table>