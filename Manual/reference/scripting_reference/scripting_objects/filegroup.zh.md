**FileGroup**对象展示文件组的信息（当文件列表设置按特定列分组时）。**[Tab](tab.zh.md).filegroups**属性返回一个表示当前文件分组的集合，以及**[Item](item.zh.md).filegroup**属性返回特定文件的当前文件分组。

说明：如果您需要知道文件位于哪个*文件类型组*，而不是如何根据当前可显示列分组文件，请查阅[FiletypeGroup](filetypegroup.zh.md)对象。

<table>
<thead><tr><th>
属性名</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回组名称。
</td></tr><tr><td>
collapsed</td><td>

*bool*</td><td>

如果当前组已折叠，则返回**True**。
</td></tr><tr><td>
count</td><td>

*int*</td><td>

返回此组中的文件数量。请注意，组可以为空；空组不会在文件列表中显示，但仍然会被**Tab.filegroups**属性返回。
</td></tr><tr><td>
id</td><td>

*int*</td><td>

返回此组的ID号。ID号是任意的——您不应该将任何含义放在实际值上，但您可以比较ID字段以简单的方式来判断两个文件是否在同一个组中。
</td></tr><tr><td>
members</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，该对象表示此组中的所有文件和文件夹。
</td></tr><tr><td>
type</td><td>

*string*</td><td>
返回一个字符串，表示分组的排序类型。
</td></tr></tbody>
</table>