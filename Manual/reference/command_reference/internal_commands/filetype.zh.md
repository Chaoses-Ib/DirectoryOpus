# FileType
**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
描述
</th></tr></thead><tbody><tr><td>
ACTION</td><td>
</td><td>

*\<事件\>*</td><td>

对所选文件触发文件类型定义的事件。例如，你可以用这个来触发按钮或热键上的文件的拖放事件。这是 **FileType** 命令的默认参数 - 你不需要指定 **ACTION** 关键字。

值必须是下列事件关键字之一：**open**, **explore**, **find**, **print**, **shellex**, **drop**, **dropshift**, **dropctrl**, **dropalt**, **dblclk**, **dblclkshift**, **dblclkctrl**, **dblclkalt**, **mdblclk**, **mdblclkalt**, **mdblclkshift** 和 **mdblclkctrl**。

*示例：* `FileType drop`

**shellex**（shell 执行）操作特殊，因为它绕过 Opus 自己的逻辑和配置/覆盖项的大部分，将请求传递给 Windows shell 去执行。当它自身使用的时候，它将做同样的事情，即在文件资源管理器中双击目标文件或文件夹。这通常与 **dblclk**（双击）操作相同，而后者通常与 **open** 操作相同，但在 Opus 和 shell 之间有差异，以及 Opus 中不影响 shell 的配置覆盖项。你可以进一步使用 **SHELLCLASS** 和 **SHELLVERB** 参数修改 **shellex** 操作的内容。
</td></tr><tr><td>
CONTEXTFORCE</td><td>
/S</td><td>

*（无值）*</td><td>

当与 **CONTEXTMENU** 参数一起使用时，这将覆盖配置中 **[杂项/Windows 集成](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.zh.md)** 页上的 **在文件上下文菜单中隐藏 Windows 项** 选项。

*示例：* `FileType CONTEXTMENU CONTEXTFORCE`
</td></tr><tr><td>
CONTEXTMENU</td><td>
/O</td><td>

*（无值）*</td><td>

显示选定的文件和文件夹的标准系统上下文菜单（作为 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这样可以将上下文菜单嵌入到下拉菜单中（例如，用于默认的文件菜单）。你还可以将其与 **CONTEXTFORCE** 选项结合使用，将完整的 Windows 上下文菜单分流到普通上下文菜单的子菜单中。

*示例：* `FileType CONTEXTMENU`
</td></tr><tr><td>
</td><td>
</td><td>

*\<GUID\>*</td><td>

显示指定上下文菜单扩展添加的任何上下文菜单项。这让你能够（结合 **在文件上下文菜单中隐藏 Windows 项** 选项）精确控制哪些上下文菜单项显示在你的上下文菜单上。你需要知道有问题的上下文菜单扩展的 GUID，并且在本文档帮助的范围内找不到解决方法 - 相反，请参阅 Opus 资源中心的 [此文章](https://resource.dopus.com/t/tip-organise-and-speed-up-context-menus/1204?u=chaoses-ib) 来了解如何使用此功能的示例。

*示例：* `FileType CONTEXTMENU {FB314ED9-A251-47B7-93E1-CDD82E34AF8B} CONTEXTFORCE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<文件类别\>*</td><td>

显示指定文件类别的任何上下文菜单。这让你能够（结合 **在文件上下文菜单中隐藏 Windows 项** 选项）精确控制哪些上下文菜单项显示在你的上下文菜单上。

*示例：* `FileType CONTEXTMENU jpegfile`
</td></tr><tr><td>
CONTEXTOPTIONS</td><td>
/K</td><td>

**INCLUDE=***\<类型\>*</td><td>

当与 **CONTEXTMENU Directory\Background** 结合使用时，这让你可以包含特定文件类型（且排除所有其它文件类型）从添加的 shell *新建* 菜单中。请注意，你必须将值用引号引起来，因为它包含一个等号，否则会混淆命令解析器。

*示例：* `FileType CONTEXTMENU Directory\Background CONTEXTOPTIONS "INCLUDE=.bmp,.jpg,.gif"`
</td></tr><tr><td>
</td><td>
</td><td>

**EXCLUDE=***\<类型\>*</td><td>

当与 **CONTEXTMENU Directory\Background** 一起使用时，从生成的 shell *新建* 菜单中排除指定的文件类型。你还可以使用\*在该上下文中完全禁用新建菜单。

*示例：* `FileType CONTEXTMENU Directory\Background CONTEXTOPTIONS "EXCLUDE=*"`
</td></tr><tr><td>
</td><td>
</td><td>

**windowsonly**</td><td>

你可以指定 **CONTEXTOPTIONS=windowsonly** 一次性添加所有“Windows”上下文菜单项。（这意味着所有不特定于 Opus 的上下文菜单项，并且可能包括使用 Windows 上下文菜单 API 添加的 3rd 方程序的菜单项。）

你可以将其与配置选项 *在文件上下文菜单中隐藏 Windows 项* 结合使用，将所有“Windows”上下文菜单项移动到子菜单。

与上面描述的 **INCLUDE** 和 **EXCLUDE** 不同，**windowsonly** *不* 仅限于 **Directory\Background** 菜单。

*示例：* `Filetype CONTEXTMENU CONTEXTOPTIONS=windowsonly`
</td></tr><tr><td>
EDIT</td><td>
/S</td><td>

*（无值）*</td><td>

显示对应于所选文件的文件类型定义的 [文件类型编辑器](/Manual/file_types/filetype_editor/README.zh.md)。你可以将该命令添加到 *所有文件和文件夹* 的上下文菜单，从而使你能快速编辑任何文件的文件类型定义。

*示例：* `FileType EDIT`
</td></tr><tr><td>
FILE</td><td>
/K/M</td><td>

*\<文件名\> ...*</td><td>

指定要执行文件类型操作的文件名。如果没有指定，将使用当前源文件夹中所有选定的文件。

*示例：* `FileType open FILE C:\Data\sales.xls`
</td></tr><tr><td>
FILECONTEXT</td><td>

*/S*</td><td>

*（无值）*</td><td>

创建一个按钮，当点击右键时，显示 **FILE** 参数指向的文件或文件夹的上下文菜单。当点击左键时，按钮的作用与不带 **FILECONTEXT** 参数的情况相同。

（这必须用于普通按钮的左键操作来修改对按钮点击右键时做出的操作。它无法在单独具有左键、右键和中键操作的“三键”中使用。）

*示例：* `FileType ACTION=dblclk FILECONTEXT FILE="C:\MyApp.exe"`
</td></tr><tr><td>
FROMCLIPBOARD</td><td>
/O</td><td>

*（无值）*</td><td>

与 **NEW** 参数一起使用，从剪贴板内容中创建具有相应名称的一个或多个新文件。这被设计为两部分操作的第二部分；第一部分是使用 **[剪贴板](clipboard.zh.md) COPYNAMES** 命令将一个或多个文件的文件名复制到剪贴板。
对于剪贴板中的每个文件名，Opus 都会创建一个指定类型的新文件。如果剪贴板包含完全限定的路径名，则新文件将与源文件创建在相同的位置（除非被 PATH 参数覆盖）。如果剪贴板仅包含没有路径的文件名，则新文件将在当前源文件列表中创建。

*示例:* `FileType NEW=.txt FROMCLIPBOARD`
</td></tr><tr><td>
</td><td>
</td><td>

**keepext**</td><td>

指定此参数以保留剪贴板上的文件的文件扩展名。

*示例:* `FileType NEW=.txt FROMCLIPBOARD=keepext`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当用于生成项列表的命令时（参见 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表开始处添加一个小的标题。当列表为空时，标题将被隐藏。标题仅适用于可能会在与该按钮相同的级别上生成多个项目命令。

当单独使用 **HEADING** 时，而未指定文本值，按钮的主要文本标签将用于标题。

*示例:* `FileType SENDTOMENU=nosub HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果希望标题文本不同于按钮标签，则可以指定标题文本。

*示例:* `FileType CONTEXTMENU HEADING="RMB 菜单"`
</td></tr><tr><td>
NEW</td><td>
/K</td><td>

*\<文件类型\>*</td><td>

创建指定类型的新文件。这等效于从 *新建* 上下文菜单中选择适当的项。只有注册有“新建”处理程序的文件才能以这种方式创建 - 因此，如果文件类型不显示在 *新建* 上下文菜单中，你将无法使用此命令创建此类文件。使用 **NEWNAME** 参数修改新文件的默认名称。

你还可以通过指定 **directory** 作为文件类型来创建目录。

*示例:* `FileType NEW .txt`  
*示例:* `FileType NEW=directory NEWNAME="我的目录"`

**FileType NEW** 命令自动将名为 **newfile** 的 [变量](../external_control_codes/codes_for_clipboard_and_variables.zh.md) 设置为新建文件的文件名。要插入变量，请使用 **{\$newfile}**。
</td></tr><tr><td>
NEWCOUNT</td><td>
/K/N</td><td>

*\<计数\>*</td><td>

允许一次创建多个新文件。这相当于多次运行 **FileType NEW** 命令。

*示例:* `FileType NEW .txt NEWCOUNT 10`
</td></tr><tr><td>
NEWMENU</td><td>
/S</td><td>

*(无值)*</td><td>

显示 Shell *新建* 菜单，该菜单允许你通过从菜单中选择适当的项来创建各种类型的新文件（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这让你可以将 *新建* 菜单嵌入到下拉菜单中。

*示例:* `FileType NEWMENU`
</td></tr><tr><td>
NEWNAME</td><td>
/K</td><td>

*\<新文件名\>*</td><td>

在创建新文件时通过 **NEW** 参数指定文件名。如果你未指定文件名的名称，将使用默认文件名。默认情况下，Opus 在创建新文件时在该新项上启动内联重命名，允许你对其重命名。如果你希望指定自己的文件名并防止内联重命名行为，请使用 **norename:** 字符串为文件名加前缀。

当主文件名已存在时，你还可以指定第二个文件名。这在与 **NEWCOUNT** 参数一起使用时非常有用，可以一次创建多个文件。在这种情况下，Opus 通常会在文件名末尾附加一个递增数字（用括号括住） - 通过使用 **NEWNAME** 参数指定一个第二个文件名，你可以控制插入该数字的位置。为此，在新名称末尾添加一个冒号，后面跟第二个名称。使用 **%c** 代码标记你希望插入数字的位置。你还可以使用 **%Nc** 指定数字应以零填充 - 例如，使用 **%5c** 填充为 5 位数字。你也可以省略主文件名，并在需要时对第一个文件自动编号。

*示例:* `FileType NEW .txt NEWNAME "norename:Text File.txt"`  
*示例:* `FileType NEW .txt NEWNAME=":Text %3c.txt" NEWCOUNT=20`
</td></tr><tr><td>
OPENWITHMENU</td><td>
/S</td><td>

*(无值)*</td><td>

显示 Shell *打开方式* 菜单，该菜单允许你选择程序来打开所选文件（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这让你可以将 *打开方式* 菜单嵌入到下拉菜单中。

*示例:* `FileType OPENWITHMENU`
</td></tr><tr><td>
PATH</td><td>
/K</td><td>

*\<路径\>*</td><td>

将其与 **NEW** 参数结合使用，以便在当前源文件列表外的其它位置创建新文件。请注意，当使用此参数时，新创建的文件不会自动进入内联重命名模式。

*示例:* `FileType NEW .txt PATH "{destpath}"`
</td></tr><tr><td>
SENDTOMENU</td><td>
/S</td><td>

*(无值)*</td><td>

显示 Shell 发送到菜单，该菜单允许你将所选文件和文件夹发送到各种程序和目标（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。

*示例:* `FileType SENDTOMENU`
</td></tr><tr><td>
</td><td>
</td><td>

**nosub**</td><td>

默认情况下，发送到菜单显示为子菜单；通过添加 **nosub** 值，发送到列表中的项将直接添加到包含 **FileType SENDTOMENU** 命令的工具栏或下拉菜单中。

*示例:* `FileType SENDTOMENU=nosub`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

强制以 \<<kbd>Shift</kbd> 键按下状态生成发送到菜单。在某些版本的 Windows 中，按住 <kbd>Shift</kbd> 时会显示一个扩展菜单。

*示例:* `FileType SENDTOMENU=nosub,shift`
</td></tr><tr><td>
SHELLCLASS</td><td>
/K</td><td>

*\<类\>*</td><td>

当与 **ACTION=shellex** 结合使用时，**SHELLCLASS** 参数允许你指定文件类型或应用程序类别的名称，Shell 应将其用于执行。这些名称来自 Windows 注册表的 HKEY_CLASSES_ROOT 部分。指定一个类允许你指示 shell 使用特定程序打开文件，即使它未关联为该文件类型的默认处理程序。

*示例:* `FileType ACTION=shellex SHELLCLASS=Photoshop.Image.20`

请注意，虽然这对于诸如无法以正常方式运行的 Microsoft Store 应用程序之类的东西很有用，但通常有更容易的方法来执行此操作！如果你只需要在特定文件上运行特定程序，通常可以直接运行该程序并传递 **{filepath}** 参数。上面的示例的一个不太生硬的版本根本不会使用 **FileType** 命令：

    C:\Program Files\Photoshop\Photoshop.exe" {filepath}
</td></tr><tr><td>
SHELLVERB</td><td>
/K</td><td>

*\<动词\>*</td><td>

当与 **ACTION=shellex** 结合使用时，**SHELLVERB** 参数允许你指定文件类型动词，以请求 Shell 执行。这与 **ACTION** 参数的其它可能值有些重叠，主要区别在于执行是由 Windows Shell（而不是 Opus）执行，而且你可以同时使用 **SHELLCLASS** 参数。
*示例：* `FileType ACTION=shellex SHELLCLASS=Photoshop.Image.20 SHELLVERB=print`
</td></tr><tr><td>
摘要</td><td>
/O</td><td>

*\<无值\>*</td><td>

显示一个包含饼状图的对话框，饼状图指示当前文件夹中的文件类型及其相对比例。

该对话框有许多选项：

- 选择的/全部 - 饼状图是应用于文件夹中的所有文件还是仅应用于所选文件
- 文件计数/大小 - 是否按文件数量（计数）或总大小对文件类型进行排序
- 扩展名/组 - 饼状图表示各个文件扩展名还是 [文件类型组](/Manual/file_types/file_type_groups.zh.md)。

默认情况下，该对话框会记住最近使用的设置。您可以使用此命令的可选参数来覆盖默认设置。

*示例：* `FileType SUMMARY`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

饼状图应应用于文件夹中的所有文件，而不是已选择的文件。

*示例：* `FileType SUMMARY=all`
</td></tr><tr><td>
</td><td>
</td><td>

**ascending**</td><td>

文件类型应按升序（从最少组到最多组）排序，而不是按降序排序。请注意，此选项当前不能通过用户界面获得，只能通过命令行获得。

*示例：* `FileType SUMMARY=groups,ascending`
</td></tr><tr><td>
</td><td>
</td><td>

**count**</td><td>

文件类型应按文件总数进行排序。

*示例：* `FileType SUMMARY=count`
</td></tr><tr><td>
</td><td>
</td><td>

**ext**</td><td>

应按扩展名而非文件类型组对文件类型进行分组。

*示例：* `FileType SUMMARY=ext,all`
</td></tr><tr><td>
</td><td>
</td><td>

**groups**</td><td>

文件类型应按文件类型组而非扩展名进行分组。

*示例：* `FileType SUMMARY=groups`
</td></tr><tr><td>
</td><td>
</td><td>

**nomerge**</td><td>

默认情况下，“相似”的文件类型被视为相同类型，例如 **\*.jpg** 和 **\*.jpeg**。使用 **nomerge** 选项将它们拆分并将其视为各个类型。

*示例：* `FileType SUMMARY=nomerge,size`
</td></tr><tr><td>
</td><td>
</td><td>

**selected**</td><td>

饼状图应仅应用于文件夹中的已选文件，而不是所有文件。

*示例：* `FileType SUMMARY=selected`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

文件类型应按文件总大小而不是文件数量进行排序。

*示例：* `FileType SUMMARY=size,ext`
</td></tr></tbody>
</table>