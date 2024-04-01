# 项

**Items** 对象使您能枚举一个或多个 **[Item](item.zh.md)** 对象的集合。**Items** 对象可从许多方法和属性中检索，包括 **[Dialog](dialog.zh.md)。Multi**、**[DOpus](dopus.zh.md).GetClip**、**[Command](command.zh.md).files** 和其它几个。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合：***[item](item.zh.md)**</td><td>

返回一个 **[item](item.zh.md)** 对象的集合，您可以枚举它。
</td></tr><tr><td>
result</td><td>

*布尔值*</td><td>

当此 **Items** 对象来自 **[Dialog](dialog.zh.md)。Multi** 方法时，它包括一个 **result** 属性，给出该对话框的结果。该项集合只有在 **result** 返回 **True** 时才有效。如果它返回 **False**，则表示用户取消了该对话框。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
RemoveNested</td><td>

*无*</td><td>

*int*</td><td>
移除该集合中的任何嵌套项（来自子文件夹而不是根文件夹的项）。返回移除的项数目。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

更新此对象的 state。此操作仅适用于来自特定数据源的集合（例如，来自 **[Tab](tab.zh.md)**）。首次检索 **Items** 对象时，将对其进行快照。在脚本外部进行的后续更改将不被检测，除非您调用 **Update** 方法。
</td></tr></tbody>
</table>