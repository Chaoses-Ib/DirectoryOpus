**ScriptColumnData** 对象传递给脚本定义的入口点，用于任何 [自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)，通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 添加。这些事件中的方法名称由该脚本定义，但通常被称为 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)**。注意，**group**、**sort**、**type** 和 **value** 字段是可设置的，它是您的方法为该列返回值的途径。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
col</td><td>

*string*</td><td>

提供 Opus 希望脚本返回其值的列的名称。如果您使用同一个 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)** 方法提供多个列，则可以使用此方法区分各个列。
</td></tr><tr><td>
columns</td><td>

*object:***[Map](map.zh.md)**</td><td>

如果 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值在添加该列时设置为 **True**，则此属性提供一个 **[Map](map.zh.md)**，允许您一次返回一个或多个列的值。

如果您的脚本返回多列，且所有列都共享相同的计算（例如读取某个文件夹的内容），则可能想要使用此方法。这样，如果第二次及后续列被调用，您可以避免重复可能耗时的操作。

**[Map](map.zh.md)** 包含一个成员元素，用于每个列。每个成员元素都具有 **group**、**group_type**、**sort**、**type**、**userdata** 和 **value** 属性，这些属性等同于以下描述的属性。

例如，您可以像这样设置名为 *MyColumn* 的列的值：

*scriptColData.columns("MyColumn").value = "My Column Value";*  
在填充数据前，您应该检查该列是否存在于映射中。在某些情况下，Opus 只会请求某些列的加载项支持，而不是全部。  
如果您没有填充 Opus 仍需要的一个列的数据，Opus 就会再次调用您的方法以请求该列数据，并在 **col** 属性中显示其名称（但仍处于多列模式）。如果某个数据块的计算产生了部分列的值而不是所有列的值，您可以利用此特性。如果数据不可用，您不必填充每列，但至少应该填充 **col** 列。  
因此，在使用多列模式时，您应该*始终*为花费时间计算的任何列设置某种值，即使计算结果是该列中不应显示任何内容。如果不应显示任何内容，请将该值设置为一个空字符串（即使该列通常显示数字或其它类型的数据，这样做也没关系）。如果您根本未设置任何值，Opus 将假定您尚未计算该列，并且可能会再次调用您的脚本以获取该列，这可能导致您在已知该列为空时重新计算，并浪费时间。
</td></tr><tr><td>
group</td><td>

*string*</td><td>

如果 **[ScriptColumn](scriptcolumn.zh.md).autogroup** 值在添加该列时设置为 **False**，您应该设置此值以指示将此文件分组在该列中后文件的放置位置。如果您不提供一个组，则此文件将进入 *Unspecified* 组。如果 **autogroup** 设置为 **True**，则此值将被忽略。

请注意，如果 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值在添加该列时设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
group_type</td><td>

*string*</td><td>

如果组通过 **group** 属性设置，则 **group_type** 允许您使用与 **type** 字段相同的关键字来控制组标题的格式（例如，您可以提供一个数字，并通过将 *group_type="size"* 设置来将组标题格式化为文件大小）。

请注意，如果 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值在添加该列时设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，该对象表示 Opus 希望脚本为其返回列值的某个文件或文件夹。
</td></tr><tr><td>
sort</td><td>

*variant*</td><td>

使您可以通过提供一个 *排序键* 来控制该列的排序顺序，该 *排序键* 可以不同于 **value**。如果提供该排序键并且列按该列进行排序，Opus 将使用此字段的值而不是 **value** 值来定位该项。

请注意，如果 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值在添加该列时设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，该对象表示包含该项的标签页。
</td></tr><tr><td>
type</td><td>

*string*</td><td>

使您可以按每个文件/文件夹为基础覆盖列的默认类型（通过 **[ScriptColumn](scriptcolumn.zh.md).type** 在添加列时设置）。  
如果没有指定该类型，并且也没有指定一个默认类型，则列将默认为纯文本。  
注意，如果在添加该列时将 **[ScriptColumn](scriptcolumn.zh.md).multicol** 值设置为 **True**，则此属性将在 **columns** **[Map](map.zh.md)** 中找到。  
可接受的值为：**number**： \\ \\ \\ \\ 该列显示整数。**double**： \\ \\ \\ \\ 该列显示浮点数（小数）。**size**： \\ \\ \\ \\ 该列显示文件大小（自动显示字节、KB、MB 等）。**zip**： \\ \\ \\ \\ 该列显示文件大小（使用 Zip 文件大小的设置）。**graph**： \\ \\ \\ \\ 该列显示一个条形图（期望值介于 0 到 100 之间）。**igraph**： \\ \\ \\ \\ 该列显示一个条形图。**percent**： \\ \\ \\ \\ 该列显示一个百分比。**date**： \\ \\ \\ \\ 该列显示一个日期。**time**： \\ \\ \\ \\ 该列显示一个时间。**datetime**： \\ \\ \\ \\ 该列同时显示一个日期和一个时间。**stars**： \\ \\ \\ \\ 该列显示星星（类似于内置的 *评级* 列）。**value** 应采用“x”或“x/y”的形式。

对于 *date*、*time* 和 *datetime* 列，您还可以指定 **utc** 以将值自动从 UTC 转换为本地时间（例如 **datetime,utc**）。对于 *number* 和 *double* 列，您还可以指定 **signed** 以将值视为有符号值，而不是无符号值（例如 **number,signed**）。上述选项是您可以通过 **[ScriptColumn](scriptcolumn.zh.md).type** 指定的选项的一个子集，因为并非所有选项在每个文件/文件夹上都适用。请注意，如果您在一个列中混合不同的类型，则通过该列排序或使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能按该列搜索时，您获得的结果可能难以预测。
| 属性 | 类型 | 描述 |
|---|---|---|
| value | *variant* | 此字段是您的方法如何为您的列返回实际值的方式 - 也就是说，对用户显示的信息在每行文件和文件夹中都是此列。 |
| userdata | *variant* | 当添加此列时，此列会通过 **[ScriptColumn](scriptcolumn.zh.md).userdata** (如果有) 返回与该列相关联的值。 |