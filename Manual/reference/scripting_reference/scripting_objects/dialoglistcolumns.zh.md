# DialogListColumns

**DialogListColumns** 对象允许您查询或修改 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中 *Details* 模式 *列表视图* 控件中的列。使用 **[Control](control.zh.md).columns** 属性获取 **DialogListColumns** 对象。

您可以枚举此对象来查询当前列。每列由 **[DialogListColumn](dialoglistcolumn.zh.md)** 对象表示。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>

\<string:name\></td><td>

*int*</td><td>
在列表视图中添加新列，并返回新列的索引。
</td></tr><tr><td>
AutoSize</td><td>

*none*</td><td>

*none*</td><td>
自动调整列表视图中所有列的大小以适合其内容。
</td></tr><tr><td>
DeleteColumn</td><td>

\<int:index\></td><td>

*none*</td><td>
删除指定的列。
</td></tr><tr><td>
GetColumnAt</td><td>

\<int:index\></td><td>

*object:*  
**[DialogListColumn](dialoglistcolumn.zh.md)**</td><td>

返回表示指定位置处的列的 **[DialogListColumn](dialoglistcolumn.zh.md)** 对象。
</td></tr><tr><td>
GetDisplayOrder</td><td>

*none*</td><td>

object:**[Vector](vector.zh.md)**</td><td>

返回列表中的列在屏幕上显示的顺序。如果您之前通过 **SetDisplayOrder** 更改了此顺序，则此顺序可能与它们的自然顺序不同。
向量包含每个列在显示顺序中的索引。例如，如果您创建了一个包含三列（索引为 0、1、2）的列表，并将最后一列（2）移动到开头，则返回的向量将包含三个整数：2、0、1。
</td></tr><tr><td>
InsertColumn</td><td>

\<string:name\>  
\<int:position\></td><td>

*int*</td><td>
在列表视图中指定的位置插入新列，并返回新列的索引。
</td></tr><tr><td>
SetDisplayOrder</td><td>

\<int:indexA\>  
\<int:indexB\>  
\<int:indexC\>  
...  
或  
\<**[Vector](vector.zh.md)**:indexes\></td><td>

*none*</td><td>

更改列表中列的显示顺序。
这在您希望将一个或多个列放置在主列之前时特别有用，在最初创建列时（由于 Windows 列表控件的行为方式）这不可能。主列是特殊的，因为它是在主列中唯一的可以具有复选框或可编辑标签的列，但您可能并不总是希望它首先显示。
您可以直接将列索引作为参数传递，也可以将一个包含相同内容的整数向量的向量（或大多数其它集合类型）传递。
例如，如果您创建了一个包含三列（索引为 0、1、2）的列表，并且希望将最后一列（2）移动到开头：*SetDisplayOrder(2,0,1)*
这只会更改列在屏幕上显示的顺序；您在代码中使用的列索引之后不会改变。
</td></tr></tbody>
</table>