**DialogListColumns** 对象可用于查询或修改脚本对话框中详细信息模式列表视图控件中的列。使用 **[Control](control.zh.md).columns** 属性来获取 **DialogListColumns** 对象。

可以枚举此对象以查询当前的列。每列由 DialogListColumn 对象表示。

| 方法名 | 参数 | 返回类型 | 说明 |
| --- | --- | --- | --- |
| AddColumn | <string:name> | *int* | 向列表视图中添加新列并返回新列的索引。 |
| AutoSize | *none* | *none* | 自动调整列表视图中所有列的大小以适应其内容。 |
| DeleteColumn | <int:index> | *none* | 删除指定列。 |
| GetColumnAt | <int:index> | *object:* DialogListColumn | 返回表示指定位置的列的 DialogListColumn 对象。 |
| GetDisplayOrder | *none* | object:Vector | 返回列表的列在屏幕上显示的顺序。如果之前通过 SetDisplayOrder 更改了顺序，则此顺序可能与其自然顺序不同。该向量包含按显示顺序排列的每个列的索引。例如，如果你创建了一个有 3 列的列表（索引为 0、1 和 2），并将最后一列（2）移动到开头，则返回的向量将包含三个整数：2、0 和 1。 |
| InsertColumn | <string:name> <int:position> | *int* | 在指定位置向列表视图中插入新列并返回新列的索引。 |
| SetDisplayOrder | <int:indexA> <int:indexB> <int:indexC> ... 或 <Vector:indexes> | *none* | 更改列表的列显示顺序。在希望将一个或多个列放在主列之前时，这将特别有用，而在创建列时这样做是不可能的（这是因为 Windows 列表控件的行为）。主列很特殊，它唯一可以有复选框或可编辑标签，但你可能并不希望它始终首先显示。既可以直接将列索引作为参数传递，也可以将具有相同内容的整数向量（或大多数其他集合类型）传递。例如，如果你创建了一个有 3 列的列表（索引为 0、1 和 2），并且希望将最后一列（2）移动到开头： *SetDisplayOrder(2,0,1)* 这只会更改列在屏幕上显示的顺序；之后，你在代码中使用的列索引不会发生变化。 |