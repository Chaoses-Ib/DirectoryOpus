# Item

**Item** 对象表示在标签中显示的文件或文件夹。您可以从 **[Tab](tab.zh.md)** 对象的各种方法中获取 **Item** 对象的集合。**Item** 对象的集合还与 **[Command](command.zh.md)** 对象一起使用，以指定命令应操作的文件或文件夹。使用 **[FSUtil](fsutil.zh.md).ReadDir** 方法枚举文件夹的内容也会返回 **Item** 对象。您可以使用 **[FSUtil](fsutil.zh.md).GetItem** 方法从文件路径创建 **Item**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回项目的完整路径名（即路径加文件名）。
</td></tr><tr><td>
access</td><td>

*date*</td><td>
返回本地时间的“上次访问”日期。
</td></tr><tr><td>
access_utc</td><td>

*date*</td><td>
返回 UTC 的“上次访问”日期。
</td></tr><tr><td>
attr</td><td>

*int*</td><td>

返回项目属性。此值是一系列逻辑上 OR 组合在一起的标志。Opus 支持的属性是：

|        |                                 |
|--------|---------------------------------|
| 1      | 只读                       |
| 2      | 隐藏                          |
| 4      | 系统                          |
| 32     | 压缩包                         |
| 1024   | 重解析点（联接等） |
| 2048   | 压缩                      |
| 4096   | 脱机存储                 |
| 8192   | 未被内容索引             |
| 16384  | 加密                       |
| 524288 | 固定                          |

使用 **fileattr** 属性（返回一个 **[FileAttr](fileattr.zh.md)** 对象）可能比处理原始属性标志更容易。
</td></tr><tr><td>
attr_text</td><td>

*string*</td><td>
返回以字符串形式表示的项目属性，如文件列表中所示。
</td></tr><tr><td>
checked</td><td>

*bool*</td><td>

如果项目已选中（在 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) 中），则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
create</td><td>

*date*</td><td>
返回本地时间的“创建”日期。
</td></tr><tr><td>
create_utc</td><td>

*date*</td><td>
返回 UTC 的“创建”日期。
</td></tr><tr><td>
current</td><td>

*bool*</td><td>

对于从 **[Viewer](viewer.zh.md)** 获取的 **Item** 对象，如果项目表示当前显示的图像，则此属性为 **True**，否则为 **False**。

对于从文件列表获取的 **Item** 对象，该属性指示该项目是否为具有焦点的项目。**focus** 属性是检查此项的更合适方法，但如果忘记哪一个是哪一个，则两者都可以使用。
</td></tr><tr><td>
display_name</td><td>

*string*</td><td>

返回项目的显示名称。只有少数项目的显示名称与其实际名称不同 - 例如，某些系统文件夹（如 *C:\Users*，其在非英语区域设置中可能具有翻译后的显示名称）。
</td></tr><tr><td>
ext</td><td>

*string*</td><td>
返回文件名扩展名。
</td></tr><tr><td>
ext_m</td><td>

*string*</td><td>

返回文件名扩展名，同时考虑多部分扩展名。 例如，名为“file.part1.rar”的文件可能会为 **ext** 返回“.rar”，但为 **ext_m** 返回“.part1.rar”。
</td></tr><tr><td>
failed</td><td>

*bool*</td><td>

如果项目在命令使用时失败，则返回 **True**。这只有在与 **[Command](command.zh.md).files** 集合结合使用时才有意义 - 命令返回后，此属性将指示每个文件的成功或失败。
</td></tr><tr><td>
fileattr</td><td>

*object:***[FileAttr](fileattr.zh.md)**</td><td>

返回一个 **[FileAttr](fileattr.zh.md)** 对象，该对象表示项目的属性。
</td></tr><tr><td>
filegroup</td><td>

*object:***[FileGroup](filegroup.zh.md)**</td><td>

如果此项目来自的文件夹显示按特定列分组，则此属性返回一个 **[FileGroup](filegroup.zh.md)** 对象，表示该项目所属的组。如果项目没有组，这将返回一个空字符串。

此属性是关于按其中一列对文件夹显示进行分组。如果您正在寻找 *文件类型组*，请参见下面的 **groups** 和 **groupsobject** 属性。
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

对于从文件列表获取的 **Item** 对象，如果该对象表示具有焦点的项目，则此属性为 **True**，否则为 **False**。一次只能有一个项目具有焦点。具有焦点的项目通常会在其周围显示一个轮廓，通常是最近被点击的项目，或者是用键盘移动到的项目。具有焦点的项目通常也是选定项目之一，但并非总是如此；选择和焦点是两件不同的事情。

对于从 **[Viewer](viewer.zh.md)** 获取的 **Item** 对象，该属性指示文件是否为当前在查看器中显示的文件。**current** 属性是测试此项的更合适方法，但 **focus** 也适用。
</td></tr><tr><td>
got_size</td><td>

*bool*</td><td>

如果文件夹项目的尺寸已计算出来，例如，通过 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 命令，则返回 **True**。如果为 **False**，则 **size** 属性对于文件夹将不可靠。
</td></tr><tr><td>
groups</td><td>

**[Vector](vector.zh.md)**:**[FiletypeGroup](filetypegroup.zh.md)**</td><td>

返回一个 **[Vector](vector.zh.md)** 的 **[FiletypeGroup](filetypegroup.zh.md)** 对象，表示该文件所属的任何和所有文件类型组。

如果您只想检查特定文件类型组的成员资格，请参见下面部分中的 **InGroup** 方法。

如果您正在寻找有关文件夹显示如何根据其中一列显示对该文件进行分组的信息，请参见上面的 **filegroup** 属性。
</td></tr><tr><td>
groupsobject</td><td>

*object:***[FiletypeGroups](filetypegroups.zh.md)**</td><td>

类似于 groups 属性，除了返回 **[FiletypeGroups](filetypegroups.zh.md)** 对象而不是 **[Vector](vector.zh.md)**。
</td></tr><tr><td>
highlighted</td><td>

*object:***[HighlightedColumns](highlightedcolumns.zh.md)**</td><td>

返回一个 **[HighlightedColumns](highlightedcolumns.zh.md)** 对象，使您可以枚举属于该项目的任何 [选定单元格](/Manual/basic_concepts/selecting_files/selecting_cells.zh.md)。

这仅适用于从 **[Tab](tab.zh.md)** 获取的项目。通常，您将在从 **复制突出显示的单元格** 上下文菜单运行的脚本中使用此项。
</td></tr><tr><td>
id</td><td>

*int*</td><td>
这是项目的唯一 ID；它在 Opus 内部使用。
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

如果项目代表一个文件夹，则返回 **True**，对于文件则返回 **False**。
</td></tr><tr><td>
is_junction</td><td>

*bool*</td><td>

如果项目是到另一个文件夹的联接，则返回 **True**。
</td></tr><tr><td>
is_reparse</td><td>

*bool*</td><td>

如果项目是重解析点，则返回 **True**。
</td></tr><tr><td>
is_symlink</td><td>

*bool*</td><td>

如果项目是符号链接，则返回 **True**。
</td></tr><tr><td>
metadata</td><td>

*object:***[Metadata](metadata.zh.md)**</td><td>

返回一个 **[Metadata](metadata.zh.md)** 对象，该对象提供对项目元数据的访问。
</td></tr><tr><td>
modify</td><td>

*date*</td><td>
返回本地时间的“上次修改”日期。
</td></tr><tr><td>
modify_utc</td><td>

*date*</td><td>
返回 UTC 的“上次修改”日期。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回项目的名称。
</td></tr><tr><td>
name_stem</td><td>

*string*</td><td>

返回项目的“stem”。这是在删除文件名扩展名后项目的名称。对于文件夹，它将与 **name** 相同。
</td></tr><tr><td>
name_stem_m</td><td>

*string*</td><td>

返回项目的“stem”，同时考虑多部分扩展名。 例如，名为“file.part1.rar”的文件可能会为 **name_stem** 返回“file.part1”，但为 **name_stem_m** 返回“file”。
</td></tr><tr><td>
nested</td><td>

*bool*</td><td>

如果项目位于展开的子文件夹中，则返回 **True**，如果它位于文件夹的根目录中，则返回 **False**。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回项目父文件夹的路径。这不包括项目本身的名称，可以通过 **name** 属性获取。
</td></tr><tr><td>
realpath</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回项目的“真实”路径。对于位于 [虚拟文件夹](/Manual/preferences/preferences_categories/folders/virtual_folders/README.zh.md)（如 [Libraries](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 或 [Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)）中的项目，这使您可以访问真实文件系统中的项目的底层路径。**realpath** 属性包括项目的完整路径，包括它自己的名称。
</td></tr><tr><td>
selected</td><td>

*bool*</td><td>

如果项目被选中，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
shortpath</td><td>

*object:***[Path](path.zh.md)**</td><td>
返回项目的短路径（如果有）。请注意，短路径在 Windows 10 中默认情况下已禁用。
</td></tr><tr><td>
size</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回项目的尺寸，作为一个 **[FileSize](filesize.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
InGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

测试文件是否属于指定的文件类型组。

每个文件类型组都有两个名称：一个始终在所有语言中都相同的内部名称，以及一个可能在每种语言中都翻译不同的显示名称。显示名称是在文件类型编辑器中看到的。安装 Opus 时预定义的组具有内部名称，例如 *"Archives"* 和 *"Music"*（它们也是其英文显示名称）。用户定义的组具有唯一的内部名称，自动生成的 GUID 字符串，例如 *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*。

*group* 参数应该是您要测试的组的名称，例如 *"Music"*。

默认情况下，将检查内部名称和显示名称，如果两者匹配，则返回 true。在 *group* 参数前面添加 *"name:"* 以将搜索限制为内部名称，或使用 *"disp:"* 将搜索限制为显示名称。

要获取与该文件匹配的所有文件类型组的列表，请使用 **groups** 属性（参见上面的部分）。
</td></tr><tr><td>
Labels</td><td>

\<string:category\>  
\<string:flags\></td><td>

**[Vector](vector.zh.md)**:*string*</td><td>

此方法返回一个 **[Vector](vector.zh.md)** 的字符串，表示已分配给该项目的任何 [标签](/Manual/file_operations/labels.zh.md)。

两个参数都是可选的。第一个是 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)，它允许您根据其类别过滤返回的标签。例如，传递 *"Status"* 仅检索分配给文件的状态图标列表。

第二个可选参数包含控制如何返回标签的标志关键字。唯一定义的标志是 *"explicit"* - 如果指定，则通配符和标签过滤器将不予考虑 - 仅返回显式分配的标签。请注意，如果您想提供第二个参数但不想按类别过滤，则应该为第一个参数传递 *"\*"* 以匹配所有类别。

如果没有请求显式标签，则将返回任何全局通配符/过滤器标签，以及为该项目的文件夹配置的任何每个文件夹标签。但是，此函数目前不返回每个文件夹的 *内容类型* 和 *文件夹类型* 标签。
</td></tr><tr><td>
MatchFilter</td><td>

\<object:filter\>  
or \<string:filter\></td><td>

*bool*</td><td>

如果项目匹配指定的过滤器，则返回 **True**。*filter* 参数必须是通过 **[DOpusFactory](dopusfactory.zh.md).NewFilter** 方法创建的 **[Filter](filter.zh.md)** 对象。

您还可以以字符串形式传递 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md)，以解析过滤器并在一个操作中比较项目，尽管如果您比较多个项目，创建 **Filter** 会更高效得多。
</td></tr><tr><td>
Open</td><td>

\<string:mode\>  
\<object:window\></td><td>

*object:***[File](file.zh.md)**</td><td>

打开此文件并返回一个 **[File](file.zh.md)** 对象，使您可以以二进制数据的形式访问其内容。

默认情况下，该文件将以 *读取模式* 打开 - 指定 *"w"* 作为可选的 *mode* 参数以 *写入模式* 打开该文件。请注意，您不能使用同一个 **File** 对象进行读写。

以写入模式打开时，您还可以指定控制文件打开方式的可选标志：

|     |                                                                                                                            |
|-----|----------------------------------------------------------------------------------------------------------------------------|
| wc  | 仅当文件尚不存在时才创建新文件。                                                                       |
| wa  | 始终创建新文件。如果文件已存在，则将覆盖该文件。（这是默认设置。）                       |
| we  | 打开现有文件。如果文件不存在，则不会创建该文件。                                              |
| wo  | 打开现有文件。如果文件不存在，则将创建该文件。                                                          |
| wt  | 截断现有文件。如果文件存在，则将截断该文件。如果文件不存在，则不会创建该文件。 |
| d   | 关闭时删除。                                                                                                           |

使用写入模式时，您可以将 *f*（强制）添加到任何上述模式字符串中，以告诉 Opus 在阻止修改现有文件时清除只读文件属性；否则，尝试以写入模式打开只读文件将失败。例如，*"wof"* 类似于 *"wo"* 模式，但也会清除只读属性。

如果您只想对文件的属性进行更改而不对其数据进行修改，您也可以指定 *"m"* 以 *修改模式* 打开它。

可选的 *window* 参数使您可以将 **File** 对象与 **[Tab](tab.zh.md)** 或 **[文件窗口](lister.zh.md)** 关联起来，如果 Opus 需要显示任何对话框（例如 UAC 提升对话框），则将使用这些对话框。您也可以指定字符串 *"NoElevate"* 以完全阻止 UAC 提升，或者指定 "ElevateNoAsk" 以防止 UAC 提示，同时如果其它操作已执行提升，则仍会获得提升。

即使无法打开文件，也会始终返回 **File** 对象。在创建返回的对象后立即检查 **File.error**，以查看是否成功打开文件。即使文件没有被打开，某些对象方法可能仍然可以使用。例如，如果文件不存在，则您无法打开它或设置其属性，但现有文件的权限可能允许您设置其属性，而阻止您修改它，反之亦然。
</td></tr><tr><td>
ShellProp</td><td>

\<string:property\>  
\<string:type\></td><td>

*variant*</td><td>

返回项目的指定 shell 属性的值。属性参数可以是属性的 PKEY 或其名称。

如果您提供一个名称，则可选的第二个参数允许您控制如何按名称查找属性。如果 *type* 的值为 "R"，则将使用第一个其原始名称与提供的名称匹配的属性。如果该值是 "D"，则将使用第一个其显示名称与提供的名称匹配的属性。如果省略 *type*，则原始名称和显示名称都可以匹配。

请注意，如果系统以 SAFEARRAY 类型返回 shell 属性，它将自动转换为 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

从磁盘上的文件更新 **Item** 对象。如果您运行过命令来更改项目的日期戳或属性，并且想要检索新信息，则可以使用此命令。
</td></tr></tbody>
</table>