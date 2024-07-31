# Items

**Items** 对象允许您枚举一个或多个 **[Item](item.zh.md)** 对象的集合。**Items** 对象可从许多方法和属性中获取，包括 **[Dialog](dialog.zh.md).Multi**、**[DOpus](dopus.zh.md).GetClip**、**[Command](command.zh.md).files** 和其它一些。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[item](item.zh.md)**</td><td>

返回一个 **[item](item.zh.md)** 对象的集合，您可以对其进行枚举。
</td></tr><tr><td>
result</td><td>

*bool*</td><td>

当此 **Items** 对象来自 **[Dialog](dialog.zh.md).Multi** 方法时，它包含一个 **result** 属性，该属性提供对话框的结果。仅当 **result** 返回 **True** 时，项目集合才有效。如果它返回 **False**，则表示用户取消了对话框。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
RemoveNested</td><td>

*无*</td><td>

*int*</td><td>
从集合中删除所有嵌套项目（来自子文件夹而不是根文件夹的项目）。返回删除的项目数量。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

更新此对象的状态。这仅适用于来自特定来源的集合（例如，来自 **[Tab](tab.zh.md)**）。第一次检索 **Items** 对象时，会获取快照。在脚本之外进行的更改不会被检测到，除非您调用 **Update** 方法。
</td></tr></tbody>
</table>