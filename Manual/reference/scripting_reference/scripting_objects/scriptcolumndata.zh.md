# ScriptColumnData

**ScriptColumnData** 对象传递给脚本定义的入口点，用于任何由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加的 [自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。这些事件的函数名由脚本本身定义，但通常称为 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)**。请注意，字段 **group**、**sort**、**type** 和 **value** 是可设置的，并且是您的方法返回列值的途径。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
col</td><td>

*string*</td><td>

提供 Opus 希望脚本返回值的列的名称。如果您使用相同的 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)** 方法提供多个列，您可以使用它来区分这些列。
</td></tr><tr><td>
columns</td><td>

*object:***[Map](map.zh.md)**</td><td>

如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性提供一个 **[Map](map.zh.md)**，允许您一次返回一个或多个列的值。

您可能希望使用此方法，如果您的脚本返回多个共享共同计算的列（例如读取文件夹的内容）。这样，当您被调用以获取第二列和后续列时，您可以避免重复可能很耗时的操作。

**[Map](map.zh.md)** 包含每个列的一个成员元素。每个成员元素都具有 **group**、**group_type**、**sort**、**type**、**userdata** 和 **value** 属性，这些属性等同于下面描述的属性。

例如，您可以像这样设置名为 *MyColumn* 的列的值：

*scriptColData.columns("MyColumn").value = "My Column Value";*  
您应该在填充列的数据之前检查列是否在映射中存在。在某些情况下，Opus 仅会请求加载项支持的某些列，而不是所有列。  
如果您没有为 Opus 仍然需要的列填写数据，Opus 将再次调用您的方法以请求它，并在 **col** 属性中包含其名称（但仍然处于多列模式）。如果计算一个数据会导致某些列的值但不是所有列的值，您可以利用这一点。您不需要填充所有列，如果数据不可用，但您至少应该填充 **col** 列。  
由于以上原因，在使用多列模式时，您*始终*应该为计算过的任何列设置某种值，即使计算结果是该列不应显示任何内容。如果应该隐藏任何内容，请将值设置为一个空字符串（即使该列通常显示数字或其它类型的数据也可以这样做）。如果您根本没有设置任何值，Opus 会假设您尚未计算该列，并可能再次调用您的脚本以请求它，这可能会导致您浪费时间重新计算您已经知道是空白的列。
</td></tr><tr><td>
group</td><td>

*string*</td><td>

如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).autogroup** 值设置为 **False**，您应该将此值设置为指示当列表按您的列分组时该文件应放入的组。如果您没有提供组，则此文件将进入 *未指定* 组。如果 **autogroup** 设置为 **True**，则忽略此值。

请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
group_type</td><td>

*string*</td><td>

如果组是通过 **group** 属性设置的，**group_type** 允许您使用与 **type** 字段相同的关键字控制组标题的格式（例如，您可以提供一个数字，并通过设置 *group_type="size"* 使组标题格式化为文件大小）。

请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，该对象表示 Opus 希望脚本返回列值的 文件或文件夹。
</td></tr><tr><td>
sort</td><td>

*variant*</td><td>

允许您通过提供一个与 **value** 不同的 *排序键* 来控制列的排序顺序。如果提供排序键，并且列表按您的列排序，Opus 将使用此字段的值来定位此项，而不是使用 **value** 值。

请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，该对象表示包含该项的标签。
</td></tr><tr><td>
type</td><td>

*string*</td><td>

允许您在每个文件/文件夹的基础上覆盖列的默认类型（在添加列时通过 **[ScriptColumn](scriptcolumn.zh.md).type** 设置）。  
如果未指定，并且也没有指定默认类型，则列默认为纯文本。  
请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。  
可接受的值为： **number**: \\ \\ \\ \\ 该列显示整数。 **double**: \\ \\ \\ \\ 该列显示浮点数（小数）。 **size**: \\ \\ \\ \\ 该列显示文件大小（自动显示字节、KB、MB 等）。 **zip**: \\ \\ \\ \\ 该列显示文件大小（使用 Zip 文件大小的设置）。 **graph**: \\ \\ \\ \\ 该列显示条形图（预期值为 0 到 100）。 **igraph**: \\ \\ \\ \\ 该列显示反向条形图。 **percent**: \\ \\ \\ \\ 该列显示百分比。 **date**: \\ \\ \\ \\ 该列显示日期。 **time**: \\ \\ \\ \\ 该列显示时间。 **datetime**: \\ \\ \\ \\ 该列同时显示日期和时间。 **stars**: \\ \\ \\ \\ 该列显示星号（类似于内置的 *Rating* 列）。**value** 应采用 "x" 或 "x/y" 的形式。

对于 *date*、*time* 和 *datetime* 列，您还可以指定 **utc**，以便将值自动从 UTC 转换为本地时间（例如 **datetime,utc**）。对于 *number* 和 *double* 列，您还可以指定 **signed**，以便将值视为有符号而不是无符号（例如 **number,signed**）。以上选项是您可以通过 **[ScriptColumn](scriptcolumn.zh.md).type** 指定的选项的子集，因为并非所有选项在每个文件/文件夹的基础上都有意义。请注意，如果您在一个列中混合了不同的类型，那么按此列排序或使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能在您的列上搜索时获得的结果可能难以预测。
</td></tr><tr><td>
value</td><td>

*variant*</td><td>

此字段是您的方法如何返回列的实际值 - 也就是说，为每个文件和文件夹在该列中显示给用户的 信息。

如果为该列设置了类型（通过 **ScriptColumnData.type** 或 **[ScriptColumn](scriptcolumn.zh.md).type** 设置），则 Opus 将尝试将提供的值转换为指定的类型。如果未设置类型，则 Opus 将将该值视为纯文本字符串。

如果您没有通过 **sort** 字段提供排序键，则 Opus 还将使用此值来在按该列排序时对列表进行排序。

请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
userdata</td><td>

*variant*</td><td>

此返回值与通过 **[ScriptColumn](scriptcolumn.zh.md).userdata** 添加列时关联的此列的值（如果有）。

请注意，如果在添加列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr></tbody>
</table>