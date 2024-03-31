如果使用 **[OnGetNewName](../scripting_events/ongetnewname.zh.md)** 方法实现了[重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)，它将为每个被重命名的项接收一个 **GetNewNameData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
custom</td><td>

对象: **[CustomFieldData](customfielddata.zh.md)**</td><td>

返回一个 **[CustomFieldData](customfielddata.zh.md)** 对象，该对象提供脚本添加到 *重命名* 对话框中的任何 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 的值。
</td></tr><tr><td>
item</td><td>

*对象:***[Item](item.zh.md)**</td><td>

返回表示正在重命名的文件或文件夹的 **[Item](item.zh.md)** 对象。
</td></tr><tr><td>
newname</td><td>

*字符串*</td><td>

返回项建议的新名称。这将是应用 [重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 中选定标准选项的结果（编号、大写等）。
</td></tr><tr><td>
newname_ext</td><td>

*字符串*</td><td>
返回建议新名称的文件扩展名。未考虑多部分扩展名（例如，将返回 “.rar” 而不是 “.part1.rar”。
</td></tr><tr><td>
newname_ext_m</td><td>

*字符串*</td><td>
返回建议新名称的文件扩展名，考虑多部分扩展名（例如，将返回“.part1.rar”而不是“.rar”）。
</td></tr><tr><td>
newname_field</td><td>

*字符串*</td><td>

返回 *新名称* 字段的内容（即，不是应用所有选项后计算的新名称，而是用户输入的字段的实际文本内容）。
</td></tr><tr><td>
newname_stem</td><td>

*字符串*</td><td>
返回建议新名称的文件词干。未考虑多部分扩展名（例如，将返回 “catpictures.part1” 而不是 “catpictures”）。
</td></tr><tr><td>
newname_stem_m</td><td>

*字符串*</td><td>
返回建议新名称的文件词干，考虑多部分扩展名（例如，将返回 “catpictures” 而不是 “catpictures.part1”）。
</td></tr><tr><td>
oldname_field</td><td>

*字符串*</td><td>

返回用户在 [重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 中输入的“旧名称”模式。
</td></tr><tr><td>
preview</td><td>

*布尔*</td><td>

如果脚本被调用来生成重命名对话框的预览，则返回 **True**，如果文件正在实际重命名，则返回 **False**。
</td></tr><tr><td>
tab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，该对象表示重命名操作正在进行的标签页。如果没有标签页，则返回 **False**。
</td></tr></tbody>
</table>