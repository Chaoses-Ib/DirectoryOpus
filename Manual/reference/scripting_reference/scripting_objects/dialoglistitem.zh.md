# DialogListItem

**DialogListItem** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中 *组合框* 或 *列表框* 控件中的一个项目。它由 **[Control](control.zh.md).GetItemAt** 和 **[Control](control.zh.md).GetItemByName** 方法返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bg</td><td>

*string*</td><td>

设置或查询用于该项目背景（填充）的颜色。格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。
目前仅 *列表视图* 控件中的项目支持此属性。
</td></tr><tr><td>
checked</td><td>

*int*</td><td>

对于启用了复选框的 *列表视图* 控件，返回或设置项目的选中状态。
选中状态为 **0**（未选中）、**1**（选中）、**2**（不确定）、**3**（未选中/禁用）、**4**（选中/禁用）、**5**（不确定/禁用）。
</td></tr><tr><td>
data</td><td>

*int*</td><td>
返回或设置与该项目关联的可选数据值。
</td></tr><tr><td>
disabled</td><td>

*bool*</td><td>

对于 *列表视图* 控件，返回或设置该项目的禁用状态。当 *列表视图* 项目被禁用时，它将以灰色显示，并且无法被选中或右键单击。
</td></tr><tr><td>
fg</td><td>

*string*</td><td>

设置或查询用于文本（前景色）的颜色。格式为 *\#RRGGBB*（十六进制）或 *RRR,GGG,BBB*（十进制）。
目前仅 *列表视图* 控件中的项目支持此属性。
</td></tr><tr><td>
group</td><td>

*int*</td><td>

返回或设置该项目所属的 *列表视图* 组。
</td></tr><tr><td>
icon</td><td>

*string*</td><td>

对于 *列表视图* 控件，返回或设置与该项目关联的图标。您可以指定文件或文件夹的路径以使用其图标，或指定文件扩展名（例如 ".txt"）以使用通用文件类型图标。您还可以将其设置为 "dir"、"file"、"ftp" 和 "ftps" 以使用通用图标。您还可以从 DLL 或 EXE 中提取图标，方法是提供文件的路径，然后用逗号分隔，再提供文件中图标的索引。
</td></tr><tr><td>
index</td><td>

*index*</td><td>

返回该项目在控件中从 0 开始的索引。

对于组合编辑框，如果用户输入了字符串而不是从列表中选择一个，则将返回 **-1**。他们输入的字符串可以通过 **name** 属性检索。
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

返回或设置该项目将以其显示的文本样式。您应该提供一个包含以下一个或多个标志的字符串："b"（粗体）、"i"（斜体）、"u"（下划线）。
目前仅 *列表视图* 控件中的项目支持此属性。
</td></tr><tr><td>
subitems</td><td>

*collection:string*</td><td>

对于处于 *详细信息* 模式下的列表视图控件，返回一个字符串集合，允许您查询或更改项目子项目的文本。集合中将包含列表中每个列的字符串，不包括第一列。

例如，假设列表总共有三列，则第一列的字符串将使用上面的 **name** 属性设置。第二列和第三列的字符串将使用 **subitems(0)** 和 **subitems(1)** 设置。
</td></tr></tbody>
</table>