**ShellProperty** 对象表示 Shell 属性 - 从 Windows 或第三方扩展（相对于 Opus 的本机元数据系统的元数据）获得的文件或文件夹的元数据项。

**[FSUtil](fsutil.zh.md).GetShellPropertyList** 方法允许你检索可用 Shell 属性的列表。然后，你可以使用 **[FSUtil](fsutil.zh.md).GetShellProperty** 或 **[Item](item.zh.md).ShellProp** 来检索特定文件的属性值。

<table>
<thead><tr><th>
属性名</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

**defwidth**</td><td>

*int*</td><td>
显示此属性的列应使用的默认像素宽度。
</td></tr><tr><td>

**display_name**</td><td>

*string*</td><td>
此属性的显示名称（应向用户显示的名称）。
</td></tr><tr><td>

**justify**</td><td>

*string*</td><td>

此属性的默认列对齐（**左**, **右**, **居中**）。
</td></tr><tr><td>

**pkey**</td><td>

*string*</td><td>

此属性的 PKEY（属性键）。这是属性的唯一 ID 和引用属性的标准方法。你也可以使用 **raw_name** 和 **display_name** 值来访问属性，但它们可能不准确（因为可能有两个属性拥有相同名称），同时速度更慢，因为每次都必须通过名称查找属性。
</td></tr><tr><td>

**raw_name**</td><td>

*string*</td><td>
属性提供者使用的内部名称。
</td></tr><tr><td>

**type**</td><td>

*string*</td><td>

此属性返回的数据类型；目前，仅支持 **string**, **number**, **datetime** 类型。
</td></tr></tbody>
</table>