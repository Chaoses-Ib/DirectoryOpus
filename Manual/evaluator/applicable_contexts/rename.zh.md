# 重命名

您可以在[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)工具中的求值器中插入求值返回的文本。

使用`{= ... =}`代码来插入求值表达式。表达式的返回值将插入到新文件名中。

在此求值上下文中，提供以下变量：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

<nobr>*列名称*</nobr></td><td>

*不同*</td><td>

此求值上下文中，作为变量提供所有[列关键字](/Manual/reference/metadata_keywords/keywords_for_columns.zh.md)。

请注意，一些关键字可能使用变量名中无效的字符（例如`:`）——为了访问它们，请使用[val](/Manual/reference/evaluator/val.zh.md)函数。

此外，还支持[特定于重命名的关键字](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.zh.md)，例如**parent**和**parentbase**。
</td></tr><tr><td>
file_name</td><td>

*字符串*</td><td>

返回正在运行表达式的文件的完整名称。这可能不同于**file**（作为列关键字），返回*名称*列的值（例如，可能隐藏了文件扩展名）。
</td></tr><tr><td>
is_dir</td><td>

*布尔*</td><td>

如果表达式正在针对文件夹运行，则为**True**，如果表达式正在针对文件运行，则为**false**。
</td></tr><tr><td>
oldname</td><td>

*字符串*</td><td>
“旧名称”字段的值。
</td></tr><tr><td>
newname</td><td>

*字符串*</td><td>
“新名称”字段的值。
</td></tr></tbody>
</table>

返回值应为将插入到新文件名的*字符串*。