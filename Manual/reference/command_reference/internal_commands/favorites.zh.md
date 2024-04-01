# Favorites

**收藏夹** 内部命令可用于：

- 显示 [收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md)（全部收藏夹或特定子分支）的动态列表
- 显示 [智能收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 的动态列表
- 将文件夹添加到收藏夹
- 创建新的 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)
- 编辑收藏夹文件夹（通过在配置中打开 [收藏夹列表](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.zh.md) 页面）

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示 [收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md) 的动态生成列表 - 可通过从此列表中选择文件夹来导航到该文件夹。充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。

此命令的一些参数可修改动态列表的外观和行为。请注意，**PATH** 参数可选择指定收藏夹列表的子分支。

*示例：* `Favorites`
</td></tr><tr><td>
ADD</td><td>
/O</td><td>

*(无值)*</td><td>

将当前源文件夹添加到收藏夹列表。系统默认情况下在收藏夹列表中显示文件夹的完整路径。

*示例：* `Favorites ADD`
</td></tr><tr><td>
</td><td>
</td><td>

**nameonly**</td><td>

将当前源文件夹添加到收藏夹列表，并将收藏夹条目的名称设置为文件夹的名称（以便收藏夹列表中仅显示名称，而不显示完整路径）。

*示例：* `Favorites ADD=nameonly`
</td></tr><tr><td>
</td><td>
</td><td>

**alias**</td><td>

添加或修改文件夹别名而不是收藏夹。可使用 **NAME** 参数指定别名的名称，也可省略它以自动使用文件夹的名称。可使用 **PATH** 参数指定别名应指向的路径，也可省略它以自动使用当前路径。

有两种备用语法可用于添加别名。使用 **ADD=alias** 等同于使用 **ALIAS=set**，只是 **PATH** 和 **NAME** 参数的行为如上所述。

*示例：* `Favorites ADD=alias PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
ADDDIALOG</td><td>
/S</td><td>

*(无值)*</td><td>

显示一个对话框，可在添加新收藏夹文件夹时编辑名称和路径。

*示例：* `Favorites ADDDIALOG`
</td></tr><tr><td>
ALIAS</td><td>
/K</td><td>

**delete**</td><td>

删除一个文件夹别名。别名名称必须由 **NAME** 参数提供，且不可选。

*示例：* `Favorites ALIAS=delete NAME=MyAlias`
</td></tr><tr><td>
</td><td>
</td><td>

**set**</td><td>

创建或修改文件夹别名。别名名称必须由 **NAME** 参数提供，路径必须由 **PATH** 参数提供，两者都不可选。

*示例：* `Favorites ALIAS=set NAME=MyAlias PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
</td><td>
</td><td>

**list**</td><td>

生成别名的动态列表，而不是常规收藏夹列表。当需要一个别名菜单以便 (取决于其他参数) 点击它们转到目标、将文件复制到目标等时，请使用此功能。  
系统默认仅显示用户定义的别名；使用 \*\*builtin \*\*或 **all** 关键字可覆盖此设置。

*示例：* `Favorites ALIAS=list NOOPENINTABS SHOWICONS`
</td></tr><tr><td>
</td><td>
</td><td>

**builtin**</td><td>

配合 **list** 关键字使用，仅显示内置别名的长列表（系统默认仅包含用户定义的别名）。

*示例：* `Favorites ALIAS=list,builtin SHOWICONS`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

配合 **list** 关键字使用，将用户定义别名和内置别名都包含在列表中。

*示例：* `Favorites ALIAS=list,all`
</td></tr><tr><td>
AUTOCREATE</td><td>
/S</td><td>

*\<branch path\>*</td><td>

如果指定的分支尚不存在，则自动创建它（由 **BRANCH** 参数指定）。这通常是收藏夹栏使用得最多的方式，目的是在打开工具栏时自动在收藏夹树中创建适当的分支。

*示例：* `FAVORITES BRANCH="Favorites Bar" AUTOCREATE`
</td></tr><tr><td>
BRANCH</td><td>
/K</td><td>

*\<branch path\>*</td><td>

指定要显示的收藏夹树的分支，或在与 **ADD** 或 **ADDDIALOG** 参数结合使用时，指定要添加新收藏夹的分支。要显示整个收藏夹树或添加到收藏夹树根目录，请完全省略 **BRANCH** 参数。使用 **\\** 分隔各个组件来指定嵌套分支，类似于文件夹路径。

如果指定某分支时某些部分或所有部分尚不存在，则在与 **ADD** 或 **ADDDIALOG** 结合使用时，将创建缺少的部分。在用来显示收藏夹列表时，可指定 **AUTOCREATE** 参数，在尚不存在该分支时自动创建。

在与 **ADDDIALOG** 结合使用时，默认情况下会选择指定路径，但之后可在与该对话框交互时更改。

*示例：* `Favorites ADD BRANCH="Test Data\Photos"`
</td></tr><tr><td>
COPYTO</td><td>
/S</td><td>

*(无值)*</td><td>

修改生成的收藏夹列表，将每个项目变为一个“复制”按钮，将选定的文件复制到收藏夹文件夹。

*示例：* `Favorites COPYTO`
</td></tr><tr><td>
EDIT</td><td>
/S</td><td>

*(无值)*</td><td>

在配置中显示 **[收藏夹列表](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.zh.md)** 页面。

*示例：* `Favorites EDIT`
</td></tr><tr><td>
EXCLUDEBRANCH</td><td>
/K</td><td>

*\<name or pattern\>*</td><td>

在显示收藏夹列表时，可使用 **EXCLUDEBRANCH** 参数从生成的列表中排除收藏夹树的整个分支。可指定完整的分支路径，或使用 [通配符](../../wildcard_reference/pattern_matching_syntax.zh.md)。

*示例：* `Favorites EXCLUDEBRANCH NetworkFaves`
</td></tr><tr><td>
FILTER</td><td>
/K</td><td>

*\<wildcard\>*</td><td>

在显示收藏夹或 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 列表时，可使用 **FILTER** 参数按路径过滤该列表，使用 [通配符](../../wildcard_reference/pattern_matching_syntax.zh.md)。不匹配通配符的路径将从生成的列表中隐藏，并且任何变为空的分支也将被裁剪干净。

\`\`Favorites SHOWICONS FILTER C:\\\`\*  
// 仅显示以 C:\\开头的路径//

*示例：* `Favorites SHOWICONS FILTER "~(\*Program Files\*)"`  
// 仅显示不包含 Program Files 的路径。//

若要按子分支而不是路径过滤列表，请改为参阅 **PATH** 参数。
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令结合使用时（参见 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数会在列表的开头添加一个小标题。当列表为空时将隐藏标题。标题仅适用于可能在与按钮本身同一级别生成多个项目的命令。
当 **HEADING** 单独使用时，没有指定文本值，主要按钮的标签文本用于标题。

*示例：* `Favorites SMART HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

如果希望标题文本不同于按钮的标签，则可以指定它。

*示例：* `Favorites HEADING="Best Folders"`
</td></tr><tr><td>
KEYARGS</td><td>
/K/M</td><td>

*\<qualifier:arguments\> ...*</td><td>

在显示收藏夹列表时，如果按住限定符键，此参数可为列表中的项目分配不同的行为。这是一个多值参数——对于列出的每个限定符键组合，可定义一系列单独的参数，这些参数将在选中列表中的项目时使用。

例如，可将收藏夹菜单配置为默认在新标签页中打开收藏夹文件夹，但在按住 <kbd>Ctrl</kbd> 键时，在新 **文件窗口** 中打开。

值的限定符部分由一个或多个表示限定符键的关键字组成——**ctrl**、**shift** 和 **alt**。可将它们组合在一起，例如 **ctrlshift** 表示必须同时按住 <kbd>Ctrl</kbd> 键和 <kbd>Shift</kbd> 键。也可使用关键字 **none** 表示在没有按住任何限定符时应用的参数。

*示例：* `Favorites KEYARGS "ctrl:NEW" "none:NEWTAB=findexisting"`
</td></tr><tr><td>
MENUMARKERS</td><td>
/S</td><td>

*(no value)*</td><td>

如果生成的收藏夹列表包含任何子菜单，则顶级按钮将显示一个表示下拉菜单的标志。

*示例：* `Favorites MENUMARKERS`
</td></tr><tr><td>
MOVETO</td><td>
/S</td><td>

*(no value)*</td><td>

修改生成的收藏夹列表，将每个项目变为一个“移动”按钮，将选定的文件移动到收藏夹文件夹。

*示例：* `Favorites MOVETO`
</td></tr><tr><td>
MULTIFUNC</td><td>
/O</td><td>

*(no value)*</td><td>

生成的收藏夹列表将是 [多功能按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.zh.md)（三按钮按钮）——用鼠标左键单击它们将如同 **OPENINLEFT** 被设置一样，用鼠标右键单击它们将如同 **OPENINRIGHT** 被设置一样，用鼠标中键单击它们将如同 **NEW** 被设置一样。

*示例：* `Favorites MULTIFUNC`
</td></tr><tr><td>
</td><td>
</td><td>

**tabs**</td><td>

除了左键和右键鼠标按钮的功能将让 **文件窗口** 在适当的一侧打开新的标签页这一点之外，上面所述功能与之类似。可通过 **NEWTAB** 参数控制以何种方式打开新标签页。

*示例：* `Favorites MULTIFUNC=tabs`
</td></tr><tr><td>
NAME</td><td>
/K</td><td>

*\<name\>*</td><td>

指定新创建的收藏夹或别名的名称。如果未提供名称，则系统默认使用文件夹的名称。

*示例：* `Favorites ADD=alias NAME=docs PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
NAMESONLY</td><td>
/S</td><td>

*(no value)*</td><td>

在列出智能收藏夹时，列表中的每个项目只会显示各自文件夹的名称，而不显示完整路径。完整路径在工具提示中显示。  
（**NAMESONLY** 参数不适用于常规收藏夹列表，因为可在列表中根据自己的意愿编辑项目标签。如果希望在添加常规收藏夹时自动抑制完整路径，请参阅上面的 **ADD=nameonly** 参数。）

*示例：* `Favorites SMART NAMESONLY`
</td></tr><tr><td>
NEW</td><td>
/S</td><td>

*(no value)*</td><td>

从此命令生成的列表中选出的收藏夹将在新的 **文件窗口** 中打开，而不是在当前 **文件窗口** 中打开。

*示例：* `Favorites NEW`
</td></tr><tr><td>
NEWTAB</td><td>
/O</td><td>

*(no value)*</td><td>

从此命令生成的列表中选出的收藏夹将在 [新标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md) 中打开。

*示例：* `Favorites NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**deflister**</td><td>

如果不存在 **lister**，则“默认 **文件窗口**”将打开，其中包含文件夹的附加标签页。如果存在 **lister**，则该文件夹将在现有 **lister** 中的新的标签页中通常打开。

*示例：* `Favorites NEWTAB=deflister`
</td></tr><tr><td>
</td><td>
</td><td>

**findexisting**</td><td>

在打开新的标签页前，在现有标签页中查找文件夹。如果找到，则现有的标签页将移至最前面；否则将打开新的标签页。首先检查活动标签页，如果活动标签页已显示选定路径，则不执行任何操作。

*示例：* `Favorites NEWTAB=findexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**findinactive**</td><td>

此项与 **findexisting** 类似，但如果活动标签页已显示选定路径，则将打开新的标签页。旨在用于切换至现有标签页的按钮，以便减少混乱，同时保留在需要时为相同的文件夹打开第二个标签页的能力。

*示例：* `Favorites NEWTAB=findinactive`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

从列表中选出的收藏夹打开的新标签页将不会移至最前面。

*示例：* `Favorites NEWTAB=nofocus OPENINDUAL`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

如果在现有标签页中找到文件夹，则将该标签页移至最前面（仅与 **findexisting** 一起使用）。

*示例：* `Favorites NEWTAB=findexisting,tofront`
</td></tr><tr><td>
NOLABELS</td><td>
/S</td><td>

*(no value)*</td><td>

此命令显示的收藏夹列表不会显示收藏夹文件夹的任何标签。只影响顶级项目；子菜单仍会显示标签。应与 **SHOWICONS** 结合使用。

*示例：* `Favorites NOLABELS SHOWICONS`
</td></tr><tr><td>
NOOPENINTABS</td><td>
/S</td><td>

*(no value)*</td><td>

不添加通常显示在生成的收藏夹列表底部的 **在标签页中打开** 命令。

*示例：* `Favorites NOOPENINTABS`
</td></tr><tr><td>
OPENINDEST</td><td>
/S</td><td>

*(no value)*</td><td>

从列表中选出的收藏夹将在目标文件列表或 **文件窗口** 中打开。

*示例：* `Favorites OPENINDEST`
</td></tr><tr><td>
OPENINDUAL</td><td>
/S</td><td>

*(no value)*</td><td>

从列表中选出的收藏夹将在双栏 **文件窗口** 的另一个文件列表中打开。如果 **文件窗口** 尚未处于该模式，则它将被设置为双栏模式。

*示例：* `Favorites OPENINDUAL`
</td></tr><tr><td>
OPENINLEFT</td><td>
/S</td><td>

*(no value)*</td><td>

收藏夹将在双栏 **文件窗口** 的左侧（或顶部）显示中打开。

*示例：* `Favorites KEYARGS none:OPENINLEFT ctrl:OPENINRIGHT`
</td></tr><tr><td>
OPENINRIGHT</td><td>
/S</td><td>

*(no value)*</td><td>

收藏夹将在双栏 **文件窗口** 的右侧（或底部）显示中打开。

*示例：* `Favorites NEWTAB OPENINRIGHT`
</td></tr><tr><td>
PATH</td><td>
</td><td>

*\<folder path\>*</td><td>

当与 **ADD** 参数配合使用时，指定要作为收藏夹或别名添加的路径。如果没有此参数，将使用当前源文件夹。

当不使用 **ADD** 参数时，这会修改动态生成的收藏夹文件夹列表，以便仅显示收藏夹列表中指定子分支的内容。分支路径必须以星号开头。也可使用 **BRANCH** 参数代替此方法——请注意 **BRANCH** 不要求分支路径前面加上星号。
若要按路径而不是子分支过滤列表，请参阅 **FILTER** 参数。

**PATH** 是 **Favorites** 命令的默认参数；不必指定 **PATH** 关键字本身。

*示例：* `Favorites /desktop ADD`  
*示例：* `Favorites \*Projects` <nobr>(等同于 `Favorites BRANCH=Projects`)</nobr>
</td></tr><tr><td>
SHOWICONS</td><td>
/S</td><td>

*(no value)*</td><td>

此命令显示的收藏夹列表将在其中显示项目的图标。请注意，包含 **Favorites** 命令的按钮也必须启用其 **显示图像** 选项。

*示例：* `Favorites SHOWICONS`
</td></tr><tr><td>
SMART</td><td>
/O</td><td>

*(no value)*</td><td>

生成 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 的动态列表，而不是常规收藏夹列表。在 **[智能收藏夹](/Manual/preferences/preferences_categories/frequently_used_paths/smartfavorites.zh.md)** 配置页面上指定列表中显示的文件夹数。

*示例：* `Favorites SMART`

添加 **NAMESONLY** 参数，以仅显示文件夹名称而不是完整路径，并将完整路径移动到工具提示中。

*示例：* `Favorites SMART NAMESONLY`
</td></tr><tr><td>
</td><td>
</td><td>

*\<number of items\>*</td><td>

显示指定数量的智能收藏夹（覆盖在配置中设置的数量）。

*示例：* `Favorites SMART 20 SHOWICONS NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

清除智能收藏夹列表，类似于在配置对话框中单击相应选项。

*示例：* `Favorites SMART=clear`
</td></tr><tr><td>
USEQUALKEYS</td><td>
/S</td><td>

*(no value)*</td><td>

激活主要限定符键的预配置行为——**Ctrl** 将在双栏中打开收藏夹文件夹，**Shift** 在新 **文件窗口** 中打开，**Alt** 在新的标签页中打开。

这等同于 <nobr>`Favorites KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB`</nobr>。

*示例：* `Favorites USEQUALKEYS`
</td></tr></tbody>
</table>