# CustomFieldData

**CustomFieldData** 对象通过 **[GetNewNameData](getnewnamedata.zh.md).custom** 属性提供给 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)。它提供对脚本添加到 *重命名* 对话框中的任何 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 的值的访问权限。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

\<自定义字段属性\></td><td>

*variant*</td><td>

**CustomFieldData** 对象的属性完全由脚本本身决定。

在 **[OnGetCustomFields](../scripting_events/ongetcustomfields.zh.md)** 方法中，将要使用的任何自定义字段的默认值分配给 **[GetCustomFieldData](getcustomfielddata.zh.md).fields** 属性。每个默认值的类型控制属性的类型。

*重命名* 对话框仅支持某些类型的自定义字段变量，因此您只能分配兼容类型的属性。支持的类型：

- 布尔选项（**True** 或 **False**） - 变量类型必须为 *bool*
- 数字选项 - 变量类型必须为 *int*
- 字符串选项 - 变量类型必须为 *string*
- 下拉列表 - 变量类型必须为 **[Vector](vector.zh.md)**，其中第一个元素为 *int*（用于指定默认选择），其余元素为字符串。
</td></tr></tbody>
</table>