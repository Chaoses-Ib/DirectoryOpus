# Select
**Select** 内部命令用于：

- 显示 *Select* 对话框（在 [简单](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md) 或 [高级](/Manual/basic_concepts/selecting_files/advanced_selection.zh.md) 模式中）
- 全选、取消全选和反选所有文件和文件夹的当前选择
- 根据通配符模式按文件名选取或取消选取文件
- 选取目标中选取的所有源文件，反之亦然
- 选取与已选取文件扩展名匹配的所有文件
- 将 [复选标记](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) 转换到选取中，反之亦然
- 根据选取文件与否隐藏文件
- 按索引选取文件范围
- 按日期和大小选取文件

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*（无参数）*</td><td>
-</td><td>
-</td><td>

显示 *Select* 对话框（根据上次使用的，在 [简单](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md) 或 [高级](/Manual/basic_concepts/selecting_files/advanced_selection.zh.md) 模式中）。

*示例：* `Select`
</td></tr><tr><td>
ADVANCED</td><td>
/O</td><td>

*（无值）*</td><td>

以 [高级](/Manual/basic_concepts/selecting_files/advanced_selection.zh.md) 模式显示 *Select* 对话框。

*示例：* `Select ADVANCED`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter name\>*</td><td>

在高级模式下显示 *Select* 对话框，并已加载指定保存的过滤器。

*示例：* `Select ADVANCED=MyFilter`
</td></tr><tr><td>
ALL</td><td>
/S</td><td>

*（无值）*</td><td>

选取当前源文件列表中的所有文件和文件夹。

*示例：* `Select ALL`
</td></tr><tr><td>
ALLDIRS</td><td>
/S</td><td>

*（无值）*</td><td>

选取当前源文件列表中的所有文件夹。

*示例：* `Select ALLDIRS`
</td></tr><tr><td>
ALLFILES</td><td>
/S</td><td>

*（无值）*</td><td>

选取当前源文件列表中的所有文件。

*示例：* `Select ALLFILES`
</td></tr><tr><td>
DATE</td><td>
/K</td><td>

*\<date\>*</td><td>

选取上次修改时间戳与指定日期匹配的文件。您可以指定：

- 仅日期，格式为 *YYYY-MM-DD*
- 仅时间，格式为 *HH:MM*（忽略秒）
- 日期和时间，格式为 *YYYY-MM-DD HH:MM* 请注意，由于两个值之间的空格字符，因此指定日期和时间都需要在值周围加上引号。

您还可以使用日期之前的 **\>**（大于）来匹配所有比指定日期新的文件，或者使用日期之前的 **\<**（小于）来匹配所有比指定日期旧的文件。

您还可以指定一个 *年龄* 而不是 *日期* 来进行测试。例如，要选取所有旧于 5 天的文件，您可以指定 `Select DATE ">5 days"`。年龄选择过程的有效关键字为 **day**、**week**、**month**、**year**、**hour**、**minute**、**second**。

*示例：* `Select *.jpg DATE "\>2012-06-15 10:00"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<date1\>***..***\<date2\>*</td><td>

选取上次修改时间戳介于两个指定日期之间的文件。这两个日期均按上述格式提供。

*示例：* `Select DATE 2012-01-01..2012-12-31 TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**oldest**</td><td>

选取当前源文件列表中最旧的项。您可以将其与 **PATTERN** 参数结合使用，选取特定类型文件中最早的文件。

*示例：* `Select *.doc DATE=oldest`
</td></tr><tr><td>
</td><td>
</td><td>

**newest**</td><td>

选取当前文件列表中最新的项。

*示例：* `Select DATE=newest DESELECTNOMATCH`
</td></tr><tr><td>
</td><td>
</td><td>

**created**</td><td>

通常此命令会考虑每个文件的上次修改时间戳，但是，通过指定此关键字，您可以使其查看创建时间。

*示例：* `Select *.(zip|7z|rar) DATE=created,2010-03-10..2010-03-17`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

考虑创建和最后修改的时间戳。

*示例：* `Select DATE=both,newest`
</td></tr><tr><td>
</td><td>
</td><td>

**next**</td><td>

修改 **newest** 和 **oldest** 参数的行为。通常，`Select DATE=newest` 将选取列表中的最新文件。如果它已被选取，则不会发生任何变化。如果您添加 **next** 关键字，Opus 将在每次运行命令时逐步选取下一个最新文件。

*示例：* `Select DATE=next,newest`
</td></tr><tr><td>
DESELECT</td><td>
/S</td><td>

*（无值）*</td><td>

此命令将取消选取文件，而不是选取文件。此命令与 **PATTERN**、**ALLDIRS** 和 **ALLFILES** 参数结合使用。

*示例：* `Select *.jpg DESELECT`
</td></tr><tr><td>
DESELECTNOMATCH</td><td>
/S</td><td>

*（无值）*</td><td>

将取消选择与模式不匹配的文件（通常情况下，不匹配的文件将保持原样）。此方法在使用 **FILTER** 参数选择带有预定义过滤器的文件时也能正常工作。

*示例：* `Select *.doc DESELECTNOMATCH`
</td></tr><tr><td>
DESELECTOTHERTYPE</td><td>
/S</td><td>

*（无值）*</td><td>

与 **TYPE** 参数一起使用以将选择限制为文件或文件夹（或使用 **ALLFILES** 和 **ALLDIRS** 参数），**DESELECTOTHERTYPE** 会导致取消选择所有其它类型的项

*示例：* `Select * TYPE=files DESELECTOTHERTYPE`
</td></tr><tr><td>
DESTTOSOURCE</td><td>
/O</td><td>

*（无值）*</td><td>

选取目标中当前所选源文件列表中的所有文件和文件夹。仅对文件名进行比较，实际上并没有比较文件。

*示例：* `Select DESTTOSOURCE`
</td></tr><tr><td>
</td><td>
</td><td>

**in**</td><td>

选取源文件列表中存在于目标中的所有文件和文件夹。

*示例：* `Select DESTTOSOURCE=in`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

在比较源和目标中选取的文件时，不考虑文件扩展名。例如，如果目标中选择了 **IMGP1234.JPG**，而源中存在 **IMGP1234.WAV**，则会将其选取。

*示例：* `Select DESTTOSOURCE=noext`
</td></tr><tr><td>
</td><td>
</td><td>

**notin**</td><td>

选取源文件列表中目标中不存在的所有文件和文件夹。

*示例：* `Select DESTTOSOURCE=notin`
</td></tr><tr><td>
DUPES</td><td>
/S</td><td>

*（无值）*</td><td>

显示 **Duplicates Selection** 对话框，它允许您在执行 [重复搜索](/Manual/additional_functionality/duplicate_file_finder.zh.md) 后选取文件。

*示例：* `Select DUPES`
</td></tr><tr><td>
EXACT</td><td>
/S</td><td>

*（无值）*</td><td>

指示 PATTERN 参数是文字文件名，而不是通配符或正则表达式。这允许您指定确切的文件名，而无需转义通配符，如 '(' 和 ')”。
*示例:*`Select "Cat Photo (1).jpg" 精确 FILTER`
</td></tr><tr><td>
FILTER</td><td>
/S</td><td>

*(无值)*</td><td>

使用预定义过滤器执行文件选择。过滤器的名称必须作为 **PATTERN** 参数的值提供。过滤器必须在配置中的 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面中预先配置。

你可以使用此功能与 **TYPE** 参数一起，将过滤器限制为仅限于文件或文件夹。

*示例：`Select "Image Files" FILTER`

你还可以通过使用 **[Command](../../scripting_reference/scripting_objects/command.zh.md).SetFilter** 方法将过滤器分配给 **Command** 对象的方式，从脚本中使用此功能。从该对象运行 `Select FILTER` 命令会根据过滤器选择文件。
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

让你在 [文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 中定义过滤器以选择匹配文件。类似于 **FILTER** 参数，但过滤器不需要预定义。

这是一个 **/R** 参数，因此 **FILTERDEF** 关键字后面的所有内容都将被视为该参数的值。

*示例：`Select FILTERDEF 名称匹配 *.zip 和大小匹配 > 2 mb`
</td></tr><tr><td>
FILTERFLAGS</td><td>
/K</td><td>

**选择**</td><td>

选择匹配过滤器的文件（此参数与 **FILTER** 参数结合使用）。这是默认行为。

*示例：`Select Documents FILTER FILTERFLAGS=select`
</td></tr><tr><td>
</td><td>
</td><td>

**取消选择**</td><td>

取消选择匹配过滤器的文件。

*示例：`Select "Music Files" FILTER FILTERFLAGS=deselect`
</td></tr><tr><td>
</td><td>
</td><td>

**隐藏**</td><td>

隐藏匹配过滤器的文件。

*示例：`Select "Temp Files" FILTER FILTERFLAGS=hide`
</td></tr><tr><td>
</td><td>
</td><td>

**显示不匹配项**</td><td>

隐藏不匹配过滤器的文件。

*示例：`Select "Image Files" FILTER FILTERFLAGS=hidenomatch`
</td></tr><tr><td>
FIRST</td><td>
/S</td><td>

*(无值)*</td><td>

选择源文件列表中的第一个项目，取消选择所有其它项目。

*示例：`Select FIRST`
</td></tr><tr><td>
FROMCHECKS</td><td>
/S</td><td>

*(无值)*</td><td>

将选中项的状态转换为选择（将选中选中项，将未选中项取消选择）。这仅适用于 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)。

*示例：`Select FROMCHECKS`
</td></tr><tr><td>
FROMSCRIPT</td><td>
/S</td><td>

*(无值)*</td><td>

当从脚本中运行选择命令时，应使用此命令（例如，通过 **Command.RunCommand**）。它告诉命令在 **Command** 对象本身中选择文件。

*示例：`Func.Command.RunCommand("Select FROMSCRIPT");`
</td></tr><tr><td>
GROUPNAME</td><td>
/O</td><td>

*(无值)*</td><td>

当文件列表被 [分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 时，这让你可以根据文件所在的分组选择文件。当 **GROUPNAME** 在没有关联值的情况下使用时，**PATTERN** 参数的值被用作为要匹配的分组的名称。

下面的示例选择在以 **X** 开头的组中的所有文件。

*示例：`Select X\* GROUPNAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<组名称\>*</td><td>

当为 **GROUPNAME** 参数提供值时，它指定文件组的名称（或通配符模式）。选择操作将仅限于匹配组中的文件和文件夹。

你还可以将此与 **SETFOCUS** 参数一起使用，以将输入焦点赋予组标题。

*示例：`Select *.jpg GROUPNAME Today`  
*示例：`Select NOPATTERN GROUPNAME Yesterday SETFOCUS`
</td></tr><tr><td>
HIDESEL</td><td>
/O</td><td>

*(无值)*</td><td>

隐藏所有选定的项目（包括文件和文件夹）。这与 **PATTERN** 参数一起用于隐藏所有匹配模式的文件，或与 **NOPATTERN** 参数一起用于隐藏所有当前选择的项。

*示例：`Select *。tmp HIDESEL`
</td></tr><tr><td>
</td><td>
</td><td>

**目录**</td><td>

隐藏所有选定的目录。

*示例：`Select HIDESEL=目录 NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**文件**</td><td>

隐藏所有选定的文件。

*示例：`Select HIDESEL=文件 NOPATTERN`
</td></tr><tr><td>
HIDEUNAFFECTED</td><td>
/S</td><td>

*(无值)*</td><td>

与 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 工具一起使用时，这会隐藏列表中未标记为同步的任何项目（已复制或已删除）。

*示例：`Select HIDEUNAFFECTED`
</td></tr><tr><td>
HIDEUNSEL</td><td>
/O</td><td>

*(无值)*</td><td>

隐藏所有未选定的项目（包括文件和文件夹）。这与 **PATTERN** 参数一起使用（不匹配模式的文件将被隐藏），或与 **NOPATTERN** 参数一起使用（所有当前未选定的文件将被隐藏）。

*示例：`Select NOPATTERN HIDEUNSEL`
</td></tr><tr><td>
</td><td>
</td><td>

**目录**</td><td>

隐藏所有未选定的目录。

*示例：`Select HIDEUNSEL=目录 NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**文件**</td><td>

隐藏所有未选定的文件。

*示例：`Select HIDEUNSEL=文件 NOPATTERN`
</td></tr><tr><td>
IGNORECHECKBOXMODE</td><td>
/S</td><td>

*(无值)*</td><td>

该命令将像文件列表不在 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) 时一样，即使它确实在复选框模式中也是如此。通常，选择命令会在复选框模式下选中和取消选中文件，但此参数允许你修改通常的文件选择，而不用管复选框。特别是，它允许脚本将通常的选择和焦点项设置为特定文件，而不用修改复选框状态。

*示例：`Select "dopus.exe" IGNORECHECKBOXMODE`
</td></tr><tr><td>
INVERT</td><td>
/S</td><td>

*(无值)*</td><td>

反转源文件列表中所有项目的选中状态。

*示例：`Select INVERT`
</td></tr><tr><td>
LAST</td><td>
/S</td><td>

*(无值)*</td><td>

选择源文件列表中的最后一个项目，取消选择所有其它项目。

*示例：`Select LAST`
</td></tr><tr><td>
MAKEVISIBLE</td><td>
/O</td><td>

*(无值)*</td><td>

确保第一个选定的项目在文件列表中可见。必要时会滚动列表。类似于 **SETFOCUS** 参数，除了查看器窗格不会更新以显示新选择。

*示例：`Select *.doc MAKEVISIBLE`
</td></tr><tr><td>
</td><td>
</td><td>

**立即**</td><td>

防止通常在将选定的文件滚动到视图中之前发生的短暂延迟。

*示例：`Select NEXT MAKEVISIBLE=立即`
</td></tr><tr><td>
NEXT</td><td>
/O</td><td>

*(无值)*</td><td>

选择文件列表中的下一个项目。紧跟在第一个当前选定项后面的第一个项目将被选中，所有其它项目将取消选中。
*示例:* `Select NEXT`
</td></tr><tr><td>
</td><td>
</td><td>

**mark**</td><td>

切换当前聚焦项目的选中状态，并将输入焦点移到列表中的下一个项目。这相当于在文件列表中按下 **Insert** 键。

*示例:* `Select NEXT=mark`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeselect**</td><td>

防止任何已选定项目被取消选择。

*示例:* `Select NEXT=nodeselect`
</td></tr><tr><td>
</td><td>
</td><td>

**row**</td><td>

在图标显示模式（例如缩略图模式）中，这将将选择向下移动一行（垂直而不是水平）。在详细信息和电源模式中忽略。

*示例:* `Select NEXT=row,mark`
</td></tr><tr><td>
NONE</td><td>
/S</td><td>

*(无值)*</td><td>

取消选择源文件列表中的所有项目。

*示例:* `Select NONE`
</td></tr><tr><td>
NOPATTERN</td><td>
/S</td><td>

*(无值)*</td><td>

**Select** 命令通常需要 **PATTERN** 参数的值才能操作，但在某些情况下，您可能需要在不提供模式的情况下对其进行操作。例如，**HIDESEL** 和 **HIDEUNSEL** 参数可用于隐藏当前选定的所有项目或未选定的所有项目，而无需首先应用新的通配符选择。

*示例:* `Select HIDESEL NOPATTERN`
</td></tr><tr><td>
PATTERN</td><td>
</td><td>

*\<pattern\>*</td><td>

指定通配符模式。与提供的模式匹配的所有项目都将被选择（或取消选择、隐藏等，具体取决于此命令的其它参数）。模式可以使用 [标准模式匹配](../../wildcard_reference/pattern_matching_syntax.zh.md) 语法进行指定，或者在提供了 **REGEXP** 参数的情况下使用 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md)。**PATTERN** 参数还用于与 **FILTER** 参数一起提供预定义过滤器的名称。

这是 **Select** 命令的默认参数，因此无需提供 **PATTERN** 关键字。

*示例:* `Select *.(bmp|jpg|gif) HIDEUNSEL`
</td></tr><tr><td>
PREV</td><td>
/O</td><td>

*(无值)*</td><td>

选择文件列表中的上一个项目。将选择最后一次当前选定项目之前的第一个项目，并取消选择所有其它项目。

*示例:* `Select PREV`
</td></tr><tr><td>
</td><td>
</td><td>

**mark**</td><td>

切换当前聚焦项目的选中状态，并将输入焦点移到列表中的上一个项目。类似于按下 **Insert** 键，但焦点移动到上一个项目而不是下一个项目。

*示例:* `Select PREV=mark`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeselect**</td><td>

防止任何已选定项目被取消选择。

*示例:* `Select PREV=nodeselect`
</td></tr><tr><td>
</td><td>
</td><td>

**row**</td><td>

在图标显示模式（例如缩略图模式）中，这将将选择向上移动一行（垂直而不是水平）。在详细信息和电源模式中忽略。

*示例:* `Select PREV=row,mark`
</td></tr><tr><td>
RANGE</td><td>
/K</td><td>

*\<range\>*</td><td>

根据项目在列表中的索引（它们在列表中的位置）选择一系列项目。此命令等效于 [逐步输入](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段的范围选择模式。*\<range\>* 值由一个或多个用逗号分隔的范围组成；每个范围可以是一个单个数字，也可以是由连接号分隔的两个数字，表示该范围内的所有数字。

*示例:* `Select RANGE 3,8-15,22-25,30`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(无值)*</td><td>

使用 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 模式，而不是标准模式匹配。

*示例:* `Select .*\\jpg REGEXP`
</td></tr><tr><td>
RESELECT</td><td>
/S</td><td>

*(无值)*</td><td>

重新选择上次执行的命令使用（并取消选择）的所有文件和文件夹。

*示例:* `Select RESELECT`
</td></tr><tr><td>
SETFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

确保第一个选定的项目在文件列表中可见。如果需要，列表将滚动。此外，如果查看器窗格已打开，则第一个选定的文件将自动查看，如果可能的话。

*示例:* `Select *.jpg SETFOCUS`
</td></tr><tr><td>
SHOWFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

如果需要，滚动文件列表以使当前聚焦项目可见。选择不会被修改。

*示例:* `Select SHOWFOCUS`
</td></tr><tr><td>
SHOWHIDDEN</td><td>
/O</td><td>

*(无值)*</td><td>

显示以前通过使用 **HIDESEL** 或 **HIDEUNSEL** 参数的命令而隐藏的任何文件或文件夹。显示这样隐藏的文件的另一种方法是重新读取文件夹（例如，按 **F5**）。

*示例:* `Select NOPATTERN SHOWHIDDEN`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

显示所有隐藏的目录。

*示例:* `Select SHOWHIDDEN=dirs NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

显示所有隐藏的文件。

*示例:* `Select SHOWHIDDEN=files NOPATTERN`
</td></tr><tr><td>
SHOWUNAFFECTED</td><td>
/S</td><td>

*(无值)*</td><td>

与 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 工具配合使用时，这将显示以前隐藏的任何项目，因为它们未标记为同步（复制或删除）。

*示例:* `Select SHOWUNAFFECTED`
</td></tr><tr><td>
SIMILAR</td><td>
/S</td><td>

*(无值)*</td><td>

选择具有与当前选定文件相同文件扩展名的所有文件。例如，如果当前选定了单个 **.jpg** 文件和单个 **.gif** 文件，此命令将在源文件列表中Select *所有* **.jpg** 文件和 **.gif** 文件。

*示例:* `Select SIMILAR`
</td></tr><tr><td>
</td><td>
</td><td>

**trueext**</td><td>

导致命令忽略多部分扩展名。例如 **file.part1.rar**、**file.part2.rar** 和 **file.part3.rar** 都将被视为 **.rar** 文件，而不是具有不同的扩展名。

*示例:* `Select SIMILAR=trueext`
</td></tr><tr><td>
SIMILARBASE</td><td>
/S</td><td>

*(无值)*</td><td>

选择具有与当前选定文件相同基础名称的所有文件。例如，如果当前选定了 **cat.jpg** 和 **dog.gif**，此命令将在源文件列表中Select *所有* **cat.**\* 和 **dog.**\* 文件。

*示例:* `Select SIMILARBASE`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*(无值)*</td><td>

在 [简单](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md) 模式中显示 *Select* 对话框。

*示例:* `Select SIMPLE`
</td></tr><tr><td>
SIZE</td><td>
/K</td><td>

*\<size\>*</td><td>

选择大小与指定大小匹配的文件。默认情况下，指定的大小将被视为字节，但可以使用以下后缀来使用不同的单位：

- **kb** - 千字节
- **mb** - 兆字节
- **gb** - 千兆字节您还可以在大小前使用 **\>**（大于）来匹配所有大于指定大小的文件，或使用 **\<**（小于）来匹配所有小于指定大小的文件。
*示例:* `Select *.png SIZE >2mb`
</td></tr><tr><td>
</td><td>
</td><td>

*\<size1\>***..***\<size2\>*</td><td>

选择其大小介于两个指定大小之间的文件。两种大小都以上述格式提供。

*示例:* `Select SIZE 500kb..5mb DESELECTNOMATCH`
</td></tr><tr><td>
</td><td>
</td><td>

**largest**</td><td>

选择当前来源文件列表中最大的项。您可以将其与 **PATTERN** 参数结合使用以选择特定类型文件中最大的一个。

*示例:* `Select *.doc SIZE=largest`
</td></tr><tr><td>
</td><td>
</td><td>

**smallest**</td><td>

选择当前文件的显示中最小的项。

*示例:* `Select SIZE=smallest`
</td></tr><tr><td>
SOURCETODEST</td><td>
/O</td><td>

*(无值)*</td><td>

选择当前在来源中选择的、目标文件列表中的所有文件与文件夹。仅对文件名进行比较 - 实际上不会比较文件。

*示例:* `Select SOURCETODEST`
</td></tr><tr><td>
</td><td>
</td><td>

**in**</td><td>

选择目标文件列表中存在于来源中的所有文件与文件夹。

*示例:* `Select SOURCETODEST=in`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

比较来源与目标中的选择文件时，不考虑文件扩展名。例如，如果 **IMGP1234.JPG** 在来源中选中，且 **IMGP1234.WAV** 存在于目标中，则它会被选中。

*示例:* `Select SOURCETODEST=noext`
</td></tr><tr><td>
</td><td>
</td><td>

**notin**</td><td>

选择目标文件列表中不存在于来源中的所有文件与文件夹。

*示例:* `Select SOURCETODEST=notin`
</td></tr><tr><td>
THIS</td><td>
/S</td><td>

*(无值)*</td><td>

选择当前焦点项。拥有输入焦点的项有可能未被选中（例如，如果您使用 **Ctrl + 光标向下** 移动焦点高亮显示），而此命令将选择当前获得焦点的任何项。

*示例:* `Select THIS`
</td></tr><tr><td>
TOCHECKS</td><td>
/S</td><td>

*(无值)*</td><td>

将项选择状态转换为选择状态。选中项将被勾选，而未选中项将被取消勾选。如果文件列表当前不在[复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)下，则将自动启用它。

*示例:* `Select TOCHECKS`
</td></tr><tr><td>
TYPE</td><td>
/K</td><td>

**files**</td><td>

强制选择仅影响文件 - 即使文件夹与模式匹配，它们也不会受到影响。

您可以添加 **DESELECTOTHERTYPE** 参数以取消选择所有“其它”类型项。

*示例:* `Select a\* TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

强制选择仅影响文件夹。

*示例:* `Select "new *" TYPE=dirs`
</td></tr></tbody>
</table>