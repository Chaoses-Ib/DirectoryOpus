# GetNewNameData

如果一个 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 使用 **[OnGetNewName](../scripting_events/ongetnewname.zh.md)** 方法实现，它会为每个要重命名的项目接收一个 **GetNewNameData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
custom</td><td>

object:**[CustomFieldData](customfielddata.zh.md)**</td><td>

返回一个 **[CustomFieldData](customfielddata.zh.md)** 对象，它提供脚本添加到 *重命名* 对话框的任何 [自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md) 的值。
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，表示要重命名的文件或文件夹。
</td></tr><tr><td>
newname</td><td>

*string*</td><td>

返回项目的建议新名称。这将是 [重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 中选定的任何标准选项（编号、大小写等）的结果。
</td></tr><tr><td>
newname_ext</td><td>

*string*</td><td>
返回建议新名称的文件扩展名。不考虑多部分扩展名（例如，将返回 ".rar" 而不是 ".part1.rar"）。
</td></tr><tr><td>
newname_ext_m</td><td>

*string*</td><td>
返回建议新名称的文件扩展名，考虑多部分扩展名（例如，将返回 ".part1.rar" 而不是 ".rar"）。
</td></tr><tr><td>
newname_field</td><td>

*string*</td><td>

返回 *新名称* 字段的内容（即，不是在应用所有选项后的计算新名称，而是用户输入的字段的实际文本内容）。
</td></tr><tr><td>
newname_stem</td><td>

*string*</td><td>
返回建议新名称的文件干。不考虑多部分扩展名（例如，将返回 "catpictures.part1" 而不是 "catpictures"）。
</td></tr><tr><td>
newname_stem_m</td><td>

*string*</td><td>
返回建议新名称的文件干，考虑多部分扩展名（例如，将返回 "catpictures" 而不是 "catpictures.part1"）。
</td></tr><tr><td>
oldname_field</td><td>

*string*</td><td>

返回用户在 [重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 中输入的“旧名称”模式。
</td></tr><tr><td>
preview</td><td>

*bool*</td><td>

如果脚本被调用来生成重命名对话框的预览，则返回 **True**，如果文件正在被真正重命名，则返回 **False**。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示重命名操作发生的标签页。如果没有标签页，则返回 **False**。
</td></tr></tbody>
</table>