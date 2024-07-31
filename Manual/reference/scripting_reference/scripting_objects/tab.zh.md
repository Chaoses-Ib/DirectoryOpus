# Tab

**Tab** 对象表示文件窗口中的文件夹标签页（即使标签页控件当前未显示，文件窗口始终至少有一个打开的标签页）。您可以从 **[文件窗口](lister.zh.md)** 对象中获取 **Tab** 对象的集合。**Tab** 对象也与 **[Command](command.zh.md)** 和 **[Func](func.zh.md)** 对象一起使用，如果命令导致打开新的标签页，则还会与 **[Results](results.zh.md)** 对象一起使用。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
all</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有文件和文件夹。

注意：脚本第一次访问此属性（以及所有返回 **[Items](items.zh.md)** 对象的其它属性）时，会对所有相关项目进行快照。如果脚本随后对这些项目进行了更改（例如，通过创建新文件、修改选择等），这些更改将不会反映在集合中。要重新同步集合，请在对象上调用 **Update** 方法。
</td></tr><tr><td>
backlist</td><td>

*collection:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象的集合，表示此标签页的“向后”历史记录列表中的路径（即，通过单击“后退”按钮可以访问的文件夹）。
</td></tr><tr><td>
color</td><td>

*string*</td><td>

返回分配给标签页的颜色（如果已分配，例如通过 **Go TABCOLOR** 命令）。颜色以 R、G、B 格式的字符串形式返回。
</td></tr><tr><td>
crumbpath</td><td>

*object:***[Path](path.zh.md)**</td><td>
返回标签页面包屑控件（如果有）中的当前路径，包括任何幽灵路径。
</td></tr><tr><td>
dest</td><td>

*bool*</td><td>

如果此标签页当前为 [目标](/Manual/basic_concepts/source_and_destination.zh.md)，则返回 **True**，否则返回 **False**。

请注意，您不能总是假设标签页是源，即使它不是目标。请使用单独的 **source** 属性来确定这一点。
</td></tr><tr><td>
dirs</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有文件夹。
</td></tr><tr><td>
dirty</td><td>

*bool*</td><td>

如果标签页被标记为脏，则返回 **True**，表示其内容列表可能已过期。如果标签页处于后台，并且用户已关闭 **配置 / 文件夹标签页 / 选项 / 在后台标签页中处理文件更改** 选项，则可能会发生这种情况。
</td></tr><tr><td>
displayed_label</td><td>

*string*</td><td>
返回此标签页的当前显示标签。
</td></tr><tr><td>
filegroups</td><td>

*collection:***[FileGroup](filegroup.zh.md)**</td><td>

返回一个 **[FileGroup](filegroup.zh.md)** 对象的集合，表示标签页中的所有文件组（当标签页被分组时）。您可以使用 **format.group_by** 属性来测试标签页是否已分组。
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有文件。
</td></tr><tr><td>
format</td><td>

*object:***[Format](format.zh.md)**</td><td>

返回一个 **[Format](format.zh.md)** 对象，表示此标签页中的当前文件夹格式。
</td></tr><tr><td>
forwardlist</td><td>

*collection:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象的集合，表示此标签页的“向前”历史记录列表中的路径（即，通过单击“向前”按钮可以访问的文件夹）。
</td></tr><tr><td>
hidden</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前隐藏的所有文件和文件夹。
</td></tr><tr><td>
hidden_dirs</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前隐藏的所有文件夹。
</td></tr><tr><td>
hidden_files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前隐藏的所有文件。
</td></tr><tr><td>
highlighted</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有文件和文件夹，这些文件和文件夹的一个或多个单元格已 [突出显示](/Manual/basic_concepts/selecting_files/selecting_cells.zh.md)。
</td></tr><tr><td>
label</td><td>

*string*</td><td>

返回当前分配的标签页标签。请注意，如果未分配自定义标签，则此值可能为空字符串。**displayed_label** 属性在所有情况下都返回当前显示的标签。
</td></tr><tr><td>
linktab</td><td>

*object:***Tab**</td><td>

如果此标签页链接到另一个标签页，则返回表示链接标签页的 **Tab** 对象。如果此标签页未链接，则此属性返回 **0**。
</td></tr><tr><td>
lister</td><td>

*object:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示拥有此标签页的父文件窗口。
</td></tr><tr><td>
lock</td><td>

*string*</td><td>
返回标签页的当前锁定状态；“off”、“on”、“changes”、“reuse”之一。
</td></tr><tr><td>
navlock</td><td>

*bool*</td><td>

如果此标签页在导航锁定模式下链接，则返回 **True**。如果标签页未链接，则此属性不存在，因此请确保首先检查 **linktab** 的值。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>
返回此标签页中显示的当前路径。
</td></tr><tr><td>
quickfilter</td><td>

*object:***[QuickFilter](quickfilter.zh.md)**</td><td>

返回一个 **[QuickFilter](quickfilter.zh.md)** 对象，提供有关此标签页中快速过滤器的状态的信息。
</td></tr><tr><td>
right</td><td>

*bool*</td><td>

如果此标签页当前位于双栏文件窗口的右侧或底部，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
selected</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有已选文件和文件夹。请注意，如果在此标签页中启用了 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，则它将是一个已选中项目的集合，而不是已选项目的集合。
</td></tr><tr><td>
selected_dirs</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有已选文件夹。
</td></tr><tr><td>
selected_files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此标签页中当前显示的所有已选文件。
</td></tr><tr><td>
selstats</td><td>

*object:***[TabStats](tabstats.zh.md)**</td><td>

返回一个 **[TabStats](tabstats.zh.md)** 对象，提供有关标签页的各种信息，包括文件数、已选文件数、已选文件的总大小等。“已选”计数由此对象提供，并考虑了 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)（也就是说，如果当前启用了复选框模式，则计数将针对已选中文件，而不是已选文件）。
</td></tr><tr><td>
source</td><td>

*bool*</td><td>

如果此标签页当前为 [源](/Manual/basic_concepts/source_and_destination.zh.md)，则返回 **True**，否则返回 **False**。

请注意，您不能总是假设标签页是目标，即使它不是源。请使用单独的 **dest** 属性来确定这一点。
</td></tr><tr><td>
stats</td><td>

*object:***[TabStats](tabstats.zh.md)**</td><td>

返回一个 **[TabStats](tabstats.zh.md)** 对象，提供有关标签页的各种信息，包括文件数、已选文件数、已选文件的总大小等。与 **selstats** 不同，此对象不考虑 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)（因此，“已选”计数将引用已选文件，而不是已选中文件）。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

此 **[Vars](vars.zh.md)** 对象表示具有 *标签页范围* 的所有已定义变量（这些变量的范围是此标签页）。
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

如果此标签页当前可见（即它是文件列表中的活动标签页），则返回 **True**，否则返回 **False**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Close即时查找</td><td>

*none*</td><td>

*none*</td><td>

从 [即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 脚本中调用此方法以强制关闭即时查找字段。
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，使您能够显示对话框和弹出菜单。对话框的 **window** 属性将自动分配给此标签页。
</td></tr><tr><td>
GetFocusItem</td><td>

*none*</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，表示标签页中具有焦点的文件或文件夹。

焦点项目通常由其名称周围的轮廓表示，并且通常是最后单击的项目或使用键盘移动到的最后一个项目。焦点项目通常也被选中，但并非总是如此；焦点和选择是两件不同的事情。

如果不存在焦点项目，或者焦点项目是特殊文件或文件夹（例如 *此电脑*，它不能由 **Item** 对象表示），则此方法不会返回对象。（在 JScript 中，测试结果是否 ***== null***，在 VBScript 中测试结果是否 ***is nothing***。）
</td></tr><tr><td>
Notify</td><td>

\<string:type\>  
\<string:msg\>  
\[\<int:timeout\>\]</td><td>

*bool*</td><td>

显示与此标签页关联的通知消息。

目前唯一定义的类型是“status”，它在状态栏中显示消息。

当标签页处于活动状态时，*msg* 字符串将在状态栏中显示。*timeout* 值允许您指定一个可选的超时值（以毫秒为单位），在此超时时间后消息将自动删除。如果没有指定超时，则用户需要单击消息才能将其关闭。
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

当脚本访问 **Tab** 对象的特定属性时，会对标签页的状态进行快照。例如，如果您要求 **selected_files** 属性，则会计算已选文件列表并将其存储在内存中。这可以提高速度，并且还意味着您不必担心在处理列表时列表会在您下方发生更改。如果脚本随后对标签页进行了更改（例如，它选择文件、创建新文件夹等），如果您再次访问相同标签页对象上的相同属性，则这些更改将不会反映在缓存的快照中。要清除缓存的快照并使对象与标签页的当前状态同步，请调用 **Tab.Update** 方法。
</td></tr><tr><td>
Update即时查找Suggestions</td><td>

*array*  
或 ***[vector](vector.zh.md)**:string* 或 *object:***[map](map.zh.md)**</td><td>

*none*</td><td>

当您实现 [即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 脚本时，您可以随时调用此方法来更新显示给用户的建议列表。

您可以提供字符串数组或 **[vector](vector.zh.md)**，或字符串/字符串对的 **[map](map.zh.md)**。

当提供 **[map](map.zh.md)** 时，每个键表示用户选择时将插入的文本，而值表示在建议列表的单独列中显示的提示或描述。

当提供字符串数组或 **[vector](vector.zh.md)** 时，您可以通过用制表符分隔来提供第二列描述。
</td></tr></tbody>
</table>