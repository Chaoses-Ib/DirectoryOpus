# ShellProperty

**ShellProperty** 对象代表一个 Shell 属性 - 一个来自 Windows 或第三方扩展（与 Opus 本地元数据系统中的元数据不同）的文件或文件夹的元数据项。

**[FSUtil](fsutil.zh.md).GetShellPropertyList** 方法允许您检索可用 Shell 属性的列表。然后，您可以使用 **[FSUtil](fsutil.zh.md).GetShellProperty** 或 **[Item](item.zh.md).ShellProp** 来检索特定文件的属性值。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

**defwidth**</td><td>

*int*</td><td>
显示此属性的列应使用的默认宽度（以像素为单位）。
</td></tr><tr><td>

**display_name**</td><td>

*string*</td><td>
此属性的显示名称（应该显示给用户的名称）。
</td></tr><tr><td>

**isviewable**</td><td>

*bool*</td><td>
该属性旨在供用户查看（例如，在列中）。
</td></tr><tr><td>

**justify**</td><td>

*string*</td><td>

此属性的默认列对齐方式（**left**、**right**、**center**）。
</td></tr><tr><td>

**pkey**</td><td>

*string*</td><td>

此属性的 PKEY（属性键）。这是属性的唯一 ID，也是引用属性的规范方法。您也可以使用 **raw_name** 和 **display_name** 值来访问属性，但它们可能不准确（因为可能存在两个具有相同名称的属性），并且速度也较慢，因为每次都需要通过名称查找属性。
</td></tr><tr><td>

**raw_name**</td><td>

*string*</td><td>
属性提供程序使用的内部名称。
</td></tr><tr><td>

**type**</td><td>

*string*</td><td>

此属性返回的数据类型；**string**、**number**、**datetime** 是目前支持的唯一类型。
</td></tr></tbody>
</table>