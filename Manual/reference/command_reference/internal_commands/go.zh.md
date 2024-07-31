# Go
**Go** 内部命令可用于：

- [导航](/Manual/basic_concepts/the_lister/navigation/README.zh.md) 到文件窗口中的另一个文件夹
- 在 [历史记录列表](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.zh.md) 中前后移动，并显示历史记录列表的内容
- 连接和断开网络共享
- 在工具栏上显示驱动器列表
- 在下拉菜单中显示文件夹的内容
- 在 [FTP 地址簿](/Manual/ftp/ftp_address_book/README.zh.md) 中显示网站列表
- 打开新的文件窗口
- 打开和处理 [文件夹标签](/Manual/basic-concepts/the_lister/tabs/README.zh.md) 和 [标签组](/Manual/basic-concepts/the_lister/tabs/tab_groups.zh.md) 。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>
BACK</td><td>
/S</td><td>

*(没有值)*</td><td>

导航到 [历史记录列表](/Manual/basic-concepts/the_lister/navigation/recent_and_history_lists.zh.md) 中的上一文件夹。历史记录列表将保留文件夹的文件选择和滚动偏移状态。**BACK** 参数可以与 **UP** 参数结合使用；在这种情况下，如果历史记录列表中的上一个文件夹是当前文件夹的父文件夹，Opus 将返回（保留选择等），而不是 **UP**。

你可以将此与更改导航目标的参数结合使用，如 **NEW**、**NEWTAB**、**OPENINDUAL** 等。

*示例：* `Go BACK`
</td></tr><tr><td>
BACKLIST</td><td>
/O</td><td>

*(没有值)*</td><td>

显示历史记录列表中所有先前文件夹的列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md) ）。这用于默认工具栏中“后退”按钮附加的下拉菜单中。

*示例：* `Go BACKLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

仅显示文件夹名称，而不是完整路径。将鼠标悬停在项目上时，工具提示将显示完整路径。

*示例：* `Go BACKLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

不会在生成的历史记录列表上显示图标。

*示例：* `Go BACKLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

将加速器键 **0** 到 **9** 分配给生成的历史记录列表上显示的前十个项目。

*示例：* `Go BACKLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

按字母顺序而不是按时间顺序对历史记录列表进行排序。

*示例：* `Go BACKLIST=sort`
</td></tr><tr><td>
COMPATIBILITYFILES</td><td>
/S</td><td>

*(没有值)*</td><td>

在文件夹及其兼容性存储之间切换。并非所有文件夹都有兼容性存储 - 在这种情况下，此命令将不起作用。例如，从 **C:\Program Files** 进入 **C:\Users\\..\VirtualStore\Program Files**，反之亦然。

兼容性存储的概念是在 Windows Vista 中引入的，并增加了 UAC，以支持尝试将文件保存在程序文件夹中的旧软件。现如今，几乎不会遇到这个概念。

*示例：* `Go COMPATIBILITYFILES`
</td></tr><tr><td>
CONNECT</td><td>
/O</td><td>

*(没有值)*</td><td>

显示系统对话框，允许你将网络共享映射到驱动器号。

*示例：* `Go CONNECT`
</td></tr><tr><td>
</td><td>
</td><td>

*\<网络路径\>*</td><td>

将指定的网络路径映射到驱动器号。

*示例：* `Go CONNECT \\server\share`
</td></tr><tr><td>
COPYARGS</td><td>
/K/R</td><td>

*(没有值)*</td><td>

诸如 `Go FOLDERCONTENT=copy` 的命令会生成一系列按钮，每个按钮将文件复制或移动到或从不同位置。每个生成的按钮都会运行 Opus **Copy** 命令，该命令采用与 **Go** 命令不同的参数。

**COPYARGS** 参数允许你指定一个或多个要添加到每个生成按钮中的附加 **Copy** 命令参数。

由于这是一个“原始”参数，它应该是该行上的最后内容。在单词“COPYARGS”之后的全部文本都将原样接受，包括任何引号字符，并附加到各个生成按钮的 copy 命令中。

*示例：* `Go C:\ FOLDERCONTENT=copy COPYARGS COPYFILETIMES=no`
</td></tr><tr><td>
CURDIR</td><td>
/O</td><td>

*(没有值)*</td><td>

为 **Go** 命令激活“当前目录”模式。当结合使用 **PATH** 参数的驱动器号时，此模式使得 Opus 导航到指定驱动器上最近访问的文件夹。Opus 会记住系统中每个驱动器的“当前目录”，即使从一个会话切换到另一个会话。

当与 **DRIVEBUTTONS** 参数结合使用时，生成的驱动器号按钮将具有相同行为，并且会突出显示以指示“当前驱动器”。通过这种方式，你可以从一个驱动器单击到另一个驱动器，记住每个驱动器上以前使用的文件夹。

*示例：* `Go D: CURDIR`  
*示例：* `Go DRIVEBUTTONS=fixed CURDIR`
</td></tr><tr><td>
</td><td>
</td><td>

**rootmode**</td><td>

修改“当前目录”模式，以便当你单击当前所在的驱动器的按钮时，它会将你带到驱动器的根目录（通常情况下，它什么事也不会做）。

*示例：* `Go DRIVEBUTTONS CURDIR=rootmode`
</td></tr><tr><td>
CURRENT</td><td>
/S</td><td>

*(没有值)*</td><td>

指明当前源文件夹。此参数用于在其它标签、文件窗口或文件列表中打开当前文件夹。

*示例：* `Go CURRENT OPENINDUAL`
</td></tr><tr><td>
DESTPATH</td><td>
/S</td><td>

*(没有值)*</td><td>

指明当前目标文件夹。此参数用于在源文件列表（或其它文件窗口或标签）中打开目标文件夹。

*示例：* `Go DESTPATH`
</td></tr><tr><td>
DISCONNECT</td><td>
/S</td><td>

*(没有值)*</td><td>

显示系统对话框，允许你断开（取消映射）网络共享。

*示例：* `Go DISCONNECT`
</td></tr><tr><td>
DRIVEBUTTONS</td><td>
/O</td><td>

*(没有值)*</td><td>

显示系统中当前所有驱动器的列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md) ）。单击按钮将源文件夹导航到该驱动器的根目录。也可以右键单击驱动器按钮以显示每个驱动器的上下文菜单。

此参数的不同值可用于限制显示的驱动器。

*示例：* `Go DRIVEBUTTONS`
</td></tr><tr><td>
</td><td>
</td><td>

**fixed**</td><td>

仅显示固定驱动器（硬盘）。

*示例：* `Go DRIVEBUTTONS=fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**network**</td><td>

仅显示网络（已映射）驱动器。

*示例：* `Go DRIVEBUTTONS=network`
</td></tr><tr><td>
</td><td>
</td><td>

**cdrom**</td><td>

仅显示 CD-ROM（和 DVD）驱动器。

*示例：* `Go DRIVEBUTTONS=cdrom`
</td></tr><tr><td>
</td><td>
</td><td>

**removable**</td><td>

仅显示可移动驱动器（软盘和某些 USB 驱动器）。

*示例：* `Go DRIVEBUTTONS=removable,cdrom`
</td></tr><tr><td>
</td><td>
</td><td>

**ramdisk**</td><td>
只显示 RAM 驱动器。

*示例：* `Go DRIVEBUTTONS=ramdisk`
</td></tr><tr><td>
</td><td>
</td><td>

**mtp**</td><td>

只显示 MTP（便携式）设备。

*示例：* `Go DRIVEBUTTONS=mtp`
</td></tr><tr><td>
</td><td>
</td><td>

**iconlettersoff**</td><td>

禁用显示各个驱动器图标的小型驱动器号。

*示例：* `Go DRIVEBUTTONS=fixed,iconlettersoff`
</td></tr><tr><td>
</td><td>
</td><td>

**iconletterson**</td><td>

启用显示各个驱动器图标的小型驱动器号。

*示例：* `Go DRIVEBUTTONS=iconletterson`
</td></tr><tr><td>
</td><td>
</td><td>

**labels**</td><td>

显示各个驱动器的标签。默认情况下，只显示各个驱动器的号。

*示例：* `Go DRIVEBUTTONS=fixed,labels`
</td></tr><tr><td>
</td><td>
</td><td>

**noletters**</td><td>

防止显示各个驱动器的号，如果使用 **labels** 关键字显示标签。注意，如果你想完全禁用在按钮中显示的任何文本，你需要在 [按钮编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 中关闭按钮的 **显示标签** 复选框。

*示例：* `Go DRIVEBUTTONS=labels,noletters`
</td></tr><tr><td>
</td><td>
</td><td>

**multifunc**</td><td>

生成的驱动器按钮将是 [多功能按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.zh.md)（三按钮按钮） - 使用鼠标左键单击它们将作为 **OPENINLEFT** 设置的效果，右键将作为 **OPENINRIGHT** 设置的效果，中键将作为 **NEW** 设置的效果。

*示例：* `Go DRIVEBUTTONS=fixed,network,multifunc`
</td></tr><tr><td>
</td><td>
</td><td>

**multifunctabs**</td><td>

类似于 **multifunc**，不同之处在于鼠标左键和右键功能将在文件窗口适当侧打开一个新标签。你可以使用 **NEWTAB** 参数控制新标签的打开方式。

*示例：* `Go DRIVEBUTTONS=multifunctabs,labels,fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**lettersbeforelabels**</td><td>

当同时显示驱动器号和标签时，首先将显示驱动器号。如果没有该设置，则在标签之后显示号。

*示例：* `Go DRIVEBUTTONS=fixed,labels,lettersbeforelabels`
</td></tr><tr><td>
</td><td>
</td><td>

**offline**</td><td>

显示网络驱动器时，将只显示脱机驱动器（默认情况下，显示已连接和脱机驱动器）。

*示例：* `Go DRIVEBUTTONS=network,offline`
</td></tr><tr><td>
</td><td>
</td><td>

**online**</td><td>

显示网络驱动器时，将只显示在线（已连接）驱动器。

*示例：* `Go DRIVEBUTTONS=network,online`
</td></tr><tr><td>
</td><td>
</td><td>

**hideempty**</td><td>

隐藏空驱动器的显示。未插入介质的可移除磁盘（软盘、读卡器、DVD）将不会显示。

*示例：* `Go DRIVEBUTTONS=cdrom,removable,hideempty`
</td></tr><tr><td>
</td><td>
</td><td>

**+***\<letters\>*</td><td>

只显示指定的驱动器号。任何未指定的驱动器都将隐藏。

*示例：* `Go DRIVEBUTTONS=removable,+fhjm`
</td></tr><tr><td>
</td><td>
</td><td>

**-***\<letters\>*</td><td>

不显示指定的驱动器号。

*示例：* `Go DRIVEBUTTONS=-d`
</td></tr><tr><td>
DUALPATH</td><td>
/K</td><td>

*\<读入路径\>*</td><td>

指定要读入双显示文件窗口目标文件列表中的路径（标准 **PATH** 参数读入源文件列表）。

\`\`Go C:\ DUALPATH D:\\\`
</td></tr><tr><td>
EJECT</td><td>
/S</td><td>

*(无值)*</td><td>

触发 **PATH** 参数指定的驱动器中媒体的弹出。如果驱动器没有弹出机制，则此命令无效。

*示例：* `Go D: EJECT`
</td></tr><tr><td>
EXISTINGLISTER</td><td>
/O</td><td>

*(无值)*</td><td>

如果已在现有文件窗口中打开了指定的文件夹（包括其它窗口中的非活动文件夹标签），则该命令会激活该文件窗口及其内部的相应标签，且不执行任何其它操作。如果找到了另一个窗口，则会忽略该命令的其它参数。如果指定的路径尚未在另一个窗口中打开，则命令将继续执行，就像没有给出 **EXISTINGLISTER** 参数一样。

*示例：* `Go "C:\Program Files" NEW EXISTINGLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**seltabsonly**</td><td>

只会考虑选定的文件夹标签。如果指定的文件夹在现有文件窗口中打开，但位于当前未选中的文件夹标签中，那么该标签将被忽略。

*示例：* `Go "C:\Program Files" NEW EXISTINGLISTER=seltabsonly`
</td></tr><tr><td>
EXPANDBRANCH</td><td>
/O</td><td>

*(无值)*</td><td>

当在配置中启用 [文件夹展开](/Manual/preferences/preferences_categories/file_displays/folder_expansion.zh.md) 时，此命令允许你通过编程方式展开当前文件列表中的文件夹。

在没有值的情况下使用时，所有当前选中的文件夹都将展开。你可以将此与 **PATH** 参数结合使用，按路径指定要展开的项，或者与 **wild** 或 **regexp** 关键字结合使用，按模式匹配指定。

*示例：* `Go EXPANDBRANCH`
</td></tr><tr><td>
</td><td>
</td><td>

**case**</td><td>

与 `regexp` 或 `wild` 结合使用，以使通配符操作区分大小写。

*示例：* `Go EXPANDBRANCH=toggle,regexp,case PATH \[a-z\]+`
</td></tr><tr><td>
</td><td>
</td><td>

**clearselect**</td><td>

与 `collapse` 结合使用，以自动清除要折叠的文件夹中的任何文件或文件夹的选择。

*示例：* `Go EXPANDBRANCH=collapse,clearselect`
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

折叠当前选中的文件夹，如果它们当前已展开。此外，如果选中了单个文件或未展开的文件夹，并且它位于已展开的父文件夹中，则父文件夹将折叠。

*示例：* `Go EXPANDBRANCH=collapse`
</td></tr><tr><td>
</td><td>
</td><td>

**noparent**</td><td>

与 `Go EXPANDBRANCH=collapse` 结合使用时，这可以防止它折叠选定文件或未展开文件夹的父文件夹。

*示例：* `Go EXPANDBRANCH=collapse,noparent`
</td></tr><tr><td>
</td><td>
</td><td>

**regexp**</td><td>

**PATH** 参数将被解读为 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md)。

*示例：* `Go EXPANDBRANCH=toggle,regexp PATH \[a-z\]+`
</td></tr><tr><td>
</td><td>
</td><td>

**script**</td><td>

当从脚本运行时，它会使用添加到 [命令](/Manual/reference/scripting_reference/scripting_objects/command.zh.md) 对象的文件夹来展开/折叠，而不是选定的文件夹。

*示例：* `Go EXPANDBRANCH=script,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换当前选定文件夹的展开状态。

*示例：* `Go EXPANDBRANCH=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggleall**</td><td>

以组的形式切换选定文件夹的展开状态。如果有任何一个未展开，则所有都会展开。如果全部展开，则全部折叠。
*示例：* `Go EXPANDBRANCH=toggleall`
</td></tr><tr><td>
</td><td>
</td><td>

**top**</td><td>

限制命令展开/折叠项于顶级，忽略嵌套项。（如果使用 **PATH** 参数来指定项则没有效果）。

*示例：* `Go EXPANDBRANCH=toggleall,top`
</td></tr><tr><td>
</td><td>
</td><td>

**wild**</td><td>

**PATH** 参数将被解释为 [通配符](../../wildcard_reference/pattern_matching_syntax.zh.md)。请注意，通配符仅针对名称进行测试，而不针对完整路径。与通配符匹配的任何文件夹都会被展开或折叠，无论它们当前是否被选中。

*示例：* `Go EXPANDBRANCH=toggleall,top,wild PATH *_backup`
</td></tr><tr><td>
FDBBUTTONS</td><td>
/O</td><td>

*(无值)*</td><td>

该命令作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。它允许您向工具栏添加模拟标准文件列表边框按钮的按钮。此命令设计为在文件列表工具栏中用作标准按钮的替代品。

默认情况下，此命令将添加 *后退*、*前进*、*向上*、*复制*、*交换* 和 *切换布局* 按钮。您可以使用各个关键字来精确控制添加哪些按钮。

*示例：* `Go FDBBUTTONS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<button keywords\>*</td><td>

使用 **back**、**forward**、**up**、**copy**、**swap** 和 **layout** 关键字的组合来精确控制要添加的按钮。

*示例：* `Go FDBBUTTONS back,forward` - 显示 *后退* 和 *前进* 按钮  
*示例：* `Go FDBBUTTONS -layout` - 显示所有按钮，但显示 *切换布局* 按钮
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

不要显示生成按钮的图标。

*示例：* `Go FDBBUTTONS -layout,noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**nolabels**</td><td>

不要显示生成按钮的标签。

*示例：* `Go FDBBUTTONS swap,layout,nolabels`
</td></tr><tr><td>
</td><td>
</td><td>

**dropdowns**</td><td>

在适用的情况下，使生成的按钮下拉按钮。

*示例：* `Go FDBBUTTONS back,forward,up,dropdowns`
</td></tr><tr><td>
FINDTITLE</td><td>
/K</td><td>

*\<title string\>*</td><td>

查找标题与指定字符串匹配的所有当前打开的文件窗口，并将它们置于最前面。要搜索的字符串可以是特定标题或 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。

*示例：* `Go FINDTITLE *Projects`\*
</td></tr><tr><td>
FOLDERCONTENT</td><td>
/O</td><td>

*(无值)*</td><td>

在下拉菜单中显示 **PATH** 参数指定路径的内容（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。生成的列表中的子文件夹可以选择，以便导航到该位置，并且可以选择生成列表中的文件以打开该文件。您还可以在项目上右键单击以显示其上下文菜单，并将文件拖放到文件夹（以复制或移动它们）或拖放到其它文件（以打开它们）。如果您将鼠标悬停在子文件夹上，它将展开以显示显示子文件夹内容的另一个菜单。

与 **FOLDERCONTENT** 一起使用时，**PATH** 参数支持用竖线 (**\|**) 分隔的多个路径。例如，这可以让您在文件窗口中的下拉菜单中复制（无论如何，在一定程度上）Windows 开始菜单，方法是同时显示当前用户的开始文件夹和公共（所有用户）开始文件夹。

*示例：* `Go /start|/commonstartmenu FOLDERCONTENT`
</td></tr><tr><td>
</td><td>
</td><td>

**button**</td><td>

生成的 **FOLDERCONTENT** 列表中的子文件夹将显示为菜单按钮。单击按钮部分将读取子文件夹，展开下拉菜单将显示其内容。

*示例：* `Go C: FOLDERCONTENT=button`
</td></tr><tr><td>
</td><td>
</td><td>

**nomenusel**</td><td>

将鼠标悬停在子文件夹上将展开它，而单击将导航到它。即使还指定了 **showempty**，也强制隐藏空文件夹。

*示例：* `Go C: FOLDERCONTENT=nomenusel`
</td></tr><tr><td>
</td><td>
</td><td>

**dblclickmenu**</td><td>

对于带有子项的文件夹，悬停和单击都将展开其子菜单，而双击将导航到它们。对于没有子项的文件夹，单击一次就足以导航到它们。

*示例：* `Go C: FOLDERCONTENT=dblclickmenu`
</td></tr><tr><td>
</td><td>
</td><td>

**norecurse**</td><td>

防止生成的列表中的子文件夹展开；列表将仅限于一个文件夹级别（尽管仍然会显示子文件夹，但您将无法展开它们）。

*示例：* `Go C: FOLDERCONTENT=norecurse`
</td></tr><tr><td>
</td><td>
</td><td>

**noparselinks**</td><td>

防止解析快捷方式。如果没有这个，对文件夹的快捷方式将可以扩展，就像普通子文件夹一样。

*示例：* `Go /profile FOLDERCONTENT=noparselinks`
</td></tr><tr><td>
</td><td>
</td><td>

**nodirs**</td><td>

从生成的列表中排除子文件夹 - 仅显示文件。

*示例：* `Go /temp FOLDERCONTENT=nodirs`
</td></tr><tr><td>
</td><td>
</td><td>

**nofiles**</td><td>

从生成的列表中排除文件 - 仅显示文件夹。

*示例：* `Go C: FOLDERCONTENT=nofiles`
</td></tr><tr><td>
</td><td>
</td><td>

**showhidden**</td><td>

包括列表中的隐藏文件和文件夹 - 没有这个，具有 **H** 属性设置的项目将被排除。

*示例：* `Go C: FOLDERCONTENT=nofiles,showhidden`
</td></tr><tr><td>
</td><td>
</td><td>

**showempty**</td><td>

空子文件夹将包含在生成的列表中。如果没有这个，则会排除空子文件夹。

*示例：* `Go CURRENT FOLDERCONTENT=showempty`
</td></tr><tr><td>
</td><td>
</td><td>

**filefilter=***\<pattern\>*</td><td>

指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 文件名必须匹配该模式才能包含在生成的列表中（如果没有这个，则包括所有文件）。

因为此关键字需要嵌入等号，所以必须用引号将整个参数值括起来，以免混淆命令解析器。

*示例：* `Go C: FOLDERCONTENT="filefilter=*.exe"`

如果您需要在模式中使用逗号 (,) 字符，请用嵌入引号将模式括起来。以下示例将 **\*,**\* 指定为模式：

*示例：* `Go C: FOLDERCONTENT="filefilter=""*"*"""`  
*示例：* `Go C: FOLDERCONTENT="filefilter=""*"*"",nodirs"`
</td></tr><tr><td>
</td><td>
</td><td>

**dirfilter=***\<pattern\>*</td><td>

指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 文件夹名称必须匹配该模式才能包含在生成的列表中（如果没有这个，则包括所有文件夹）。

因为此关键字需要嵌入等号，所以必须用引号将整个参数值括起来，以免混淆命令解析器。

*示例：* `Go C:\Work FOLDERCONTENT="dirfilter=~(.svn)"`

如果您需要在模式中使用逗号 (,) 字符，请用嵌入引号将模式括起来，类似于上面的 **filefilter** 示例。
</td></tr><tr><td>
</td><td>
</td><td>

**maxfiles=***\<num\>*</td><td>

指定每个层级所列出的最大文件数。如果生成了子文件夹菜单，那么每个菜单也以类似方式受到限制。

由于此关键字需要嵌入等号，因此必须将整个参数值用引号引起来，以避免命令解析器产生混淆。

*示例：* `Go C: FOLDERCONTENT="maxfiles=5,sortdate"`

如果您希望全部排除文件，那么使用 **nofiles** 比 **maxfiles=0** 的效率更高。
</td></tr><tr><td>
</td><td>
</td><td>

**maxdirs=***\<num\>*</td><td>

指定每个层级所列出的最大文件夹数。如果生成了子文件夹菜单，那么每个菜单也以类似方式受到限制。

由于此关键字需要嵌入等号，因此必须将整个参数值用引号引起来，以避免命令解析器产生混淆。

*示例：* `Go C: FOLDERCONTENT="maxdirs=10"`

如果您希望全部排除文件夹，那么使用 **nodirs** 比 **maxdirs=0** 的效率更高。
</td></tr><tr><td>
</td><td>
</td><td>

**maxdepth=***\<levels\>*</td><td>

指定生成列表中子文件夹展开的最大深度。

由于此关键字需要嵌入等号，因此必须将整个参数值用引号引起来，以避免命令解析器产生混淆。

*示例：* `Go C: FOLDERCONTENT="maxdepth=10"`
</td></tr><tr><td>
</td><td>
</td><td>

**hideext**</td><td>

在生成列表中的文件不显示其文件名扩展名。

*示例：* `Go /mydocuments FOLDERCONTENT=hideext`
</td></tr><tr><td>
</td><td>
</td><td>

**sortext**</td><td>

按文件扩展名对生成列表中的文件进行排序。

*示例：* `Go /temp FOLDERCONTENT=nodirs,sortext`
</td></tr><tr><td>
</td><td>
</td><td>

**sortsize**</td><td>

按大小对生成列表中的文件进行排序。

*示例：* `Go "C:\Program Files" FOLDERCONTENT=sortsize`
</td></tr><tr><td>
</td><td>
</td><td>

**sortdate**</td><td>

按时间戳对生成列表中的文件进行排序。

*示例：* `Go /downloads FOLDERCONTENT=sortdate`
</td></tr><tr><td>
</td><td>
</td><td>

**sortnone**</td><td>

完全不对列表进行排序。文件和文件夹仍然会按照分组进行分组，但是每个组中显示的顺序与操作系统返回的顺序一致。通常与按名称排序相同，但在某些文件夹中可能导致特殊或随机排序。

使用 *快速访问* 文件夹（在 Windows 11 的更高版本中重新命名为 *主页*）时很有用，这里的顺序是您定义的，并且通常希望在显示项目的所有位置都保留此顺序。

*示例：* `Go /quickaccess FOLDERCONTENT=norecurse,nofiles,sortnone`
</td></tr><tr><td>
</td><td>
</td><td>

**sortreverse**</td><td>

反转生成列表中项的常规排序顺序。

*示例：* `Go /downloads FOLDERCONTENT=sortdate,sortreverse`
</td></tr><tr><td>
</td><td>
</td><td>

**copy**</td><td>

生成列表专门用于将所选文件复制到列表中显示的文件夹中。当您从下拉菜单中选择某个子文件夹时，会修改标准行为。例如，如果您选择当前文件夹中的某些文件，然后从下拉 `Go FOLDERCONTENT` 菜单中选择某个子文件夹，这些文件将被复制到该文件夹。

每个生成按钮都将运行 **Copy** 命令。您可以使用单独的 **COPYARGS** 参数指定每个生成按钮中包含的其它 **Copy** 命令参数。

*示例：* `Go \\NAS\Music FOLDERCONTENT=nofiles,copy`
</td></tr><tr><td>
</td><td>
</td><td>

**move**</td><td>

从生成列表中选择某个子文件夹会将所选文件移动到该文件夹。

*示例：* `Go D:\Archive\Documents FOLDERCONTENT=nofiles,move`
</td></tr><tr><td>
</td><td>
</td><td>

**copytosource**</td><td>

点击生成列表中的文件或文件夹会将其复制到当前文件夹。（请注意，此复制方向与上面讨论的 **copy** 和 **move** 模式相反。）

如果您有一个包含模板项的文件夹，当在不同的文件夹间移动时需要经常将这些项复制到不同文件夹中，这种情况会很有用。要更新模板项列表，只需向文件夹添加或删除项（或它们的软链接）即可。

*示例：* `Go "C:\My Templates" FOLDERCONTENT=copytosource`

每个生成按钮都将运行 **Copy** 命令。您可以使用单独的 **COPYARGS** 参数指定每个生成按钮中包含的其它 **Copy** 命令参数。

*示例：* `Go C:\ FOLDERCONTENT=copy COPYARGS COPYFILETIMES=no\*\*`

没有 "copyto..." 关键字的单独 "move" 版本，因为似乎不需要它们，但是您可以通过 **COPYARGS** 参数实现相同的功能：

*示例：* `Go C:\ FOLDERCONTENT=copy COPYARGS MOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**copytodest**</td><td>

类似于 **copytosource**，但您点击的项会被复制到目标文件夹，而不是当前（源）文件夹。

*示例：* `Go "C:\Templates" FOLDERCONTENT=copytodest,nodirs`
</td></tr><tr><td>
</td><td>
</td><td>

**copytoleft**</td><td>

类似于 **copytosource**，但您点击的项始终会复制到左侧文件夹（假设是双显示窗口）。

*示例：* `Go "C:\Templates" FOLDERCONTENT=copytoleft`
</td></tr><tr><td>
</td><td>
</td><td>

**copytoright**</td><td>

类似于 **copytosource**，但您点击的项始终会复制到右侧文件夹（假设是双显示窗口）。

*示例：* `Go "C:\Templates" FOLDERCONTENT=copytoright`
</td></tr><tr><td>
</td><td>
</td><td>

**useshell**</td><td>

通常文件夹路径（例如 **C:\\**）使用本机 Windows API 函数进行枚举。如果您指定 **useshell** 关键字，则将改用 Shell （即资源管理器）进行枚举。这在某些情况下可能为您提供本地化名称，以及不同的排序和不同的内容。

*示例：* `Go C: FOLDERCONTENT=useshell`
</td></tr><tr><td>
FORWARD</td><td>
/S</td><td>

*(无值)*</td><td>

导航到 [历史记录列表](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.zh.md) 中的下一个文件夹。

您可以将此与更改导航目标的参数结合使用，例如 **NEW**, **NEWTAB**, **OPENINDUAL** 等。

*示例：* `Go FORWARD`
</td></tr><tr><td>
FORWARDLIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示历史记录列表中所有后续文件夹的列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这用于默认工具栏上“前进”按钮上附加的下拉菜单中。

*示例：* `Go FORWARDLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

仅显示文件夹名称，不显示完整路径。将鼠标悬停在项上时，工具提示将显示完整路径。

*示例：* `Go FORWARDLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

在生成的历史列表中不显示图标。

*示例：* `Go FORWARDLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

将快捷键 **0** 到 **9** 分配到生成的历史列表中显示的前十个项。
*示例:* `Go FORWARDLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

按字母顺序而非按时间顺序排列历史记录列表。

*示例:* `Go FORWARDLIST=sort`
</td></tr><tr><td>
FROMSEL</td><td>
/S</td><td>

*(无值)*</td><td>

指示源文件列表中的第一个选定文件夹。此参数用于打开选定的文件夹（在当前文件列表、其它标签页、新的文件窗口等等中）。

*示例:* `Go FROMSEL NEW`
</td></tr><tr><td>
FTP</td><td>
/S</td><td>

*(无值)*</td><td>

显示 **[FTP 连接](/Manual/ftp/ftp_connect.zh.md)** 对话框，允许您与 FTP 站点进行临时连接。

*示例:* `Go FTP`
</td></tr><tr><td>
FTPCMD</td><td>
/K/R</td><td>

*\<命令\>*</td><td>

向远程 FTP 服务器发送原始命令（当前正在查看 FTP 目录时）。如果从未连接过 FTP 站点，则此命令不起作用。可在 [FTP 日志](/Manual/ftp/ftp_log.zh.md) 中查看命令的效果（如果有）。

*示例:* `Go FTPCMD chmod * 755`
</td></tr><tr><td>
FTPSITE</td><td>
/K</td><td>

*\<站点名称\>*</td><td>

连接 [FTP 地址簿](/Manual/ftp/ftp_address_book/README.zh.md) 中列出的 FTP 站点。必须按名称指定站点，如果该站点位于地址簿的子文件夹中，则必须包括该项的完整路径。**FTPSITE** 参数相当于在 **PATH** 参数中用 **@** 前缀站点项名称。

*示例:* `Go FTPSITE "Work Servers\Dallas\Production"`
</td></tr><tr><td>
FTPSITEICONS</td><td>
/S</td><td>

*(无值)*</td><td>

结合 **FTPSITELIST** 参数，为该命令生成的列表中的所有站点显示图标。

*示例:* `Go FTPSITELIST FTPSITEICONS`
</td></tr><tr><td>
FTPSITELIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示 [FTP 地址簿](/Manual/ftp/ftp_address_book/README.zh.md) 中的站点列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。

*示例:* `Go FTPSITELIST`
</td></tr><tr><td>
</td><td>
</td><td>

*\<站点前缀\>*</td><td>

从地址簿的指定子文件夹开始显示 FTP 站点列表。

*示例:* `Go FTPSITELIST "Work Servers"`
</td></tr><tr><td>
GROUPCOLLAPSE</td><td>
/K</td><td>

*\<组名称\>*</td><td>

当文件列表 [组合](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 时，此命令可用于折叠指定组。组名称必须完全匹配，但您还可以使用 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 来折叠所有与该模式匹配的组。

*示例:* `Go GROUPCOLLAPSE` \*
</td></tr><tr><td>
GROUPEXPAND</td><td>
/K</td><td>

*\<组名称\>*</td><td>

展开指定的文件组。组名称必须完全匹配，但您还可以使用 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 来展开所有与该模式匹配的组。

*示例:* `Go GROUPEXPAND` \*
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（参见 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表的开头添加一个小标题。当列表为空时，标题将被隐藏。标题仅适用于在与按钮同级的位置可能生成多个项目的命令。

当 **HEADING** 单独使用而不指定文本值时，将使用主按钮的标签文本作为标题。

*示例:* `Go DRIVEBUTTONS HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果您希望标题文本与按钮的标签不同，则可以指定它。

*示例:* `Go DRIVEBUTTONS HEADING="List of Drive Buttons"`
</td></tr><tr><td>
HISTORYLIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示历史记录列表的内容（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这是先前（**BACKLIST**）和后续（**FORWARDLIST**）文件夹的组合。

*示例:* `Go HISTORYLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

仅显示文件夹名称，而不显示完整路径。悬停在项目上时，工具提示将显示完整路径。

*示例:* `Go HISTORYLIST=namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**noicons**</td><td>

在生成的历史记录列表中不显示图标。

*示例:* `Go HISTORYLIST=noicons`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

将快捷键 **0** 到 **9** 分配给生成的历史记录列表中显示的前十个项目。

*示例:* `Go HISTORYLIST=noicons,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

按字母顺序而非按时间顺序排列历史记录列表。

*示例:* `Go HISTORYLIST=sort`
</td></tr><tr><td>
INITIALDIR</td><td>
/S</td><td>

*(无值)*</td><td>

将文件列表返回到它读取的第一个文件夹。

*示例:* `Go INITIALDIR`
</td></tr><tr><td>
KEYARGS</td><td>
/K/M</td><td>

*\<限定符:参数\> ...*</td><td>

提供了一种替代方式来根据按下的限定符键来修改 **Go** 命令的行为（而不是使用 **@keydown** [命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md)）。这是一个多值参数 - 对于列出的每个限定符键组合，您可以在运行命令并按住该键组合时定义一组单独的参数。

例如，您可以将一个 **Go** 按钮配置为在默认情况下在新标签页中打开文件夹，但如果按住 **Control** 键，则在新文件窗口中打开文件夹。

值的限定符部分由一个或更多代表限定符键的关键字组成 - **ctrl**、**shift** 和 **alt**。这些关键字可以组合起来，例如 **ctrlshift** 表示必须同时按住 **Control** 和 **Shift** 键。您还可以使用关键字 **none** 来表示按住无限定符时应用的参数。

*示例:* `Go FROMSEL KEYARGS "ctrl:NEW" "none:NEWTAB=findexisting"`
</td></tr><tr><td>
LASTACTIVELISTER</td><td>
/S</td><td>

*(无值)*</td><td>

将最近活动的文件窗口调到前面。如果当前没有有效的文件窗口打开，则将改为使用提供给该命令的任何其它参数。所以例如，您可以有一个全局热键，用于调出上一个文件窗口到前面，或在没有打开文件窗口时打开一个新文件窗口。

*示例:* `Go LASTACTIVELISTER NEW`
</td></tr><tr><td>
LASTCRUMB</td><td>
/S</td><td>

*(无值)*</td><td>

如果文件列表有一个与之关联的 [定位字段 breadcrumb](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md)，并且当前显示的是幻影路径，此命令将转到幻影路径中的最后一个“面包屑”。

*示例:* `Go LASTCRUMB`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

*\<布局名称\>*</td><td>

在新文件窗口中打开以指定 [布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 加载的文件夹。如果布局包含多个文件窗口，则仅使用第一个文件窗口。可以使用 **Go** 命令的其它参数来覆盖布局中的设置。
*\<name\>*</td><td>

通过 **REMEMBERTREEEXPANSION** 和 **RESTORETREEEXPANSION** 使用时，指定名称来保存或加载文件夹树扩展。

*示例:* `Go REMEMBERTREEEXPANSION NAME=CurrentJob`
</td></tr><tr><td>
NEW</td><td>
/O</td><td>

*(无值)*</td><td>

打开一个新的文件窗口。[默认文件窗口](/Manual/basic_concepts/the_lister/the_default_lister.zh.md) 设置被用于新打开的文件窗口，尽管 **Go** 命令的其它各种参数可以用于覆盖默认文件窗口的设置。

*示例:* `Go C:\ NEW`
</td></tr><tr><td>
</td><td>
</td><td>

*\<x\>,\<y\>,\<w\>,\<h\>*</td><td>

指定新文件窗口窗口的位置和大小。*\<x\>* 和 *\<y\>* 表示窗口的左上角坐标，*\<w\>* 和 *\<h\>* 分别表示宽度和高度。

*示例:* `Go NEW 240,300,640,480`
</td></tr><tr><td>
</td><td>
</td><td>

**max**</td><td>

最大化新文件窗口窗口。你可以使用 *\<x\>* 和 *\<y\>* 参数来控制窗口在其显示在其上的监视器上最大化。

*示例:* `Go NEW -1024,0,max`
</td></tr><tr><td>
</td><td>
</td><td>

**min**</td><td>

最小化新文件窗口窗口。如果指定了大小和位置，则它将在取消最小化（还原）文件窗口后表示还原后的位置。

*示例:* `Go NEW 1800,50,1024,768,min`
</td></tr><tr><td>
</td><td>
</td><td>

**norm**</td><td>

新文件窗口窗口既不最小化也不最大化。例如，如果默认文件窗口最大化，请使用此项来覆盖。

*示例:* `Go NEW norm`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

将新文件窗口设置为当前源。

*示例:* `Go FROMSEL NEW=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

将新文件窗口设置为目标。

*示例:* `Go C:\Backup NEW=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**lockoff**</td><td>

新文件窗口将被设置为“关闭” - 既不是 [源也不是目标](/Manual/basic_concepts/source_and_destination.zh.md)。

*示例:* `Go NEW=off`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

在新文件窗口中打开文件夹树。

*示例:* `Go C:\Windows NEW=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**notree**</td><td>

在新文件窗口中不打开文件夹树。

*示例:* `Go NEW=0,0,640,480,notree`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

在 [双屏幕](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式下打开新文件窗口，采用默认文件窗口的垂直或水平布局。
\`\`Go NEW=dual C:\ DUALPATH D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**dualhoriz**</td><td>

在双屏幕模式下打开新文件窗口，水平布局。

*示例:* `Go NEW=dualhoriz FROMSEL`
</td></tr><tr><td>
</td><td>
</td><td>

**dualvert**</td><td>

在 [双屏幕](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式下打开新文件窗口，垂直布局。
\`\`Go NEW=dualvert C:\ DUALPATH D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**nodual**</td><td>

在单屏幕模式下打开新文件窗口。

*示例:* `Go NEW=nodual`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

在新文件窗口中显示 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)。

*示例:* `Go NEW=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**noviewpane**</td><td>

在新文件窗口中不显示查看器窗格。

*示例:* `Go NEW=noviewpane,notree`
</td></tr><tr><td>
</td><td>
</td><td>

**findpanel**</td><td>

在新文件窗口中以查找文件模式显示 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。面板将以其简单或高级状态打开，具体取决于上次关闭面板时使用的状态。

*示例:* `Go CURRENT NEW=findpanel`
</td></tr><tr><td>
</td><td>
</td><td>

**findsimple**</td><td>

在新文件窗口中以查找文件（简单）模式显示 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。

*示例:* `Go CURRENT NEW=findsimple`
</td></tr><tr><td>
</td><td>
</td><td>

**findadvanced**</td><td>

在新文件窗口中以查找文件（高级）模式显示 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。

*示例:* `Go CURRENT NEW=findadvanced`
</td></tr><tr><td>
</td><td>
</td><td>

**syncpanel**</td><td>

在新文件窗口中以同步模式显示实用程序面板。

*示例:* `Go {sourcepath} DUALPATH {destpath} NEW=syncpanel`
</td></tr><tr><td>
</td><td>
</td><td>

**dupepanel**</td><td>

在新文件窗口中以重复文件查找器模式显示实用程序面板。

*示例:* `Go {sourcepath} NEW=dupepanel`
</td></tr><tr><td>
</td><td>
</td><td>

**noutilitypanel**</td><td>

在新文件窗口中不显示实用程序面板。

*示例:* `Go NEW=noutilitypanel`
</td></tr><tr><td>
</td><td>
</td><td>

**metapane**</td><td>

在新文件窗口中显示 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)。

*示例:* `Go NEW=metapane`
</td></tr><tr><td>
</td><td>
</td><td>

**nometapane**</td><td>

不显示元数据窗格。

*示例:* `Go NEW=nometapane,noutilitypanel,noviewpane,notree,nodual`
</td></tr><tr><td>
NEWTAB</td><td>
/O</td><td>

*(无值)*</td><td>

打开一个新的 [文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)。如果未指定路径（例如通过 **PATH** 参数），则会打开一个空白标签页，否则指定的路径将被加载到新标签页中。你可以使用 **TABPOS** 参数来控制新打开的标签页的位置。

*示例:* `Go C:\ NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**deflister**</td><td>

如果命令在没有文件窗口的情况下运行，则默认文件窗口将与指定文件夹的新标签页一起打开。如果文件窗口已存在，则指定文件夹的新标签页将正常打开在现有文件窗口中。

*示例:* `Go C:\ NEWTAB=deflister,findexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**findexisting**</td><td>

在现有标签页中查找指定路径。如果找到，则现有标签页将被置于顶层；否则将打开一个新标签页。首先会检查活动标签页，如果活动标签页已经显示指定路径，则将不执行任何操作。

*示例:* `Go CURRENT NEWTAB=findexisting OPENINDUAL`

在某些情况下，**findexisting** 是默认行为，**nofindexisting** 可用于取消它。
</td></tr><tr><td>
</td><td>
</td><td>

**findinactive**</td><td>

与 **findexisting** 相似，不同之处在于，如果活动标签页已经具有指定路径，则将打开一个新标签页。旨在针对切换到现有标签页的按钮使用，以减少混乱，同时保留在需要时为同一文件夹打开第二个标签页的能力。

*示例:* `Go "C:\Program Files" NEWTAB=findinactive`
</td></tr><tr><td>
</td><td>
</td><td>

**nofindexisting**</td><td>

明确取消了上面描述的 **findexisting** 行为。大多数命令的默认设置是不查找现有标签页，但有些命令（例如 <nobr>`Go OPENCONTAINER NEWTAB`</nobr>) 会查找现有标签页，除非明确告知不要这样做。
*示例：`Go OPENCONTAINER NEWTAB=nofindexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

新标签页不会设为活动。

*示例：`Go CURRENT NEWTAB=nofocus`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

将文件窗口置于前面。在其它窗口中打开标签页时非常有用。

*示例：`Go CURRENT NEWTAB=tofront OPENINDEST`
</td></tr><tr><td>
NEXTCRUMB</td><td>
/S</td><td>

*(无值)*</td><td>

如果文件列表区有一个与其关联的 [面包屑位置字段](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.zh.md)，且当前显示的是幽灵路径，此命令将会转到幽灵路径中的下一个“面包屑”。

*示例：`Go NEXTCRUMB`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(无值)*</td><td>

允许 [脚本](/Manual/scripting/README.zh.md) 运行 **Go** 命令，而不会触发其它脚本（或它自己）。添加 **NOSCRIPT** 参数会禁用 **[OnBeforeFolderChange](../../scripting_reference/scripting_events/onbeforefolderchange.zh.md)**、**[OnAfterFolderChange](../../scripting_reference/scripting_events/onafterfolderchange.zh.md)**、**[OnOpenTab](../../scripting_reference/scripting_events/onopentab.zh.md)** 和 **[OnOpenLister](../../scripting_reference/scripting_events/onopenlister.zh.md)** 事件，否则这些事件会因该命令而触发。
</td></tr><tr><td>
OPENCONTAINER</td><td>
/O</td><td>

*(无值)*</td><td>

打开所选项目的容器（父文件夹）。在普通文件夹中，它不太有用（因为所选项目的父级是您已经所在的文件夹），但在 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)、[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 和 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 中，它可以帮助您快速转到文件所在的实际文件夹。

当选择多个项目时，此命令也可使用，并且如果所选项目来自多个容器，则可能会打开多个窗口或标签页。

此命令用于默认的集合项目上下文菜单。

*示例：`Go OPENCONTAINER`

当与 **NEWTAB** 参数结合使用时，会自动搜索现有标签页，无需明确使用 **NEWTAB=findexisting**。如果您始终需要打开一个新标签页，忽略与同一文件夹相关的任何现有标签页，则可以使用 **NEWTAB=nofindexisting**。

*示例：`Go OPENCONTAINER NEWTAB=nofindexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**target**</td><td>

取消引用快捷方式或连接点。这类似于快捷方式在系统属性对话框中的“查找目标”按钮。当使用已选快捷方式运行此命令时，将加载包含快捷方式目标的文件夹，且目标本身将自动被选中（除非同时提供了 **noselect**；请参阅下方）。类似地，如果选择了连接点，您将转到其目标的父级且其目标将被选中。如果所选项目既不是快捷方式也不是连接点，则该命令的功能与未指定 **target** 的命令的功能相同。

*示例：`Go OPENCONTAINER=target NEW`
</td></tr><tr><td>
</td><td>
</td><td>

**noselect**</td><td>

通常情况下，会选择相关项目并使其在包含文件夹中可见。指定此参数可以防止选择，只打开包含文件夹。

*示例：`Go OPENCONTAINER=target,noselect NEWTAB`
</td></tr><tr><td>
OPENINDEST</td><td>
/S</td><td>

*(无值)*</td><td>

指定文件夹将被读入目标文件列表区。如果当前文件窗口不处于双显示模式，则可能意味着文件夹被读入另一个文件窗口。您可以将此与 **NEWTAB** 结合使用，以便在目标中打开标签页。

*示例：`Go CURRENT OPENINDEST`
</td></tr><tr><td>
OPENINDUAL</td><td>
/O</td><td>

*(无值)*</td><td>

指定文件夹将被读入双显示文件窗口的目标文件列表区。此参数与 **OPENINDEST** 的区别在于，如果文件窗口目前尚未处于该模式，它会强制将单显示文件窗口转为双显示模式。在这种情况下将使用默认布局（水平或垂直）。

*示例：`Go CURRENT OPENINDUAL`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

将双显示文件窗口的布局强制设为水平（一个显示区在另一个之上）。

*示例：`Go C:\Windows OPENINDUAL=horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

将布局强制设为垂直（并排显示）。

*示例：`Go CURRENT NEWTAB OPENINDUAL=vert`
</td></tr><tr><td>
OPENINLEFT</td><td>
/S</td><td>

*(无值)*</td><td>

将指定文件夹读入双显示文件窗口中的左手（或顶部）文件列表区。在单显示文件窗口中，此参数不起作用（文件夹将如常读入单一显示区）。

*示例：`Go {rightpath} OPENINLEFT`
</td></tr><tr><td>
OPENINRIGHT</td><td>
/O</td><td>

*(无值)*</td><td>

将指定文件夹读入双显示文件窗口中的右手（或底部）文件列表区。如果当前文件窗口尚未处于双显示模式，它将自动设为该模式。在这种情况下将使用默认布局（水平或垂直）。

*示例：`Go {leftpath} OPENINRIGHT`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

将双显示文件窗口的布局强制设为水平（一个显示区在另一个之上）。

*示例：`Go C:\Windows OPENINRIGHT=horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

将布局强制设为垂直（并排显示）。

*示例：`Go {leftpath} NEWTAB OPENINRIGHT=vert`
</td></tr><tr><td>
PATH</td><td>
</td><td>

*(无值)*</td><td>

指定要读取的路径（或与 **FOLDERCONTENT** 参数结合使用，指定要显示其内容的路径）。

Opus 支持多种格式的路径，例如：

- 绝对路径，如 *C:\Windows*
- 相对路径，如 ..\\.（从当前文件夹向上两级）
- 虚拟文件系统 [URL 样式路径](/Manual/basic_concepts/virtual_file_system/README.zh.md)（例如 *ftp://ftp.microsoft.com* 或 *lib://Documents*）
- FTP [通讯簿快捷方式](/Manual/ftp/ftp_paths.zh.md)（例如 *@MyFtpSite*）
- [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)，如 */mydocuments*
- 环境变量，如 *%USERPROFILE%*
- [外部控制代码](../external_control_codes/README.zh.md)，如 **{sourcepath}**
- 文件 URI，如 **[file:///C:/Temp](file:///C:/Temp)**。这是 **Go** 命令的默认参数，因此您无需指定 **PATH** 关键字。请记住，如果路径包含空格，则需要用引号引起来。

*示例：`Go "C:\Program Files\GPSoftware\Directory Opus"`
</td></tr><tr><td>
PATHENTRY</td><td>
/O</td><td>

*(无值)*</td><td>

以允许您在当前文件列表区导航到其它文件夹的特殊模式（“转到”模式）显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段。此命令等效于 **[CLI](cli.zh.md) QUICKGO**。
*示例：* `Go PATHENTRY`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

"Go" 字段将作用于目标文件列表而不是源文件列表。请注意，它仍然会显示在源文件列表的底部，但一旦按 **Enter**，文件夹将被读入目标文件夹。

*示例：* `Go PATHENTRY=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

"Go" 字段将作用于左文件列表，无论是源文件还是目标文件。

*示例：* `Go PATHENTRY=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

"Go" 字段将作用于右文件列表。

*示例：* `Go PATHENTRY=right`
</td></tr><tr><td>
REBUILDTREE</td><td>
/O</td><td>

*(无值)*</td><td>

重新构建附加到源文件列表的文件夹树内容。这相当于关闭树然后再重新打开。

*示例：* `Go REBUILDTREE`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

重新构建附加到目标文件列表的文件夹树（当启用双树时）。

*示例：* `Go REBUILDTREE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

重新构建附加到左/上方文件列表的文件夹树。

*示例：* `Go REBUILDTREE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

重新构建附加到右/下方文件列表的文件夹树（当启用双树时）。

*示例：* `Go REBUILDTREE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

重新构建两个文件夹树（或单一树，以适用的为准）。

*示例：* `Go REBUILDTREE=both`
</td></tr><tr><td>
REFRESH</td><td>
/O</td><td>

*(无值)*</td><td>

刷新源文件列表中当前文件夹的显示。

*示例：* `Go REFRESH`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

刷新文件夹树。

*示例：* `Go REFRESH=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

在双显示文件窗口中刷新两个文件列表。

*示例：* `Go REFRESH=both`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

刷新两个文件列表和文件夹树。

*示例：* `Go REFRESH=all`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

刷新源文件列表及其树。

*示例：* `Go REFRESH=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

刷新目标文件列表及其树。

*示例：* `Go REFRESH=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

刷新 [查看窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)。窗格中当前显示的图像或文件将被重新加载。

*示例：* `Go REFRESH=viewpane`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

刷新左文件列表。

*示例：* `Go REFRESH=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

刷新右文件列表。

*示例：* `Go REFRESH=right`
</td></tr><tr><td>
REFRESHTHUMBS</td><td>
/O</td><td>

*(无值)*</td><td>

刷新当前文件夹中显示的缩略图。如果启用缩略图缓存，则会清除当前文件夹的缓存，强制重新生成缩略图。

*示例：* `Go REFRESHTHUMBS`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

仅按住 **Shift** 键时刷新缩略图。这使您可以将普通文件夹刷新与一个命令上的缩略图刷新结合使用——默认情况下，它可以执行普通文件夹刷新，还可以按住 **Shift** 键强制重新生成缩略图。

*示例：* `Go REFRESH REFRESHTHUMBS=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

仅按住 **Alt** 键时刷新缩略图。

*示例：* `Go REFRESHTHUMBS=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

仅按住 **Control** 键时刷新缩略图。

*示例：* `Go REFRESHTHUMBS=ctrl REFRESH=all`
</td></tr><tr><td>
REMEMBERTREEEXPANSION</td><td>
/O</td><td>

*(无值)*</td><td>

记住源文件夹树的当前展开状态。一旦记住状态，您可以使用 **RESTORETREEEXPANSION** 在稍后还原。

默认情况下，展开状态仅在文件窗口的生命周期内被记住。如果与 **NAME** 参数一起使用，则展开将在该名称下保存，并且可以在将来的任何时间还原。

*示例：* `Go REMEMBERTREEEXPANSION`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

记住附加到目标文件列表的文件夹树的展开状态（当启用双树时）。

*示例：* `Go REMEMBERTREEEXPANSION=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

记住附加到左/上方文件列表的文件夹树的展开状态。

*示例：* `Go REMEMBERTREEEXPANSION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

记住附加到右/下方文件列表的文件夹树的展开状态（当启用双树时）。

*示例：* `Go REMEMBERTREEEXPANSION=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

记住两个文件夹树（或单一树，以适用的为准）的展开状态。

*示例：* `Go REMEMBERTREEEXPANSION=both`
</td></tr><tr><td>
RESTORETREEEXPANSION</td><td>
/O</td><td>

*(无值)*</td><td>

还原先前使用 **REMEMBERTREEEXPANSION** 记住的源文件夹树的展开状态。

与 **NAME** 参数结合使用以还原已保存的展开。

*示例：* `Go RESTORETREEEXPANSION NAME=CurrentJob`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

还原附加到目标文件列表的文件夹树的展开状态（当启用双树时）。

*示例：* `Go RESTORETREEEXPANSION=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

还原附加到左/上方文件列表的文件夹树的展开状态。

*示例：* `Go RESTORETREEEXPANSION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

还原附加到右/下方文件列表的文件夹树的展开状态（当启用双树时）。

*示例：* `Go RESTORETREEEXPANSION=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

还原两个文件夹树（或单一树，以适用的为准）的展开状态。

*示例：* `Go RESTORETREEEXPANSION=both`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

将树的展开重置为其初始状态。可以与上述关键字结合使用。

*示例：* `Go RESTORETREEEXPANSION=both,reset`
</td></tr><tr><td>
ROOT</td><td>
/O</td><td>

*(无值)*</td><td>

导航到当前文件夹的根目录。例如，*C:\Program Files\GPSoftware\Directory Opus* 的根目录为 *C:*.

*示例：* `Go ROOT`
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

在导航到根文件夹的同时折叠文件夹树中当前驱动器的分支。

*示例：* `Go ROOT=collapse`
</td></tr><tr><td>
RUNEMBEDDEDIFNOTFOUND</td><td>
/S</td><td>

*(无值)*</td><td>

此参数用于将函数 [嵌入](/Manual/customize/creating_your_own_buttons/embedded_functions.zh.md) 到 **Go FINDTITLE** 命令中。通常，如果不存在与提供的字符串匹配的文件窗口，则不会运行嵌入函数。如果指定了 **RUNEMBEDDEDIFNOTFOUND** 参数，则未找到匹配的文件窗口时，将在当前文件窗口中运行嵌入命令。
*示例：*

`Go FINDTITLE PhotoWork RUNEMBEDDEDIFNOTFOUND
[Set VIEW=Thumbnails]
`
</td></tr><tr><td>
SWAP</td><td>
/S</td><td>

*(无值)*</td><td>

交换在源文件列表和目标文件列表中显示的文件夹。

*示例：*`Go SWAP`
</td></tr><tr><td>
SWITCHPATH</td><td>
/K/M</td><td>

*\<其它路径\> ...*</td><td>

在两个或更多路径间切换（或循环）。**PATH** 参数用于提供序列中的第一个路径，然后 **SWITCHPATH** 参数提供第二个和后续的路径。运行此命令时，Opus 会查看在源文件列表中显示的当前路径。如果它匹配 provided paths 中的一个，则会读取序列中的下一个路径（然后再读下一个、再下一个，如此类推）。如果当前路径不匹配 provided paths 中的任何一个，则会读取序列中的第一个路径。

\`\`Go C:\ SWITCHPATH D:\ E:\ F:\ G:\\\`
</td></tr><tr><td>
TABCLOSE</td><td>
/O</td><td>

*(无值)*</td><td>

关闭源文件列表中的当前 [文件夹标签](/Manual/basic_concepts/the_lister/tabs/README.zh.md)。

你可以在此中结合使用 **PATH** 参数以指定应关闭的标签的路径。当在此上下文中使用时，**PATH** 参数可以接受通配符 - 与所提供的模式匹配的所有标签都会被关闭。

**TABPOS** 参数用于指定要关闭的特定标签（从 0 开始编号）的 index，或相对于当前标签的位置，或第一个或最后一个标签的位置。（**PATH** 参数也可以指定一个特定的 tab index，但此用法已弃用，改用 **TABPOS**。）

*示例：* 关闭当前标签：`Go TABCLOSE`
关闭显示在 C: 驱动器上的所有标签：`Go TABCLOSE PATH=C:*`
关闭第一个标签：`Go TABCLOSE TABPOS=first`
关闭最后一个标签：`Go TABCLOSE TABPOS=last`
关闭位于当前标签后的标签：`Go TABCLOSE TABPOS=+1`
关闭位于当前标签前的标签：`Go TABCLOSE TABPOS=-1`

当从 [脚本](/Manual/scripting/README.zh.md) 使用时，你可以传递 **[Tab](../../scripting_reference/scripting_objects/tab.zh.md)** 对象的默认值以指定要关闭的标签。

*示例：* `Go TABCLOSE=\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

关闭左（或上）文件列表中的文件夹标签，无论它是否是源。

*示例:* `Go TABCLOSE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

关闭右（或下）文件列表中的文件夹标签。

*示例:* `Go TABCLOSE=right TABPOS=-2`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

关闭目标文件列表中的文件夹标签。

\`\`Go TABCLOSE=dest PATH=C:\\\`\*
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

即使文件夹标签被锁定且在配置中禁用关闭单个锁定标签，也要关闭文件夹标签。

*示例:* `Go TABCLOSE=force`

*示例:* `Go TABCLOSE=dest,force`
</td></tr><tr><td>
TABCLOSEALL</td><td>
/O</td><td>

*(无值)*</td><td>

关闭除当前标签外的所有文件夹标签。

当与 **TABGROUPLOAD** 命令结合使用时，这将覆盖标签组的 *关闭现有文件夹标签* 设置，并强制关闭现有标签。

*示例:* `Go TABCLOSEALL`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

关闭当前标签左侧的所有文件夹标签。

*示例:* `Go TABCLOSEALL=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

关闭当前标签右侧的所有文件夹标签。

*示例:* `Go TABCLOSEALL=right`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

让你可以在双显示文件窗口中关闭目标文件列表中的标签。

*示例:* `Go TABCLOSEALL=dest,right`
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

强制关闭锁定标签。通常情况下，此命令不会关闭锁定标签。

*示例:* `Go TABCLOSEALL=right,force`
</td></tr><tr><td>
</td><td>
</td><td>

**expand**</td><td>

将标签展开为文件窗口. 标签将在当前文件窗口中关闭，而每个文件夹都将作为一个新文件窗口打开。

*示例:* `Go TABCLOSEALL=right,expand`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

当与 **TABGROUPLOAD** 命令结合使用时，这将覆盖标签组的 *关闭现有文件夹标签* 设置，并强制保留现有标签。

当不与 **TABGROUPLOAD** 结合使用时，此值没有意义。

*示例:* `Go TABGROUPLOAD=MyTabs TABCLOSEALL=no`
</td></tr><tr><td>
TABCOLOR</td><td>
/K</td><td>

*\<颜色\>*</td><td>

为当前标签分配自定颜色。你可以用十进制形式 R、G、B（例如 127、192、55）或十六进制形式 #RRGGBB（例如 #ff0033）指定颜色。

*示例:* `Go TABCOLOR \#ff8000`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

重置当前标签的颜色。

*示例:* `Go TABCOLOR=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**edit**</td><td>

启动对当前标签颜色进行编辑。你可以使用 **PATH** 参数指定要编辑的标签的 index（最左边的为 index #0）。

*示例:* `Go TABCOLOR=edit`
</td></tr><tr><td>
TABDUPLICATE</td><td>
/O</td><td>

*(无值)*</td><td>

复制当前文件夹标签。

*示例:* `Go TABDUPLICATE`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

在双显示文件窗口的另一个文件列表中创建当前文件夹标签的副本。

*示例:* `Go TABDUPLICATE=dual`
</td></tr><tr><td>
TABFINDEXISTING</td><td>
/S</td><td>

*(无值)*</td><td>

如果在另一个标签中打开了指定文件夹，Opus 将切换到该标签，否则将文件夹读入当前标签。启用与 **NEWTAB=findexisting** 参数类似的行为，但不找到路径时不会打开新标签。

*示例:* `Go /mydocuments TABFINDEXISTING`
</td></tr><tr><td>
TABGROUPFORCE</td><td>
/S</td><td>

*(无值)*</td><td>

与 **TABGROUPLOAD** 或 **TABGROUPLIST** 参数结合使用以强制加载标签中的文件夹，即使它们通常会因配置中 [自动读取](/Manual/preferences/preferences_categories/folders/automatic_reading.zh.md) 页上的自动加载设置而被阻止。

*示例:* `Go TABGROUPLOAD “My Tab Group” TABGROUPFORCE`
</td></tr><tr><td>
TABGROUPLIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示你保存的 [文件夹标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 的列表（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从列表中选择一个组将在当前文件列表中打开这些标签。

此参数在与 **USEQUALKEYS**、**TABGROUPFORCE** 和 **KEYARGS** 参数结合使用时有效。

*示例:* `Go TABGROUPLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

为生成标签组列表上显示的第一个十项分配快捷键 **0** 至 **9**。

*示例:* `Go TABGROUPLIST=keys USEQUALKEYS`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

在生成标签组列表上显示项目的图标。

*示例:* `Go TABGROUPLIST=keys,icons`
</td></tr><tr><td>
</td><td>
</td><td>

**nohighlight**</td><td>

防止活动标签页组高亮显示。

*示例:* `Go TABGROUPLIST=icons,nohighlight`
</td></tr><tr><td>
</td><td>
</td><td>

**savecurrent**</td><td>

在加载新建标签页组之前保存当前文件夹标签页组（如有）。如果没有此参数，加载其它标签页组时对标签页组的任何更改都将会丢失，除非你明确保存这些更改。

在特殊情况下，单击当前标签页组的按钮将重新加载该组而无须先覆盖，从而使你可以复原到该组上一次保存的状态。

如果当前未加载任何标签页组，则在加载新建标签页组之前不会保存任何内容。

*示例:* `Go TABGROUPLIST=savecurrent`

请注意，如果你希望 Opus 以这种方式自动保存标签页组，你可能还需要添加一些内容，以便在列表关闭时或在其它事件（如打开/关闭标签页或更改文件夹）时触发 **Go TABGROUPSAVE=!current,!quiet**，具体取决于你希望在何时更新标签页组。这可能仅在只使用一个列表的情况下有意义，因为多个列表可能对当前打开的组有不同的视图，并且会相互覆盖。但是，如果你希望自动保存标签页组，你可能已经在始终使用单窗口，因为其它人会为独立的标签页组使用独立的窗口，并在窗口之间切换，而不是在单窗口中切换组。
</td></tr><tr><td>
TABGROUPLOAD</td><td>
/K</td><td>

*\<组名称\>*</td><td>

加载已命名的文件夹标签页组。这可以与 **OPENINDUAL** 等结合，以便在另一个文件列表中打开标签页组。你还可以结合 **TABCLOSEALL** 参数，以覆盖标签页组的 *关闭现有文件夹标签页* 设置。

*示例:* `Go TABGROUPLOAD "My Tab Group" TABCLOSEALL=no`
</td></tr><tr><td>
TABGROUPSAVE</td><td>
/O</td><td>

*(无值)*</td><td>

将当前文件夹标签页组另存为一个新标签页组。系统将提示你为该组提供一个名称。

*示例:* `Go TABGROUPSAVE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<组名称\>*</td><td>

使用指定组名称保存当前文件夹标签页组。

*示例:* `Go TABGROUPSAVE "My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!both**</td><td>

在双显示列表中，这将使用“特定端”选项将两个文件列表中的标签页保存到单个组中。你还可以通过在关键字后加逗号指定组名称。（如果有的话，组名称必须在关键字后，而不能在关键字之前。）

*示例:* `Go TABGROUPSAVE="!both,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!closeall**</td><td>

保存标签页组，以便在加载它时关闭所有现有标签页（除非在加载时覆盖）。如果没有指定 **!closeall** 或 **!nocloseall**，覆盖现有组将保留其模式，默认情况下，非交互方式创建的新组将关闭现有标签页，而交互方式创建的新组将默认为上次显示交互对话框时使用的模式。（如果有的话，组名称必须在关键字后，而不能在关键字之前。）

*示例:* `Go TABGROUPSAVE="!both,!closeall,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!nocloseall**</td><td>

保存标签页组，以便在加载它时不关闭任何现有标签页（除非在加载时覆盖）。有关更多信息，请参见上面的 **!closeall**。（如果有的话，组名称必须在关键字后，而不能在关键字之前。）

*示例:* `Go TABGROUPSAVE="!both,!nocloseall,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!current**</td><td>

覆盖上一次加载的文件夹标签页组。忽略 **!both** 关键字，相反，模式从现有组中继承。添加 **!quiet** 关键字，以使命令在没有当前标签页组要覆盖的情况下不执行任何操作；否则，在这种情况中，系统将提示你输入新组的名称。

*示例:* `Go TABGROUPSAVE="!current"`
</td></tr><tr><td>
</td><td>
</td><td>

**!quiet**</td><td>

将 **!quiet** 与 **!current** 结合使用，以防止在没有标签页组要覆盖的情况下系统要求你命名一个新标签页组。

*示例:* `Go TABGROUPSAVE="!current,!quiet"`
</td></tr><tr><td>
</td><td>
</td><td>

**!unless**</td><td>

将 **!unless** 与 **!current** 结合使用，以告诉命令保存当前组，除非它具有特定名称。你可能不需要直接使用此参数，但它是 **Go TABGROUPLIST=savecurrent** 命令避免在单击其按钮重新加载它时覆盖当前组的方式。

*示例:* `Go TABGROUPSAVE="!current,!quiet,!unless,My Tab Group"`
</td></tr><tr><td>
</td><td>
</td><td>

**!forget**</td><td>

告诉文件列表忘记其加载的最后一个标签页组的名称。与 **!both** 结合使用，以使双显示列表的两个端都忘记。如果你加载一个标签页组，然后对其进行修改，以至于它不再与原始组有任何联系，并且你不希望它在任何标签页组列表中保持选中状态，你可能希望使用此参数。

*示例:* `Go TABGROUPSAVE="!forget"`
</td></tr><tr><td>
TABLINK</td><td>
/K</td><td>

**on**</td><td>

在双显示列表中，将源文件列表中的当前活动标签页与目标文件列表中的当前活动标签页相链接。

*示例:* `Go TABLINK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

如果当前活动标签页已链接，这将取消链接。

*示例:* `Go TABLINK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在左右两个文件列表中，为当前活动标签页切换启用或禁用标签页链接。

*示例:* `Go TABLINK=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**navlock**</td><td>

与 **on** 或 **toggle** 结合使用，以指定标签页应在 [导航锁定](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.zh.md) 模式下链接（以便在更改文件夹时它会跟随另一个标签页）。

*示例:* `Go TABLINK=toggle,navlock`
</td></tr><tr><td>
</td><td>
</td><td>
reset</td><td>

当两个标签页在导航锁定模式下链接时，reset 关键字让你可以将同步位置复原到当前位置（用于在它们不同步时恢复）。

*示例:* `Go TABLINK=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**unlinkall**</td><td>

取消链接当前列表中的所有链接标签页。

*示例:* `Go TABLINK=unlinkall`
</td></tr><tr><td>
</td><td>
</td><td>

*\<tab1\>,\<tab2\>*</td><td>

当从 [脚本](/Manual/scripting/README.zh.md) 中使用时，你可以传递两个 **[标签页](../../scripting_reference/scripting_objects/tab.zh.md)** 对象的默认值，以指定你要链接的准确标签页。这两个值必须用逗号分隔。如果只指定了一个 **[标签页](../../scripting_reference/scripting_objects/tab.zh.md)** 对象，则会取消其链接（如果当前已链接）。

*示例:* `Go TABLINK=\<tab1\>,\<tab2\>,navlock`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

生成标准标签页链接菜单。此菜单包含在默认文件夹标签页 [上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md) 中。
*Example:* `Go TABLINK=menu`
</td></tr><tr><td>
TABLIST</td><td>
/O</td><td>

*(no value)*</td><td>

显示当前打开的文件夹标签列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从列表中选择标签将切换到该标签。您还可以将文件拖放到列表中的项目，将它们复制到该标签的文件夹中。

默认情况下，显示的标签来自当前源文件列表，但您可以与 **OPENINLEFT**、**OPENINRIGHT** 和 **OPENINDEST** 自变量结合使用，以显示来自其它文件列表的标签。

*Example:* `Go TABLIST`
</td></tr><tr><td>
</td><td>
</td><td>

**keys**</td><td>

将快捷键 **0** 到 **9** 分配给在生成的标签列表中显示的前十项。

*Example:* `Go TABLIST=keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sort**</td><td>

按字母顺序对标签列表进行排序（如果不进行此操作，列表中的项目将以与物理标签相同的顺序列出）。排序顺序基于文件夹名称（或标签标签）。

*Example:* `Go TABLIST=sort,keys`
</td></tr><tr><td>
</td><td>
</td><td>

**sortpath**</td><td>

根据每个文件夹的完整路径，按字母顺序对标签列表进行排序。

*Example:* `Go TABLIST=sortpath`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

为列表中的每个标签显示文件夹图标。

*Example:* `Go TABLIST=sortpath,icons`
</td></tr><tr><td>
</td><td>
</td><td>

**namesonly**</td><td>

仅显示每个标签的文件夹名称，而不是完整路径。不影响使用自定义标签的标签；自定义标签始终按原样显示。

*Example:* `Go TABLIST=sort,namesonly`
</td></tr><tr><td>
</td><td>
</td><td>

**maxwidth=***\<width\>*</td><td>

为列表中的每个项目指定最大宽度（以字符为单位）。在显示每个标签的完整路径时，您可能希望使用此项来防止标签列表过宽。如果没有指定，则默认使用 50 的最大宽度——您可以通过指定 **maxwidth=0** 来禁用此项（并且完全没有最大宽度）。

请注意，由于此参数需要等号，因此您必须用引号将 **TABLIST** 自变量的整个值括起来。

*Example:* `Go TABLIST="keys,maxwidth=70"`
</td></tr><tr><td>
TABLOCK</td><td>
/K</td><td>

**lock**</td><td>

锁定当前 [文件夹标签](/Manual/basic_concepts/the_lister/tabs/README.zh.md)，以防止任何文件夹更改。尝试更改文件夹将导致创建新标签。

*Example:* `Go TABLOCK=lock`
</td></tr><tr><td>
</td><td>
</td><td>

**lockchanges**</td><td>

锁定当前标签。允许更改文件夹，但如果单击标签或将焦点从另一个标签移到此标签，该标签将恢复到其原始（已锁定）目录。您还可以使用命令 **Go TABLOCKDIR** 返回原始目录。

*Example:* `Go TABLOCK=lockchanges`
</td></tr><tr><td>
</td><td>
</td><td>

**lockreuse**</td><td>

锁定当前标签。尝试更改文件夹将导致使用第一个已存在的未锁定标签读取新目录。如果找不到可用的未锁定标签，将打开一个新标签。

*Example:* `Go TABLOCK=lockreuse`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

解锁当前文件夹标签。

*Example:* `Go TABLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

与各种 **lock** 关键字结合使用，以切换该锁定模式的开关。

*Example:* `Go TABLOCK=lockchanges,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

锁定或解锁所有文件夹标签。

*Example:* `Go TABLOCK=lock,all`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

锁定或解锁当前标签左侧的所有标签。

*Example:* `Go TABLOCK=lockchanges,toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

锁定或解锁当前标签右侧的所有标签。

*Example:* `Go TABLOCK=off,right`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

生成标准标签锁定菜单。此菜单包含在默认文件夹标签 [上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md) 中。

*Example:* `Go TABLOCK=menu`
</td></tr><tr><td>
TABLOCKDIR</td><td>
/S</td><td>

*(no value)*</td><td>

指示当前文件夹标签的原始（已锁定）目录。这是标签在设置为“允许更改锁定”模式时在标签中显示的目录。您可以使用此选项返回锁定文件夹，或在另一个标签或文件窗口中打开该文件夹。如果当前标签未锁定，则此自变量的行为与 **CURRENT** 自变量相同。

*Example:* `Go TABLOCKDIR`
</td></tr><tr><td>
TABMOVE</td><td>
/O</td><td>

*(no value)*</td><td>

将当前文件夹标签移动到其它文件列表。（有关在不更改侧面的情况下重新定位标签，请参见 **TABPOS**。）如果文件窗口尚未处于该模式，则将设置文件窗口为双显示模式。

*Example:* `Go TABMOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**split**</td><td>

拆分当前在单显示文件窗口中打开的文件夹标签。文件窗口将设置为双显示模式，并将从当前标签开始的所有标签移至另一个显示。如果文件窗口已经处于双显示模式，则此命令无效。

*Example:* `Go TABMOVE=split`
</td></tr><tr><td>
</td><td>
</td><td>

**splitlister**</td><td>

将当前文件列表中的文件夹标签拆分为新的文件窗口。从当前标签开始的所有标签都将在当前显示中关闭，并在新的文件窗口中重新打开。

*Example:* `Go TABMOVE=splitlister`
</td></tr><tr><td>
</td><td>
</td><td>

*\<new position\>*</td><td>

指定移动标签的新位置。您可以指定一个绝对位置、**-1** 表示相同的相对位置、和 **-2** 将移动标签定位到当前活动标签的右侧。如果未指定，则移动的标签将定位在所有现有标签的末尾。

*Example:* `Go TABMOVE=-2`
</td></tr><tr><td>
</td><td>
</td><td>

**active**</td><td>

如果指定了，则移动标签将变为活动标签。否则，其它文件列表中以前活动的标签仍然保持活动状态。

*Example:* `Go TABMOVE=active,-2`
</td></tr><tr><td>
TABNAME</td><td>
/O</td><td>

*(no value)*</td><td>

如果已分配当前标签名称，则清除该名称。这会将标签标签重置为默认值，即显示当前文件夹的名称。

*Example:* `Go TABNAME`
</td></tr><tr><td>
</td><td>
</td><td>

\<*tab name*\></td><td>

将指定的名称分配给当前标签。如果与 **NEWTAB** 自变量组合使用，该名称将分配给新创建的标签。

*Example:* `Go C:\Work NEWTAB TABNAME "My Work Dir"`

您可以在标签名称中使用几个特殊的“标记”来插入各种信息：

|        |                                           |
|--------|-------------------------------------------|
| **%P** | 当前（源）文件夹的完整路径              |
| **%N** | 当前（源）文件夹的名称                     |
| **%R** | 当前（源）文件夹的驱动器根目录         |
| **%!** | 隐藏节                                    |
**%!** 代码允许您隐藏字符串中所有其它标记为空的部分。

*示例：* `Go TABNAME "%!驱动器 %R ： %!%N"`

这意味着，如果 **%R** 标记为空字符串，结果将仅仅是 "%N"（文件夹的名称）。
</td></tr><tr><td>
</td><td>
</td><td>

**!edit**</td><td>

发起当前标签名称的编辑。您可以使用 **PATH** 参数指定要编辑的标签索引（最左边的索引为 \#0）。

*示例：* `Go TABNAME=!edit`
</td></tr><tr><td>
TABPOS</td><td>
/K</td><td>

**first**</td><td>

当与 **NEWTAB** 参数结合使用时，将新创建的标签显示在标签栏的第一个位置。当与 **TABCLOSE** 结合使用时，关闭第一个标签。当单独使用时，重新定位活动文件夹标签，使其成为标签栏上的第一个标签。

*示例：* `Go C:\ NEWTAB TABPOS=first`

当从 [脚本](/Manual/scripting/README.zh.md) 中使用时，您可以传递 **[Tab](../../scripting_reference/scripting_objects/tab.zh.md)** 对象的默认值，以指定您希望作为第二个参数重新定位的标签。

*示例：* `Go TABPOS=first,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**last**</td><td>

当与 **NEWTAB** 参数结合使用时，将新创建的标签显示在标签栏的最后一个位置。当与 **TABCLOSE** 结合使用时，关闭最后一个标签。当单独使用时，重新定位活动文件夹标签，使其成为标签栏上的最后一个标签。

*示例：* `Go TABPOS=last`

当从 [脚本](/Manual/scripting/README.zh.md) 中使用时，您可以传递 **[Tab](../../scripting_reference/scripting_objects/tab.zh.md)** 对象的默认值，以指定您希望作为第二个参数重新定位的标签。

*示例：* `Go TABPOS=last,\<tab\>`
</td></tr><tr><td>
</td><td>
</td><td>

**+1**</td><td>

当与 **NEWTAB** 参数结合使用时，将新创建的标签显示在当前活动标签的右侧。当与 **TABCLOSE** 结合使用时，关闭活动标签右侧的标签。当单独使用时，重新定位活动文件夹标签，使其位于标签栏上当前位置的右侧。您还可以使用 +2 向右移动两个位置，依此类推。

*示例：* `Go
|        |                                                                       |
|--------|-----------------------------------------------------------------------|
| **%P** | 当前（源）文件夹的全路径                                             |
| **%N** | 当前（源）文件夹的名称                                               |
| **%R** | 当前（源）文件夹的驱动器根目录                                     |
| **%D** | 目标文件夹的全路径                                                 |
| **%M** | 目标文件夹的名称                                                    |
| **%G** | 如果文件夹是一个交界处或软链接，则为目标                         |
| **%1** | 左侧文件列表中的全路径                                              |
| **%2** | 右侧文件列表中的全路径                                             |
| **%3** | 左侧文件列表中的文件夹名称                                          |
| **%4** | 右侧文件列表中的文件夹名称                                         |
| **%L** | 该文件窗口来自的布局的名称（如果有）                                 |
| **%S** | 在文件窗口中选择的当前样式的名称（如果有）                            |
| **%T** | 完整的原始标题（仅用于添加前缀或后缀）                           |
| **%!** | 隐藏部分                                                          |

*示例:* `Go NEW TITLE "Directory Opus - %N"`

**%!** 代码允许你在部分中隐藏字符串，其中部分内的所有其它标记都是空的。

*示例:* `Go NEW TITLE "%!%T - %!Directory Opus"`

这意味着如果 **%T** 标记扩展为空字符串，则结果将恰好是 "Directory Opus"，而不是 "- Directory Opus"。
</td></tr><tr><td>
TOFRONT</td><td>
/S</td><td>

*(无值)*</td><td>

使文件窗口成为活动窗口，并将其置于前面。通常在从 Opus 外部发送命令时使用，以确保读取文件夹的窗口可见。

*示例:* `Go C:\ TOFRONT`
</td></tr><tr><td>
TREECOLLAPSE</td><td>
/O</td><td>

*(无值)*</td><td>

折叠属于源文件列表的树中选定的分支。

*示例:* `Go TREECOLLAPSE`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

折叠属于目标文件列表的树中选定的分支（启用双树时）。

*示例:* `Go TREECOLLAPSE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

折叠左侧/顶部文件列表中选定的分支。

*示例:* `Go TREECOLLAPSE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

折叠右侧/底部文件列表中选定的分支（启用双树时）。

*示例:* `Go TREECOLLAPSE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

折叠源树和目标树中选定的分支。

*示例:* `Go TREECOLLAPSE=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

折叠当前具有输入焦点（或属于具有输入焦点的文件列表的树）的树中选定的分支。

*示例:* `Go TREECOLLAPSE=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

折叠选定文件夹下的所有文件夹（及其所有子文件夹，依此类推），而不仅仅是选定的文件夹。

*示例:* `Go TREECOLLAPSE=all,both`
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

仅折叠选定文件夹下的后代的第一级。

*示例:* `Go TREECOLLAPSE=left,first`
</td></tr><tr><td>
</td><td>
</td><td>

**second**</td><td>

折叠选定文件夹下的第一级和第二级后代。

*示例:* `Go TREECOLLAPSE=second`
</td></tr><tr><td>
TREEEXPAND</td><td>
/O</td><td>

*(无值)*</td><td>

当与读取文件夹结合使用时，此命令会自动展开文件夹树以显示新文件夹的内容。只有当 **[文件夹树/展开/折叠](/Manual/preferences/preferences_categories/folder_tree/expand_collapse/README.zh.md)** 配置页面上的 **自动展开到当前文件夹** 选项已关闭时，此选项才有用。

你还可以单独使用此命令来展开当前选定的文件夹。

*示例:* `Go "C:\Program Files\GPSoftware\Directory Opus" NEW TREEEXPAND`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

展开属于目标文件列表的树中选定的分支（启用双树时）。

*示例:* `Go TREEEXPAND=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

展开左侧/顶部文件列表中选定的分支。

*示例:* `Go TREEEXPAND=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

展开右侧/底部文件列表中选定的分支（启用双树时）。

*示例:* `Go TREEEXPAND=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

展开源树和目标树中选定的分支。

*示例:* `Go TREEEXPAND=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

展开当前具有输入焦点（或属于具有输入焦点的文件列表的树）的树中选定的分支。

*示例:* `Go TREEEXPAND=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

展开选定文件夹下的所有文件夹（及其所有子文件夹，依此类推），而不仅仅是选定的文件夹。

*示例:* `Go TREEEXPAND=all,both`
</td></tr><tr><td>
</td><td>
</td><td>

**first**</td><td>

仅展开选定文件夹下的后代的第一级。

*示例:* `Go TREEEXPAND=left,first`
</td></tr><tr><td>
</td><td>
</td><td>

**second**</td><td>

展开选定文件夹下的第一级和第二级后代。

*示例:* `Go TREEEXPAND=second`
</td></tr><tr><td>
TREESETPINSTATE</td><td>
/O</td><td>

*(无值)*</td><td>

切换 [文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md) 中当前选定文件夹的“固定”状态。已固定的文件夹始终保持展开状态 - 它们无法折叠。请注意，必须从配置中的 [固定](/Manual/preferences/preferences_categories/folder_tree/expand_collapse/pins.zh.md) 页面启用文件夹固定才能使此命令生效。

*示例:* `Go TREESETPINSTATE`
</td></tr><tr><td>
</td><td>
</td><td>

**on**</td><td>

启用当前选定文件夹的“固定”状态。

*示例:* `Go TREESETPINSTATE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前选定文件夹的“固定”状态。

*示例:* `Go TREESETPINSTATE=off`
</td></tr><tr><td>
UNDOCLOSELISTER</td><td>
/O</td><td>

*(无值)*</td><td>

重新打开上次关闭的文件窗口（例如，如果你不小心关闭了你正在使用的文件窗口，此命令就会将其重新打开）。

*示例:* `Go UNDOCLOSELISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**closeexisting**</td><td>

重新打开上次关闭的文件窗口，并关闭所有其它打开的文件窗口。

*示例:* `Go UNDOCLOSELISTER=closeexisting`
</td></tr><tr><td>
UP</td><td>
/S</td><td>

*(无值)*</td><td>

[向上](/Manual/basic_concepts/the_lister/navigation/up_forwards_back.zh.md) 导航到当前文件夹的父文件夹。你可以将此与 **OPENINDUAL** 等结合使用，在另一个文件列表或文件窗口中打开当前文件夹的父文件夹。这还可以与 **BACK** 参数结合使用 - 在这种情况下，如果当前文件夹的父文件夹也是历史列表中的上一个文件夹，Opus 将向后退而不是向上移动 - 保留文件选择和其它状态以前的文件夹。

*Example:* `Go UP`
</td></tr><tr><td>
USEQUALKEYS</td><td>
/S</td><td>

*(不设值)*</td><td>

激活预先配置的主限定键的行为 - **Control** 将在双显示模式下打开文件夹，**Shift** 在新文件窗口中打开，**Alt** 在新标签页中打开。

这相当于 **KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB**.

*Example:* `Go C:\ USEQUALKEYS`
</td></tr><tr><td>
USER</td><td>
/K</td><td>

*\<用户名\>*</td><td>

当为 **PATH** 参数提供特定文件夹别名时可以使用。这允许你指定一个替代用户名来访问特定用户实例的系统文件夹（前提是，当然你有相应的权限）。如果指定的别名不支持多个用户，则此参数无效。

*Example:* `Go /desktopdir USER="Leo Nudelson"`
</td></tr><tr><td>
VIEW</td><td>
/K</td><td>

**largeicons**</td><td>

将新文件夹的 [视图](/Manual/basic_concepts/the_lister/view_modes.zh.md) 更改为 *大图标* 模式。

*Example:* `Go CURRENT NEWTAB VIEW=largeicons`
</td></tr><tr><td>
</td><td>
</td><td>

**smallicons**</td><td>

将新文件夹的视图更改为 *小图标* 模式。

*Example:* `Go C:\ VIEW smallicons`
</td></tr><tr><td>
</td><td>
</td><td>

**list**</td><td>

将视图更改为 *列表* 模式。

*Example:* `Go {destpath} VIEW list`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

将视图更改为 *详细信息* 模式。

*Example:* `Go CURRENT LAYOUT=PhotoLayout VIEW=details`
</td></tr><tr><td>
</td><td>
</td><td>

**power**</td><td>

将视图更改为增强模式。

*Example:* `Go NEW VIEW=power`
</td></tr><tr><td>
</td><td>
</td><td>

**thumbnails**</td><td>

将视图更改为 *缩略图* 模式。

*Example:* `Go /desktop VIEW=thumbnails`
</td></tr><tr><td>
</td><td>
</td><td>

**tiles**</td><td>

将视图更改为 *平铺* 模式。

*Example:* `Go @WorkFTP NEWTAB VIEW tiles`
</td></tr><tr><td>
WHENDUAL</td><td>
/K</td><td>

**checkmouse**</td><td>

此命令与 **BACK**, **FORWARD** 和 **UP** 参数配合使用，旨在与“应用命令”热键搭配使用，例如鼠标上的后退按钮。它让你可以使由鼠标触发的导航命令作用于双显示文件窗口中鼠标指针下方的文件列表区域，而不是默认情况下的源文件列表区域。

*Example:* `Go BACK WHENDUAL=checkmouse`
</td></tr><tr><td>
</td><td>
r</td><td>

**anydevice**</td><td>

与 **checkmouse** 参数配合使用，可在从非鼠标设备（例如，当命令绑定到键盘上的 **Back** 按钮时）运行该命令时激活 **WHENDUAL** 参数。

*Example:* `Go BACK WHENDUAL=checkmouse,anydevice`
</td></tr><tr><td>
</td><td>
</td><td>

**deffocus**</td><td>

添加 deffocus 参数以使命令在鼠标指针当前不在两个文件列表区域的任一区域上时恢复默认行为。

*Example:* `Go BACK WHENDUAL=checkmouse,deffocus`
</td></tr></tbody>
</table>
