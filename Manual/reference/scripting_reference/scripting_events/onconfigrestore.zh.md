# OnConfigRestore

**OnConfigRestore** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，用于在 Opus 配置从备份还原时接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnConfigRestore
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ConfigRestoreData](../scripting_objects/configrestoredata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

**ConfigRestoreData.location** 属性标识正在从中还原 Opus 配置的暂存文件夹。您可以在返回之前对该文件夹中的文件进行更改，您所做的任何修改都将被导入当前配置。
</td></tr></tbody>
</table>