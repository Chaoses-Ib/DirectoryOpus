<table>
<thead><tr><th>
属性名</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*String*</td><td>
返回 item 的完整路径名（例如路径加上文件名）。
</td></tr><tr><td>
access</td><td>

*日期*</td><td>
返回“上次访问”日期（本地时间）。
</td></tr><tr><td>
access_utc</td><td>

*日期*</td><td>
返回“上次访问”日期（UTC）。
</td></tr><tr><td>
attr</td><td>

*int*</td><td>

返回 item 属性。此值为逻辑或运算在一起的一系列标记。Opus 支持的属性包括：

|        |                                 |
|--------|---------------------------------|
| 1      | 只读                       |
| 2      | 隐藏                          |
| 4      | 系统                          |
| 32     | 压缩包                         |
| 1024   | 重新分析点（链接等） |
| 2048   | 已压缩                      |
| 4096   | 离线存储                 |
| 8192   | 未进行内容索引             |
| 16384  | 已加密                       |
| 524288 | 已固定                          |

使用返回 **[FileAttr](fileattr.zh.md)** 对象的 **fileattr** 属性可能比处理原始属性标记更容易。
</td></tr><tr><td>
attr_text</td><td>

*String*</td><td>
返回文件列表中显示的 item 属性，为字符串形式。
</td></tr><tr><td>
checked</td><td>

*Boolean*</td><td>

如果选中 item（在 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) 中），则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
create</td><td>

*日期*</td><td>
返回“创建”日期（本地时间）。
</td></tr><tr><td>
create_utc</td><td>

*日期*</td><td>
返回“创建”日期（UTC）。
</td></tr><tr><td>
current</td><td>

*Boolean*</td><td>

对于从 **[Viewer](viewer.zh.md)** 中获取的 **Item** 对象，如果 item 表示当前显示图像，则此属性为 **True**，否则为 **False**。

对于从文件列表中获取的 **Item** 对象，此属性指示该 item 是否具有焦点。**focus** 属性是检查此项更为正式的方法，但是在忘记哪个属性是哪个属性的情况下，这两个属性都可以正常工作。
</td></tr><tr><td>
display_name</td><td>

*String*</td><td>

返回 item 的显示名称。只有少数 item 的显示名称与其实际名称不同 - 一些示例是某些系统文件夹（如 *C:\Users*，在非英语语言环境中可能有翻译的显示名称）。
</td></tr><tr><td>
ext</td><td>

*String*</td><td>
返回文件名扩展名。
</td></tr><tr><td>
ext_m</td><td>

*String*</td><td>

返回文件名扩展名，并考虑多部分扩展名。 例如，名为“file.part1.rar”的文件对于 **ext** 可能会返回“.rar”，而对于 **ext_m** 可能会返回“.part1.rar”。
</td></tr><tr><td>
failed</td><td>

*Boolean*</td><td>

如果 item 在命令中使用时失败，则返回 **True**。这仅与 **[Command](command.zh.md).files** 集合一起使用才有意义 - 一旦命令返回，此属性将基于每个文件指示成功或失败。
</td></tr><tr><td>
fileattr</td><td>

*Object:***[FileAttr](fileattr.zh.md)**</td><td>

返回表示 item 属性的 **[FileAttr](fileattr.zh.md)** 对象。
</td></tr><tr><td>
filegroup</td><td>

*Object:***[FileGroup](filegroup.zh.md)**</td><td>

如果此 item 所属的文件列表按特定列分组，则此属性将返回表示该 item 所在分组的 **[FileGroup](filegroup.zh.md)** 对象。如果该 item 没有所属分组，则此属性将返回空字符串。

此属性关系到按其列之一对文件列表进行分组。如果你正在寻找 *文件类型分组*，请参见下文中的 **groups** 和 **groupsobject** 属性。
</td></tr><tr><td>
focus</td><td>

*Boolean*</td><td>

对于从文件列表中获取的 **Item** 对象，如果对象表示具有焦点的 item，则此属性为 **True**，否则为 **False**。一次只能有一个 item 具有焦点。具有焦点的 item 通常在其周围显示边框，并且通常是最近点击的 item 或使用键盘移至的 item。具有焦点的 item 通常也是所选 item 之一，但不总是如此；选择和焦点是两个独立的事物。

对于从 **[Viewer](viewer.zh.md)** 中获取的 **Item** 对象，此属性指示该文件是否为 viewer 中当前显示的文件。**current** 属性是测试此项更为正式的方法，但 **focus** 也适用于此项。
</td></tr><tr><td>
got_size</td><td>

*Boolean*</td><td>

如果文件夹 item 的大小已由例如 **[GetSizes](../../command_reference/internal_commands/getsizes.zh.md)** 命令计算，则返回 **True**。如果为 **False**，则 **size** 属性对于文件夹不可靠。
</td></tr><tr><td>
groups</td><td>

**[Vector](vector.zh.md)**:**[FiletypeGroup](filetypegroup.zh.md)**</td><td>

返回 **[FiletypeGroup](filetypegroup.zh.md)** 对象的 **[Vector](vector.zh.md)**，表示该文件属于其中的所有文件类型分组。

如果你只想检查特定文件类型分组的所属关系，请参见以下部分中的 **InGroup** 方法。

如果你正在查找有关文件列表如何基于其中显示的列之一对该文件进行分组的信息，请参见上文中的 **filegroup** 属性。
</td></tr><tr><td>
groupsobject</td><td>

*object:***[FiletypeGroups](filetypegroups.zh.md)**</td><td>

与 groups 属性类似，但返回 **[FiletypeGroups](filetypegroups.zh.md)** 对象，不返回 **[Vector](vector.zh.md)**。
</td></tr><tr><td>
highlighted</td><td>

*object:***[HighlightedColumns](highlightedcolumns.zh.md)**</td><td>

返回一个 **[HighlightedColumns](highlightedcolumns.zh.md)** 对象，用于枚举属于此 item 的任何 [选定单元格](/Manual/basic_concepts/selecting_files/selecting_cells.zh.md)。

此项仅当从 **[Tab](tab.zh.md)** 中检索该 item 时适用于此项。通常，你可以在从 **复制突出显示单元格** 上下文菜单中运行的脚本中使用该项。
</td></tr><tr><td>
id</td><td>

*int*</td><td>
这是该 item 的唯一 ID；它是 Opus 内部使用的。
</td></tr><tr><td>
is_dir</td><td>

*Boolean*</td><td>

如果 item 表示文件夹，则返回 **True**，如果表示文件，则返回 **False**。
</td></tr><tr><td>
is_junction</td><td>

*Boolean*</td><td>

如果 item 是另一个文件夹的链接，则返回 **True**。
</td></tr><tr><td>
is_reparse</td><td>

*Boolean*</td><td>

如果 item 是重新分析点，则返回 **True**。
<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
InGroup</td><td>

\<string:组\></td><td>

*bool*</td><td>

测试文件是否属于指定的文件类型组。

每个文件类型组都有两个名称：一个内部名称，它在所有语言中始终相同，以及一个显示名称，它可能在每种语言中翻译成不同的名称。显示名称是你在文件类型编辑器中看到的内容。当你安装 Opus 时预先定义的组具有内部名称，如 *"Archives"* 和 *"Music"*（它们也是它们的英文显示名称）。用户定义的组具有内部名称，它们是唯一的、自动生成的 GUID 字符串，如 *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*。

*组* 参数应该是你要进行测试的组的名称，例如 *"Music"。

默认情况下，内部名称和显示名称都经过检查，任何一个的匹配都会返回 true。用 *"name:"* 为 *组* 参数添加前缀以将搜索限制为内部名称，或用 *"disp:"* 将搜索限制为显示名称。

要获取文件匹配的所有文件类型组列表，请改为使用 **groups** 属性（请参阅上面的部分）。
</td></tr><tr><td>
Labels</td><td>

\<string:类别\>  
\<string:标志\></td><td>

**[Vector](vector.zh.md)**:*string*</td><td>

此方法返回一个 **[Vector](vector.zh.md)** 的字符串，表示已分配给该项的任何 [标签](/Manual/file_operations/labels.zh.md)。

两个参数都是可选的。第一个是一个 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)，它允许你基于标签的类别过滤返回的标签。例如，传递 *"Status"* 仅检索分配给文件的状态图标列表。

第二个可选参数包含控制如何返回标签的标志关键字。唯一定义的标志是 *"explicit"* - 如果指定，将不考虑通配符和标签过滤器 - 只会返回显式分配的标签。请注意，如果你想提供第二个参数但不想按类别过滤，你应该为第一个参数传递 *"\*"* 以匹配所有类别。

如果不请求显式标签，将返回任何全局通配符/过滤器标签，以及为该项的文件夹配置的任何每个文件夹的标签。但是，此函数当前不返回每个文件夹的 *内容类型* 和 *文件夹类型* 标签。
</td></tr><tr><td>
MatchFilter</td><td>

\<object:filter\>  
或 \<string:filter\></td><td>

*bool*</td><td>

如果项与指定的过滤器匹配，则返回 **True**。*filter* 参数必须是 **[Filter](filter.zh.md)** 对象，由 **[DOpusFactory](dopusfactory.zh.md).NewFilter** 方法创建。

你还可以以字符串形式传递 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md)，以一次操作解析过滤器并比较项，但如果你要比较多个项，则会创建 **Filter** 的效率会更高。
</td></tr><tr><td>
Open</td><td>

\<string:模式\>  
\<object:窗口\></td><td>

*object:***[File](file.zh.md)**</td><td>

打开此文件并返回一个 **[File](file.zh.md)** 对象，该对象允许你访问其内容作为二进制数据。

默认情况下，文件将在 *读取模式* 中打开 - 指定可选的 *mode* 参数为 *"w"* 以在 *写入模式* 中打开文件。请注意，你不能使用同一个 **File** 对象同时读取和写入。

在写入模式下打开时，你还可以指定控制如何打开文件的可选标志：

<pre>

|     |                                                                                                                            |
|-----|----------------------------------------------------------------------------------------------------------------------------|
| wc  | 仅在文件不存在时创建一个新文件。                                                                                       |
| wa  | 创建一个新文件，始终。如果文件已存在，它将被覆盖。（这是默认设置。）                                                 |
| we  | 打开现有文件。如果文件不存在，则不会创建该文件。                                                                            |
| wo  | 打开现有文件。如果文件不存在，它将被创建。                                                                                |
| wt  | 截断现有文件。如果文件存在，它将被截断。如果文件不存在，则不会创建该文件。                              |
| d   | 关闭时删除。                                                                                                                 |

</pre>

在使用写入模式时，你可以在上面任何一个模式字符串后添加 *f*（强制），来告诉 Opus 在修改现有文件时如果只读文件属性阻止了它，则清除该属性；否则，尝试以写入权限打开只读文件将失败。例如，*"wof"* 就如同 *"wo"* 模式，但也会清除只读属性。
如果只想修改文件的属性而无需修改其数据，还可以指定“*m*”以在“*修改模式*”下打开文件。

可选的“*窗口*”参数允许你将**文件**对象与 **[标签](tab.zh.md)** 或 **[列表](lister.zh.md)** 关联起来，如果 Opus 需要显示任何对话框（例如 UAC 提升对话框），将使用这些标签或列表。你还可以指定字符串“NoElevate”以完全阻止 UAC 提升，或者指定“ElevateNoAsk”以阻止 UAC 提示，同时在已经执行过提升操作的其他情况下仍然获得提升。

**文件** 对象始终会被返回，即使无法打开文件。在创建它之后立即检查返回的对象上的 **File.error** 以查看是否成功打开文件。即使文件无法打开，该对象的一些方法仍然可能起作用。例如，如果文件不存在，那么你无法打开它或设置它的属性，但是对于存在的文件，权限可能允许你设置其属性，同时阻止你修改它，反之亦然。
</td></tr><tr><td>
ShellProp</td><td>

\<string:property\>  
\<string:type\></td><td>

*variant*</td><td>

返回项目指定 shell 属性的值。该属性参数可以是属性的 PKEY 或其名称。

如果你提供名称，则可选的第二个参数允许你控制按名称查找属性的方式。如果 *type* 的值为“R”，则将使用原始名称与所提供名称匹配的第一个属性。如果值为“D”，则将使用显示名称与所提供名称匹配的第一个属性。如果省略 *type*，则原始名称和显示名称都可以匹配。

请注意，如果 shell 属性由系统以 SAFEARRAY 类型返回，它将自动转换为 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

从磁盘上的文件更新 **项目** 对象。如果你已经运行某个命令来更改项目的 time stamp 或属性，并且想要检索新信息，可以使用它。
</td></tr></tbody>
</table>