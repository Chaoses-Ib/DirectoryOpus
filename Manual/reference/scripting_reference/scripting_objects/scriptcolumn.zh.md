# ScriptColumn

在一个脚本的 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，它可以调用 **[ScriptInitData](scriptinitdata.zh.md).AddColumn** 方法来 [添加自定义列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md) 到 Opus。这些列可以在文件列表和信息提示中显示，并且可以使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能进行搜索。每次调用 **AddColumn** 都将返回一个 **ScriptColumn** 对象，该对象需要由脚本初始化。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
autogroup</td><td>

*bool*</td><td>

如果将此设置为 **True**（默认值），并且文件列表按此列 [分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md)，Opus 将根据列值自动生成组。如果将其设置为 **False**，Opus 将期望您在 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)** 函数中提供分组信息。
</td></tr><tr><td>
autorefresh</td><td>

*bool* 或 *int*</td><td>

设置为 **True**（或 **1**）以强制 Opus 在文件更改时更新此列的值。您还可以将此值设置为 **2** 以强制 Opus 在文件属性更改时更新值（通常只有在文件修改时间或大小更改时才会更新）。
</td></tr><tr><td>
defsort</td><td>

*int*</td><td>

此属性允许您控制列的默认排序行为。通常，当用户单击列标题按列排序时，列最初将按升序排序，然后再次单击将反转排序顺序。如果将 **defsort** 设置为 **-1**，则第一次单击列标题将按降序排序。日期和大小字段默认设置此行为。
</td></tr><tr><td>
defwidth</td><td>

*int* 或 *string*</td><td>

指定列的默认宽度，除非文件列表启用了自动调整大小。如果指定一个简单的整数值，则表示以平均字符数衡量的宽度（例如 *12* 指定 12 个平均字符宽）。您也可以通过添加 *px* 后缀来指定像素的绝对数量（例如 *"150px"* 指定 150 像素）。
</td></tr><tr><td>
ellipsis</td><td>

*string*</td><td>

允许您控制列的“省略号”方式；也就是说，当列的内容太宽而无法容纳在列中时会发生什么。默认情况下，字符串的结尾将替换为省略号 (...)。可用的标志是：

|     |                                             |
|-----|---------------------------------------------|
| m   | 使用中间省略号而不是结尾省略号 |
</td></tr><tr><td>
graph_colors</td><td>

*object:***[Vector](vector.zh.md)**</td><td>

对于图形列，指定第一个图形颜色集。只要图形的百分比低于阈值，就会以这些颜色显示图形。  
您可以指定单一颜色（以 *r,g,b* 或 *\#rrggbb* 格式），在这种情况下，图形将是一个平坦的纯色，或者指定恰好五种颜色来配置图形的渐变。在第二种情况下，五种颜色分别对应 *外部亮*、*内部亮*、*内部暗*、*外部暗* 和 *平坦*。前四种颜色控制渐变，第五种（平坦）颜色在禁用渐变时使用。

**graph_colors** 属性返回一个 **[Vector](vector.zh.md)**；您需要使用 **push_back()** 方法将颜色添加到其中。
</td></tr><tr><td>
graph_colors2</td><td>

*object:***[Vector](vector.zh.md)**</td><td>

与 **graph_colors** 相似，此属性允许您为图形列配置第二组颜色，当图形值超过阈值时将使用这组颜色。
</td></tr><tr><td>
graph_threshold</td><td>
</td><td>

对于图形列，指定图形从第一组颜色切换到第二组颜色的百分比阈值（例如，蓝色图形变为红色以指示驱动器几乎已满）。将阈值设置为 **-1** 以完全禁用第二组颜色。
</td></tr><tr><td>
grouporder</td><td>

*string*</td><td>

如果 **autogroup** 属性设置为 **False**，**grouporder** 属性允许您控制列组的显示顺序。每个组应以所需的顺序列在字符串中，以分号 (;) 分隔（例如 *"Never Modified;Modified"*）。如果未提供，组将默认按字母顺序排序。
</td></tr><tr><td>
header</td><td>

*string*</td><td>

如果设置了此属性，则它定义了将在此列添加到文件窗口时在列标题中显示的字符串。如果未设置，将使用 **label** 值。
</td></tr><tr><td>
infotiponly</td><td>

*bool*</td><td>

如果希望您的列仅供 [信息提示](/Manual/file_types/filetype_editor/info_tip.zh.md) 使用，请将其设置为 **True**。如果您的列需要大量时间才能返回值，您可能希望这样做，在这种情况下，用户可能只想在信息提示中使用它，以便他们可以按需查看值。如果设置为 **False**（默认值），则该列将在任何地方都可用。
</td></tr><tr><td>
justify</td><td>

*string*</td><td>

此字段允许您控制列的对齐方式。如果未指定，列默认左对齐。可接受的值是 *center*、*left*、*right* 和 *path*。
</td></tr><tr><td>
keyscroll</td><td>

*bool*</td><td>

如果将其设置为 **True**，并且用户启用了 **排序字段特定按键滚动** 配置选项，那么您的列将参与此特殊模式。
</td></tr><tr><td>
label</td><td>

*string*</td><td>

使用此方法设置列的标签。当列添加到 Details/增强模式文件列表（除非被 **header** 属性覆盖）时，以及在各种列列表中（例如在 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中）都会显示此标签。
</td></tr><tr><td>
match</td><td>

**[Vector](vector.zh.md):***string*</td><td>

如果将字符串添加到此 **[Vector](vector.zh.md)**（例如通过 **push_back** 方法），它将用于在使用 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能搜索此列时提供可能的值的下拉列表。
</td></tr><tr><td>
maxstars</td><td>

*int*</td><td>

如果列类型设置为 *stars*，则此属性允许您指定将使用的最大星数。这用于确保列的大小正确。
</td></tr><tr><td>
method</td><td>

*string*</td><td>

这是脚本中提供新列的实际值的该方法的名称。这通常设置为 *OnXXXXX*，其中 *XXXXX* 是命令的名称，但可以使用任何方法名称。

当调用方法时，它将传递一个参数，即 **[ScriptColumnData](scriptcolumndata.zh.md)** 对象。通常，此方法称为 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)**。
</td></tr><tr><td>
multicol</td><td>

*bool*</td><td>

如果您的脚本实现多个需要进行共同计算才能执行的列，您可能希望设置 **multicol** 属性。如果将其设置为 **True**，则您的列处理程序函数可以选择同时返回多个列的数据，而不仅仅是它正在调用的特定列。

当调用您的处理程序时，**[ScriptColumnData](scriptcolumndata.zh.md)** 对象将不包含通常的 **group**、**sort**、**type** 和 **value** 属性。相反，它将具有一个 **columns** 属性，该属性指向一个 **[Map](map.zh.md)**，该 **[Map](map.zh.md)** 允许您一次设置一个或多个列的值。

例如，您可以这样设置名为 *MyColumn* 的列的值：

*scriptColData.columns("MyColumn").value = "My Column Value";*
</td></tr><tr><td>
name</td><td>

*string*</td><td>

这是列的原始名称。这决定了可以用于以编程方式控制列的名称（例如，**Set COLUMNSTOGGLE** 命令可用于按名称切换列的显示）。

自定义列的名称由提供该列的脚本的名称和该列本身的原始名称组合而成，并在前缀 *scp:* 之前。例如，如果您的脚本名为 *My Script*，并且您的列名为 *My Column*，则可以使用命令 **Set COLUMNSTOGGLE="scp:My Script/My Column"** 切换此列。如果您不确定任何内容，可以使用按钮编辑器菜单自动构建命令。
</td></tr><tr><td>
namerefresh</td><td>
</td><td>

设置为 **True** 以强制 Opus 在文件名称更改时更新此列的值。
</td></tr><tr><td>
nogroup</td><td>

*bool*</td><td>

设置为 **True** 以防止文件列表按此列分组。
</td></tr><tr><td>
nosort</td><td>

*bool*</td><td>

设置为 **True** 以防止文件列表按此列排序。
</td></tr><tr><td>
timeout</td><td>

*int*</td><td>

Opus 在可能放弃等待列值计算之前的毫秒数。  
默认值为 10000（即 10 秒）。设置为 0（零）以强制 Opus 在所有情况下永远等待。  
超时并不总是适用。当 Opus 请求脚本提供要显示在文件列表中的列数据时，不会使用超时，因为计算在后台发生并且不会阻碍任何事情。但是，如果列在某些会阻碍其它事情的情况下花费的时间太长，Opus 可能会放弃等待。这是为了避免在脚本陷入无限循环时永远阻塞。  
查找过滤器和打印/导出文件夹列表对话框是使用超时从脚本列请求数据的两个示例。计算没有大小限制的文件的哈希值的列是一个可能需要很长时间并且需要增加超时或将其设置为 0 的示例。
</td></tr><tr><td>
type</td><td>

*string*</td><td>

此字段允许您设置列的默认类型。

如果未指定，列默认设置为纯文本。

可接受的值是：

|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **number**      | 列显示整数                                                                                                                                |
| **double**      | 列显示浮点数（小数）                                                                                                                       |
| **size**        | 列显示文件大小（自动显示字节、KB、MB 等）                                                                                                |
| **zip**         | 列显示文件大小（使用 Zip 文件大小的设置）                                                                                                      |
| **duration**    | 列显示持续时间（期望以秒为单位的值）。仅在需要时才会显示小时。                                                                               |
| **durationh**   | 列显示持续时间。始终显示小时。                                                                                                                    |
| **graph**       | 列显示条形图（期望的值为 0 到 100）                                                                                                            |
| **graphrel**    | 列显示条形图。Opus 自动跟踪提供的最小值和最大值并相应地缩放图形                                                                        |
| **graphrel0**   | 与 **graphrel** 相似，但最小值始终为 0，Opus 会跟踪最大值                                                                               |
| **igraph**      | 列显示反转的条形图                                                                                                                           |
| **igraphrel**   | 相对于 0 的反转相对条形图                                                                                                                 |
| **igraphrel0**  | 相对于 0 的反转条形图                                                                                                            |
| **percent**     | 列显示百分比                                                                                                                                   |
| **percentrel**  | 相对百分比                                                                                                                                 |
| **percentrel0** | 相对于 0 的百分比                                                                                                                            |
| **date**        | 列显示日期                                                                                                                                    |
| **time**        | 列显示时间                                                                                                                                    |
| **datetime**    | 列显示日期和时间                                                                                                                            |
| **stars**       | 列显示星级（类似于内置的 *Rating* 列）                                                                                                        |

对于纯文本列，您可以指定 **numericsort** 或 **nonumericsort** 来覆盖文件夹选项中的 *"数字顺序文件名排序"* 设置。类似地，**wordsort** 或 **nowordsort** 可用于覆盖 *"单词排序（对连字符等进行特殊处理）"* 设置。您也可以组合这两个选项，例如 **nonumericsort,nowordsort** 以仅请求基本排序。对于尊重文件夹选项排序设置的纯文本数据，请将类型保留为空，或将其设置为空字符串。

对于 *date*、*time* 和 *datetime* 列，您还可以指定 **utc** 以将值自动从 UTC 转换为本地时间（例如 **datetime,utc**）。

对于 *number* 和 *double* 列，您还可以指定 **signed** 以将值视为有符号值而不是无符号值（例如 **number,signed**）。

对于图形列，您可以使用 **graph_colors**、**graph_colors2** 和 **graph_threshold** 来配置图形的外观。

您的 **[OnScriptColumn](../scripting_events/onscriptcolumn.zh.md)** 方法可以在每个文件的基础上覆盖类型，但是此字段设置默认类型，并且还控制使用您的列搜索时 **[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 功能的行为。
</td></tr><tr><td>
userdata</td><td>

*variant*</td><td>

允许您将数据值与列关联。该值将在您的列处理程序的 **[ScriptColumnData](scriptcolumndata.zh.md).userdata** 属性中传递
</td></tr></tbody>
</table>