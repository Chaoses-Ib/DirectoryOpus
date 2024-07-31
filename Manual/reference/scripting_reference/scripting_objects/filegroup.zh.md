# FileGroup

**FileGroup** 对象提供有关文件组的信息（当文件列表设置为按特定列分组时）。**[Tab](tab.zh.md).filegroups** 属性返回一个表示该标签页中当前文件组的集合，而 **[Item](item.zh.md).filegroup** 属性返回特定项目的当前文件组。

注意：如果您需要查找文件所属的 *文件类型组*，而不是基于当前可见列的文件分组方式，请参阅 [FiletypeGroup](filetypegroup.zh.md) 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回组的名称。
</td></tr><tr><td>
collapsed</td><td>

*布尔值*</td><td>

如果组当前处于折叠状态，则返回 **True**。
</td></tr><tr><td>
count</td><td>

*整数*</td><td>

返回该组中的项目数。注意，组可以为空；空组不会显示在文件列表中，但仍然会由 **Tab.filegroups** 属性返回。
</td></tr><tr><td>
id</td><td>

*整数*</td><td>

返回该组的 id 号。id 号是任意的——您不应该对实际值赋予任何意义，但您可以比较 id 字段，作为判断两个项目是否在同一组的简单方法。
</td></tr><tr><td>
members</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示该组中的所有文件和文件夹。
</td></tr><tr><td>
type</td><td>

*字符串*</td><td>
返回一个字符串，指示该组的排序类型。
</td></tr></tbody>
</table>