在脚本的 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，它可以调用 **[ScriptInitData](scriptinitdata.zh.md).AddColumn** 方法向 Opus [添加自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。这些列可以显示在文件列表和信息提示中，并且可以使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能进行搜索。每次调用 **AddColumn** 都会返回一个 **ScriptColumn** 对象，脚本需要对其进行初始化。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
autogroup</td><td>

*布尔值*</td><td>

如果将其设置为 **True**（这是默认设置），并且文件列表按此列进行 [分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md)，Opus 将根据列值自动生成组。如果您将其设置为 **False**，Opus 将希望您在 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)** 函数中提供分组信息。
</td></tr><tr><td>
autorefresh</td><td>

*布尔值* 或 *整数*</td><td>

设置为 **True**（或 **1**）以强制 Opus 在文件更改时更新此列的值。您还可以将此值设置为 **2** 以强制 Opus 在文件的属性更改时更新值（通常仅在文件修改时间或大小更改时才会更新）。
</td></tr><tr><td>
defsort</td><td>

*整数*</td><td>

此属性允许您控制列的默认排序行为。通常，当用户单击列标题按列进行排序时，该列最初按升序排序，然后再次单击可反转排序顺序。如果您将 **defsort** 设置为 **-1**，则首次单击列标题将按降序排序。日期和大小字段默认设置此行为。
</td></tr><tr><td>
defwidth</td><td>

*整数* 或 *字符串*</td><td>

为您的列指定一个默认宽度，除非文件列表已启用自动调整大小，否则将使用此宽度。如果您指定一个简单的整数值，则表示以平均字符（例如 *12* 指定 12 个平均字符宽）度量的宽度。您还可以通过添加 *px* 后缀（例如 *"150px"* 指定 150 个像素）来指定绝对像素数。
</td></tr><tr><td>
ellipsis</td><td>

*字符串*</td><td>

允许您控制列如何“省略”；也就是说，当其内容太宽而不适合列时会发生什么。默认情况下，字符串的结尾将替换为省略号 (...)。可用的标志为：

|     |                                             |
|-----|---------------------------------------------|
| m   | 使用中间省略号，而不是结尾省略号 |
</td></tr><tr><td>
graph_colors</td><td>

*对象:***[Vector](vector.zh.md)**</td><td>

对于图形列，指定第一个图形颜色集。只要其百分比低于阈值，该图形就会以这些颜色显示。  
您可以指定单一颜色（以 *r,g,b* 或 *\#rrggbb* 格式），在这种情况下，该图形将为纯色，或者指定恰好五种颜色来配置图形的渐变。在第二种情况下，这五种颜色分别对应于 *外部亮*、*内部亮*、*内部暗*、*外部暗* 和 *纯色*。前四个控制渐变，第五个（纯色）在禁用渐变时使用。 

**graph_colors** 属性返回一个 **[Vector](vector.zh.md)**；您需要使用 **push_back()** 方法将您的颜色添加到其中。
</td></tr><tr><td>
graph_colors2</td><td>

*对象:***[Vector](vector.zh.md)**</td><td>

类似于 **graph_colors**，此属性允许您为图形列配置第二组颜色，当图形值超过阈值时将使用此颜色组。
</td></tr><tr><td>
graph_threshold</td><td>
</td><td>

对于图形列，指定将图形从第一组颜色切换到第二组颜色的百分比阈值（例如，蓝色图形变为红色表示驱动器几乎已满）。将阈值设置为 **-1** 以完全禁用第二组颜色。
</td></tr><tr><td>
grouporder</td><td>

*字符串*</td><td>

如果 **autogroup** 属性设置为 **False**，那么 **grouporder** 属性允许您控制列的组出现的顺序。应以分号分隔在字符串中列出每个组，按所需顺序分隔（例如 *"Never Modified;Modified"*）。如果未提供，组将默认按字母顺序列序。
</td></tr><tr><td>
header</td><td>

*字符串*</td><td>

如果设置此属性，则此列添加到文件窗口时将在列标题中显示定义的字符串。如果未设置，将使用 **label** 值。
</td></tr><tr><td>
infotiponly</td><td>

*布尔值*</td><td>

如果您希望您的列仅可用于 [信息提示](/Manual/file_types/filetype_editor/info_tip.zh.md) 中，则将其设置为 **True**。如果您列花费大量时间来返回值时，您可能需要这样做，在这种情况下，用户可能只希望在信息提示中使用它，以便他们可以按需查看值。如果设置为 **False**（默认值），则该列将无处可用。
</td></tr><tr><td>
justify</td><td>

*字符串*</td><td>

此字段允许您控制列的对齐方式。如果未指定，则默认左对齐列。可接受的值为 *居中*、*左*、*右* 和 *路径*。
</td></tr><tr><td>
keyscroll</td><td>

*布尔值*</td><td>

如果将其设置为 **True**，并且用户启用了 **针对排序字段特定的键滚动** 配置选项，则您的列将参与此特殊模式。
</td></tr><tr><td>
label</td><td>

*字符串*</td><td>

使用此设置来设置列的标签。当列添加到详细资料或高级模式文件列表中时（除非被 **header** 属性覆盖），以及在诸如 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中诸如的各种列列表中，将在列标题中显示此标签。
</td></tr><tr><td>
match</td><td>

**[Vector](vector.zh.md):***string*</td><td>

如果您向此 **[Vector](vector.zh.md)** 添加字符串（例如通过 **push_back** 方法），则在使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 函数根据此列进行搜索时，它将用于提供可能的候选项的下拉列表。
</td></tr><tr><td>
maxstars</td><td>

*整数*</td><td>

如果列类型设置为 *星星*，则此属性允许您指定要使用的最大星星数。这用于确保列大小正确。
</td></tr><tr><td>
method</td><td>

*字符串*</td><td>

这是您脚本中提供新列实际值的方法的名称。通常将其设置为 *OnXXXXX*，其中 *XXXXX* 是命令的名称，然而可以使用任何方法名称。

调用方法时，将向它传递一个单独的参数，即 **[ScriptColumnData](scriptcolumndata.zh.md)** 对象。通常将此方法称为 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)**。
</td></tr><tr><td>
multicol</td><td>

*布尔值*</td><td>

如果您的脚本实现了多个需要进行公共计算的列，您可能希望设置 **multicol** 属性。如果将其设置为 **True**，则列处理函数可以选择同时返回多列的数据，而不仅仅是它被调用的特定列。
当调用程序句柄时，**[ScriptColumnData](scriptcolumndata.zh.md)** 对象将不包含通常的 **group**、**sort**、**type** 和 **value** 属性。相反，它将具有一个 **columns** 属性，指向可用于一次为一列或多列设置值的 **[Map](map.zh.md)**。

例如，您可能会这样设置名为 *MyColumn* 的列的值：

*scriptColData.columns("MyColumn").value = "My Column Value";*
| 用户数据 | *变体* | 允许您将数据值与一列关联。此值将以 **[ScriptColumnData](scriptcolumndata.zh.md).userdata** 属性的形式传递给您的列处理程序 |
|---|---|---|