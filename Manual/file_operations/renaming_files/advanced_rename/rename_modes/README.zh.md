# 重命名模式

重命名对话框的顶部部分是用于定义重命名“模式”的地方，此模式决定如何解释两个输入字段“旧名称”和“新名称”。

![](/Manual/images/media/13/rename_mode.png)

使用“模式”下拉菜单选择重命名模式。

- *[Standard Wildcard Rename](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/standard_wildcard_rename.zh.md)*：按字面意思输入新名称，或使用简单的通配符系统重命名。
- *[Find And Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/find_and_replace.zh.md)*：指定一个要搜索的文本字符串，以及另一个要替换它的字符串（这就像文本编辑器中的搜索和替换一样）。
- *[Regular Expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md)*：按字面意思输入新名称，或使用正则表达式搜索和替换进行重命名。
- *[Regular Expressions + Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions_and_find_and_replace.zh.md)*：输入正则表达式进行搜索，以及要替换它的文本（将上述两种模式结合在一起）。

此部分中的其它控件有：

- **旧名称**：应用于每个旧（原始）文件名的输入模式。当使用通配符或“正则表达式”重命名时，该字段用于指定“从”或“搜索”模式。当使用“查找和替换”模式时，该字段指定查找字符串。
- **新名称**：应用于生成每个新文件名的输出模式。当使用“查找和替换”模式时，该字段指定替换字符串。
- **区分大小写**：启用区分大小写的模式匹配或“查找和替换”搜索*.*当启用时，现有文件名的字母大小写必须与提供的模式完全匹配 - 例如，如果启用了“区分大小写”选项，则“*d\*”将不匹配“*Dog*”。
- **忽略扩展名**：从重命名操作中完全排除文件扩展名 - 如果启用，文件扩展名将不会被修改，并且您不必（也不应该）考虑任何通配符模式中的扩展名。您通常应该启用此选项，因为它使通配符（特别是正则表达式）变得更加简单，并且很少需要修改文件名扩展名。

**重置**按钮提供了一种快速清除重命名对话框其它字段并恢复到“空白页”的方法。

更多：

[Standard Wildcard Rename](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/standard_wildcard_rename.zh.md)  
[Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/find_and_replace.zh.md)  
[Regular Expressions](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md)  
[Regular Expressions + Find and Replace](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions_and_find_and_replace.zh.md)