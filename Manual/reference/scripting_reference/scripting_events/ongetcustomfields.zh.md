**OnGetCustomFields** 事件可以由 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 实现，以将 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 添加到“重命名”对话框中。这允许您提供一个或多个控制项，用户可以使用这些控制项将参数传递给您的脚本。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnGetCustomFields
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[GetCustomFieldData](../scripting_objects/getcustomfielddata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

当您的脚本从预设加载（或当您单击集成脚本编辑器中的 **刷新** 按钮时，“重命名”对话框将调用此方法。

**GetCustomFieldData.fields** 属性允许您将一个或多个自定义字段添加到“重命名”对话框中。对于每个字段，您可以：

- 提供标签
- 指定编辑字段的提示横幅
- 将上下旋钮添加到数字编辑控件
- 指定编辑字段的长度限制

有关更多信息，请参阅 [重命名对话框中的自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md)。
</td></tr></tbody>
</table>