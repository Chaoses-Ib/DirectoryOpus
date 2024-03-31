**CustomFieldData** 对象通过 **[GetNewNameData](getnewnamedata.zh.md).custom** 属性提供给 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)。它提供对脚本添加到 *重命名* 对话框中的任何 [自定字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 的值进行访问。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

\<自定字段属性\></td><td>

*变体*</td><td>

**CustomFieldData** 对象的属性完全由脚本本身决定。

在 **[OnGetCustomFields](../scripting_events/ongetcustomfields.zh.md)** 方法中，将任意自定字段的默认值指定给 **[GetCustomFieldData](getcustomfielddata.zh.md).fields** 属性。每个默认值类型控制属性的类型。

*重命名* 对话框仅对自定字段支持特定类型的变量，因此仅能指定兼容类型的属性。支持的类型包括：

- 布尔值选项（**True** 或 **False**） - 变量类型必须为 *bool*
- 数字选项 - 变量类型必须为 *int*
- 字符串选项 - 变量类型必须为 *string*
- 下拉列表 - 变量类型必须是 **[Vector](vector.zh.md)**，第一个元素为 *int*（指定默认选项），其余元素为字符串。
</td></tr></tbody>
</table>