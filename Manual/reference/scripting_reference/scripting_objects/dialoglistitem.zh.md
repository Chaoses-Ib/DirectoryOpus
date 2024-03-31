**DialogListItem** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中 *组合框* 或 *列表框* 控件中的一个项目。它是由 **[Control](control.zh.md)。GetItemAt** 和 **[Control](control.zh.md)。GetItemByName** 方法返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

设置或查询此项目背景（填充）所用的颜色。此格式为 *\#RRGGBB*(十六进制) 或 *RRR,GGG,BBB* (十进制)。  
目前该属性仅支持 *列表视图* 控件中的项目。
</td></tr><tr><td>
checked</td><td>

*int*</td><td>

对于启用了复选框的 *列表视图* 控件，返回或设置项目的选中状态。  
选中状态为 **0** (未选中)，**1** (选中)，**2** (不确定)，**3** (未选中/禁用)，**4** (选中/禁用)，**5** (不确定/禁用)。
</td></tr><tr><td>
data</td><td>

*int*</td><td>
返回或设置与此项目关联的可选数据值。
</td></tr><tr><td>
disabled</td><td>

*bool*</td><td>

对于 *列表视图* 控件，返回或设置此项目的禁用状态。当 *列表视图* 禁用后，它将显示为幽灵，并且无法选择或右键单击。
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

设置或查询此控件文本（前景色）所用的颜色。此格式为 *\#RRGGBB*(十六进制) 或 *RRR,GGG,BBB* (十进制)。  
目前该属性仅支持 *列表视图* 控件中的项目。
</td></tr><tr><td>
group</td><td>

*int*</td><td>

返回或设置此项目所属的 *列表视图* 组。
</td></tr><tr><td>
icon</td><td>

*string*</td><td>

对于 *列表视图* 控件，返回或设置与此项目关联的图标。您可以指定文件或文件夹的路径以使用其图标，也可以指定文件扩展名（例如“·txt”）以使用通用文件类型图标。您还可以将其设置为 “dir”、“file”、“ftp” 和 “ftps”，以使用通用图标。您还可以通过提供文件路径后接逗号，然后提供文件中图标索引来从 DLL 或 EXE 中提取图标。
</td></tr><tr><td>
index</td><td>

*index*</td><td>

返回控件中此项目的基于0的索引。

对于组合编辑框，如果用户输入字符串而不是从列表中选择一个字符串，则此属性将返回 **-1**。他们输入的字符串可从 **name** 属性中获取。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回或设置项目的名称。
</td></tr><tr><td>
selected</td><td>

*bool*</td><td>

返回或设置项目的选中状态。主要用于多选 *列表框* 控件。
</td></tr><tr><td>
style</td><td>

*string*</td><td>

返回或设置此项目将显示的文本样式。您应该提供一个包含以下一个或多个标志的字符串：“b”（粗体）、“i”（斜体）、“u”（下划线）。  
目前该属性仅支持 *列表视图* 控件中的项目。
</td></tr><tr><td>
subitems</td><td>

*collection:string*</td><td>

对于处于 *详细信息* 模式的列表视图控件，返回一个字符串集合，使用此集合可以查询或更改项目子项目的文本。列表中的每一列（第一列除外）都将在该集合中对应一个字符串。

例如，假设列表中共有三列，那么第一列对应的字符串将使用上面的 **name** 属性进行设置。第二和第三列的字符串将使用 **subitems(0)** 和 **subitems(1)** 进行设置。
</td></tr></tbody>
</table>