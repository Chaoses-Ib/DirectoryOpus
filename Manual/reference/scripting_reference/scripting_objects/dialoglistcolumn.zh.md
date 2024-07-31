# DialogListColumn

**DialogListColumn** 对象表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中 *详细信息* 模式 *列表视图* 控件中的一个列。使用 **[Control](control.zh.md).columns** 属性获取一个 **[DialogListColumns](dialoglistcolumns.zh.md)** 对象，然后对其进行枚举以获取单个 **DialogListColumn** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
name</td><td>

*string*</td><td>
返回或设置列的名称。
</td></tr><tr><td>
resize</td><td>

*bool*</td><td>

如果要使此列在列表视图水平调整大小时自动调整大小，请将此属性设置为 **True**。一次只能将一个列设置为自动调整大小。
</td></tr><tr><td>
sort</td><td>

*int*</td><td>

如果列表视图当前按此列正向排序，则返回 **1**；如果当前按此列反向排序，则返回 **-1**；否则返回 **0**。设置此属性将重新排序列表。
</td></tr><tr><td>
width</td><td>

*int*</td><td>

返回或设置列的宽度（以像素为单位）。将其设置为 **-1** 以自动调整列的大小以适合其内容。您可以使用 [DialogListColumns](dialoglistcolumns.zh.md)**.AutoSize** 方法一次自动调整所有列的大小。
</td></tr></tbody>
</table>