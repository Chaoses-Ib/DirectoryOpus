# OnGetCustomFields

**OnGetCustomFields** 事件可以由 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 实现，以在 *重命名* 对话框中添加 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md)。这使您可以提供一个或多个控件，供用户使用这些控件将参数传递给您的脚本。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnGetCustomFields
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[GetCustomFieldData](../scripting_objects/getcustomfielddata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

当您的脚本从预设加载时（或您单击集成脚本编辑器中的 **刷新** 按钮），*重命名* 对话框将调用此方法。

**GetCustomFieldData.fields** 属性使您能够在重命名对话框中添加一个或多个自定义字段。对于每个字段，您可以：

- 提供标签
- 为编辑字段指定提示信息
- 为数字编辑控件添加向上/向下微调器
- 为编辑字段指定长度限制

有关更多信息，请参阅 [重命名对话框中的自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md)。
</td></tr></tbody>
</table>