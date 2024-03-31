**Tab**对象表示文件窗口中的一个文件夹标签页（即使标签页控件当前未显示，文件窗口始终至少有一个打开的标签页）。可以从**[文件窗口](lister.zh.md)**对象获取**Tab**对象的集合。**Tab**对象还与**[Command](command.zh.md)**和**[Func](func.zh.md)**对象一起使用，如果某条命令导致打开新的标签，则还与**[Results](results.zh.md)**对象一起使用。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
all</td><td>

*对象:***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有文件和文件夹。

注意：脚本首次访问此属性（以及所有返回**[Items](items.zh.md)**对象的其它属性）时，会截图所有相关项。如果脚本对那些项进行修改（例如，通过创建新文件，修改选择等），集合不会反映这些更改。要重新同步集合，请对该对象调用**Update**方法。
</td></tr><tr><td>
backlist</td><td>

*集合：***[Path](path.zh.md)**</td><td>

返回一个**[Path](path.zh.md)**对象集合，表示此标签页的“后退”历史记录列表中的路径（即点击“返回”按钮后会进入的文件夹）。
</td></tr><tr><td>
color</td><td>

*字符串*</td><td>

返回标签页的指定颜色（如果已通过例如**Go TABCOLOR**命令指定了颜色）。颜色以 R、G、B 格式返回为字符串。
</td></tr><tr><td>
crumbpath</td><td>

*对象：***[Path](path.zh.md)**</td><td>
返回标签页面包屑控件的当前路径（如果它有一个），包括任何幽灵路径。
</td></tr><tr><td>
dest</td><td>

*布尔值*</td><td>

如果此标签页当前为[目标](/Manual/basic_concepts/source_and_destination.zh.md)，则返回**True**，否则返回**False**。

请注意，如果标签页不是目标，你不能总是认为它是源。为此请使用单独的**source**属性。
</td></tr><tr><td>
dirs</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有文件夹。
</td></tr><tr><td>
dirty</td><td>

*布尔值*</td><td>

如果标签页标记为脏的，则返回**True**，表示其内容列表可能已过时。如果标签页处于后台并且用户已关闭配置/文件夹标签页/选项/处理后台标签页中的文件更改”选项，则可能发生这种情况。
</td></tr><tr><td>
displayed_label</td><td>

*字符串*</td><td>
返回此标签页当前显示的标签。
</td></tr><tr><td>
filegroups</td><td>

*集合：***[FileGroup](filegroup.zh.md)**</td><td>

返回一个**[FileGroup](filegroup.zh.md)**对象集合，它表示标签页中所有文件组（当标签页被分组时）。可以通过**format.group_by**属性测试该标签页是否已分组。
</td></tr><tr><td>
files</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有文件。
</td></tr><tr><td>
format</td><td>

*对象：***[Format](format.zh.md)**</td><td>

返回一个**[Format](format.zh.md)**对象，它表示此标签页中的当前文件夹格式。
</td></tr><tr><td>
forwardlist</td><td>

*集合：***[Path](path.zh.md)**</td><td>

返回一个**[Path](path.zh.md)**对象集合，它表示此标签页的“前进”历史记录列表中的路径（即点击“前进”按钮后会进入的文件夹）。
</td></tr><tr><td>
hidden</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中隐藏的所有文件和文件夹。
</td></tr><tr><td>
hidden_dirs</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中隐藏的所有文件夹。
</td></tr><tr><td>
hidden_files</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中隐藏的所有文件
</td></tr><tr><td>
label</td><td>

*字符串*</td><td>

返回当前分配的标签页标签。如果尚未分配自定义标签，请注意这可能是一个空字符串。**displayed_label**属性在所有情况下都返回当前显示的标签。
</td></tr><tr><td>
linktab</td><td>

*对象:***Tab**</td><td>

如果此标签页链接到另一个标签页，则返回一个**Tab**对象，表示该链接的标签页。如果此标签页未链接，此属性返回**0**。
</td></tr><tr><td>
lister</td><td>

*对象：***[文件窗口](lister.zh.md)**</td><td>

返回一个**[文件窗口](lister.zh.md)**对象，它表示拥有此标签页的父文件窗口。
</td></tr><tr><td>
lock</td><td>

*字符串*</td><td>
返回标签页的当前锁定状态；“关闭”、“开启”、“更改”、“重复使用”之一。
</td></tr><tr><td>
navlock</td><td>

*布尔值*</td><td>

如果此标签页已在导航锁定模式下链接，则返回**True**。如果标签页未链接，此属性不存在，因此请确保首先检查**linktab**的值。
</td></tr><tr><td>
path</td><td>

*对象：***[Path](path.zh.md)**</td><td>
返回此标签页中显示的当前路径。
</td></tr><tr><td>
quickfilter</td><td>

*对象：***[QuickFilter](quickfilter.zh.md)**</td><td>

返回一个**[QuickFilter](quickfilter.zh.md)**对象，提供此标签页中快速过滤器状态的相关信息。
</td></tr><tr><td>
right</td><td>

*布尔值*</td><td>

如果此标签页当前位于双栏器文件窗口的右侧或底部，则返回**True**，否则返回**False**。
</td></tr><tr><td>
selected</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有选定的文件和文件夹。如果在标签页中已启用[复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，这将是已选中的项的集合，而不是选定的项的集合。
</td></tr><tr><td>
selected_dirs</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有已选中的文件夹。
</td></tr><tr><td>
selected_files</td><td>

*对象：***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)**对象，它表示当前在此标签页中显示的所有已选中的文件
</td></tr><tr><td>
selstats</td><td>

*对象：***[TabStats](tabstats.zh.md)**</td><td>

返回一个**[TabStats](tabstats.zh.md)**对象，它提供有关该标签页的各种信息，包括文件数量、已选择的文件数量、已选择文件的总大小等。此对象提供的“已选择”计数考虑了[复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md）（即，如果复选框模式当前已启用，则计数将是针对已选中的文件，而不是针对已选择的文件）。
</td></tr><tr><td>
source</td><td>

*布尔值*</td><td>
返回此标签页当前是 [源](/Manual/basic_concepts/source_and_destination.zh.md)的 **True**，其他情况下返回 **False**。

请注意，如果标签页不是源，则不能总是假设它为目标。使用单独的 **dest** 属性。
</td></tr><tr><td>
stats</td><td>

*object:***[TabStats](tabstats.zh.md)**</td><td>

返回一个 **[TabStats](tabstats.zh.md)** 对象，它提供有关标签页的各种信息，包括文件数量、所选文件数量、选定文件总大小等。与 **selstats** 不同，此对象不考虑 [选择模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md) （因此，“已选择”数量将指选中的文件，而不是选中的文件）。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

此 **[Vars](vars.zh.md)** 对象表示具有 *标签页范围*（此标签页的范围）的所有定义变量。
</td></tr><tr><td>
visible</td><td>

*bool*</td><td>

如果此标签页当前可见（即它是文件列表中的活动标签页），则返回 **True**；否则返回 **False**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Close即时查找</td><td>

*无*</td><td>

*无*</td><td>

从 [即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 脚本调用此方法以强制关闭即时查找字段。
</td></tr><tr><td>
Dlg</td><td>

*无*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，该对象允许你显示对话框和弹出菜单。对话框的 **window** 属性将自动分配给此标签页。
</td></tr><tr><td>
GetFocusItem</td><td>

*无*</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，表示标签页中获得焦点的文件或文件夹。

焦点项通常用它名称周围的轮廓表示，并且通常是最近单击或使用键盘移动到的最后一个项。焦点项也通常被选中，但并非总是如此；焦点和选择是两件不同的事情。

如果焦点项不存在，或者焦点项是特殊文件或文件夹，例如不能用 **Item** 对象表示的 *此电脑*，则此方法不会返回对象。（在 JScript 中，如果结果 ***== null***，则进行测试；在 VBScript 中，如果结果 ***is nothing***，则进行测试。）
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

当脚本访问 **Tab** 对象的特定属性时，会对标签页的状态进行快照。例如，如果你询问 **selected_files** 属性，所选文件列表将被计算，然后存储在内存中。这可以加快速度，还意味着在处理过程中不必担心列表在你使用时发生更改。如果脚本随后对标签页进行更改（例如，选择文件、创建新文件夹等），如果在同一个标签页对象上再次访问相同属性，缓存的快照不会反映这些更改。要清除缓存的快照并重新同步对象与标签页的当前状态，请调用 **Tab.Update** 方法。
</td></tr><tr><td>
Update即时查找Suggestions</td><td>

*数组*  
或 ***[vector](vector.zh.md)**:string* 或 *object:***[map](map.zh.md)**</td><td>

*无*</td><td>

当实现 [即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 脚本时，可以随时调用此方法以更新向用户显示的建议列表。

你可以提供一个字符串的数组或 **[vector](vector.zh.md)**，或者提供一个字符串/字符串对的 **[map](map.zh.md)**。

提供 **[map](map.zh.md)** 时，每个键表示如果用户选择，则将插入的文本，而值表示提示或描述，该提示或描述显示在建议列表中的单独列中。

提供字符串数组或 **[vector](vector.zh.md)** 时，可以通过用制表符将它与主值分隔来提供第二列描述。
</td></tr></tbody>
</table>