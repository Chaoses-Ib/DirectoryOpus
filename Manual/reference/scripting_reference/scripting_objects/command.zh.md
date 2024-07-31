# Command

**Command** 对象用于脚本运行 Opus 命令。任何您可以从按钮或热键运行的命令都可以从脚本运行 - 脚本甚至可以运行 [其它脚本添加的命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。从根本上说，使用 **Command** 对象类似于配置 Opus 按钮。您向对象添加一个或多个命令行，就像您向按钮的功能添加一个或多个命令行一样。您可以告诉它对哪些文件和文件夹进行操作，并且可以使用对象的各种方法和属性来修改命令的行为。初始化对象后，您可以使用 **Run** 或 **RunCommand** 方法来调用命令。

**Command** 对象可以通过 **[DOpusFactory](dopusfactory.zh.md).Command** 方法创建。默认情况下，此对象没有源、目标、要操作的文件等 - 您必须使用适当的方法来配置命令才能运行它。您还可以从 **[Func](func.zh.md).command** 属性检索 **Command** 对象，在这种情况下，源、目标、要操作的文件以及其它几个属性会为您预先初始化。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
deselect</td><td>

*bool*</td><td>

将此属性设置为 **False** 以防止此命令使用的文件被取消选择，并将此属性设置为 **True** 以在函数完成后取消选择它们。请注意，文件只有在来自 **[Tab](tab.zh.md)** 对象时才会被取消选择，并且只有在命令成功时才会被取消选择。
</td></tr><tr><td>
dest</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示此命令的目标文件夹。如果设置了目标标签页，则它将是标签页中的路径。您不能直接设置此属性 - 相反，请使用 **SetDest** 或 **SetDestTab** 方法来更改目标文件夹。
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示此命令的目标标签页（如果它存在 - 并非所有命令都需要目标）。您不能直接设置此属性 - 相反，请使用 **SetDestTab** 方法来更改目标标签页。
</td></tr><tr><td>
filecount</td><td>

*int*</td><td>

返回 **files** 对象中的项目数。
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.zh.md)**</td><td>

返回一个 **[Items](items.zh.md)** 对象，表示此命令要对其进行操作的文件和文件夹。您不能直接修改此对象 - 相反，您可以使用各种方法（**ClearFiles**、**SetFiles**、**AddFile**、**RemoveFile** 等）来修改要操作的项目列表。
</td></tr><tr><td>
linecount</td><td>

*int*</td><td>
返回添加到命令的指令行数。
</td></tr><tr><td>
progress</td><td>

*object:***[Progress](progress.zh.md)**</td><td>

返回一个 **[Progress](progress.zh.md)** 对象，您可以使用它向用户显示进度指示器。
</td></tr><tr><td>
results</td><td>

*object:***[Results](results.zh.md)**</td><td>

在使用此对象运行的每个命令之后，都可以从此属性获得 **Results** 对象。这提供了有关命令结果的信息。
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，表示此命令的源文件夹。如果设置了源标签页，则它将是标签页中的路径。您不能直接设置此属性 - 相反，请使用 **SetSource** 或 **SetSourceTab** 方法来更改源文件夹。
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示此命令的源标签页。您不能直接设置此属性 - 相反，请使用 **SetSourceTab** 方法来更改源标签页。
</td></tr><tr><td>
vars</td><td>

*object*:**[Vars](vars.zh.md)**</td><td>

此 **[Vars](vars.zh.md)** 对象表示所有定义的具有 *命令范围* 的变量（这些变量的作用域为此函数 - 例如，使用 **@set** 指令设置的变量）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddFile</td><td>

\<string:path\>  
或 \<**[Path:](path.zh.md)**path\>  
或 \<**[Item:](item.zh.md)**item\></td><td>

*int*</td><td>

将指定的项目添加到此命令要对其进行操作的项目集合中。您可以将项目的路径作为 *string* 或 **[Path](path.zh.md)** 对象传递，也可以直接传递 **[Item](item.zh.md)** 对象。

此方法返回集合中的项目总数。
</td></tr><tr><td>
AddFiles</td><td>

*object:***[Items](items.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Item](item.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Path](path.zh.md)**  
或 ***[Vector](vector.zh.md)**:string*  
或 ***[StringSet](stringset.zh.md)***  
或 ***[UnorderedSet](unorderedset.zh.md)***</td><td>

*int*</td><td>

将指定集合中的项目添加到此命令要对其进行操作的项目列表中。返回值是集合中新的项目数。

您还可以传递 **[Vector](vector.zh.md)** 的 **[Item](item.zh.md)** 或 **[Path](path.zh.md)** 对象，或完整路径字符串，而不是集合。或者，您可以传递 **[StringSet](stringset.zh.md)** 或 **[UnorderedSet](unorderedset.zh.md)** 的完整路径字符串。
</td></tr><tr><td>
AddFilesFromClipboard</td><td>

*none*</td><td>

*int*</td><td>
将剪贴板的内容添加到此命令要对其进行操作的项目集合中。此方法支持将文件和作为文本复制到剪贴板的文件路径。返回值是集合中新的项目数。
</td></tr><tr><td>
AddFilesFromFile</td><td>

\<string:path\>  
\<string:encoding\></td><td>

*int*</td><td>

从指定文件的内容中读取文件路径并将其添加到项目集合中。您可以将文件的路径作为 *string* 或 **[Path](path.zh.md)** 对象传递。文件必须包含每行一个绝对路径。  
文件的编码假定为 ANSI，除非它在开头有 BOM（字节序标记），或者您指定了 *encoding* 参数。如果指定了编码，则它必须是一个 *string*，等于以下之一：**utf16be**、**utf16le**、**utf8**、**ansi** 或 **cp:*XXXX***，其中 *XXXX* 指定代码页号）。

返回值是集合中新的项目数。
</td></tr><tr><td>
AddFilesFromFolder</td><td>

\<string:path\></td><td>

*int*</td><td>

将指定文件夹的内容添加到此命令要对其进行操作的项目集合中。您可以将文件夹的路径作为 *string* 或 **[Path](path.zh.md)** 对象传递。您还可以将 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 附加到路径，以仅添加与指定模式匹配的文件。
</td></tr><tr><td>
AddLine</td><td>

\<string:instruction\></td><td>

*none*</td><td>

将指定的指令行添加到此对象将运行的命令中。**AddLine** 方法允许您构建复杂的多个命令行 - 依次添加每一行，然后使用 **Run** 方法运行命令。对于单行命令，使用 **RunCommand** 方法更简单。
</td></tr><tr><td>
Clear</td><td>

*none*</td><td>

*none*</td><td>
清除命令中的所有指令行。
</td></tr><tr><td>
ClearFailed</td><td>

*none*</td><td>

*none*</td><td>

从 **[Items](items.zh.md)** 集合中清除失败标志。当运行命令时，任何失败的项目都会将其 **failed** 属性设置为 **True**，并且一旦发生这种情况，任何后续命令都会跳过该文件。您可以调用此方法来重置所有失败标志。
</td></tr><tr><td>
ClearFiles</td><td>

*none*</td><td>

*none*</td><td>
清除此命令要对其进行操作的项目集合。
</td></tr><tr><td>
ClearModifier</td><td>

\<string:modifier\></td><td>

*none*</td><td>

清除为此命令设置的任何修饰符。支持的修饰符是完整 [命令修饰符](../../command_reference/command_modifier_reference.zh.md) 列表的子集 - 请参阅 **SetModifier** 方法以获取这些修饰符的列表。您还可以传递 \* 来清除已设置的所有修饰符。
</td></tr><tr><td>
CommandList</td><td>

*none*  
或 \<string:types\></td><td>

*object:***[StringSet](stringset.zh.md)**</td><td>

返回一个 **[StringSet](stringset.zh.md)**，其中包含所有 Opus 命令的名称。您还可以选择通过向 **CommandList** 方法提供一个或多个以下标志作为参数来过滤此集合：

|       |                              |
|-------|------------------------------|
| **i** | 内部（内置）命令           |
| **s** | 脚本命令                      |
| **u** | 用户命令                      |
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.zh.md)**</td><td>

创建一个新的 **[Dialog](dialog.zh.md)** 对象，允许您显示对话框和弹出菜单。对话框的 **window** 属性将自动分配给源标签页。
</td></tr><tr><td>
GetModifiers</td><td>

*none*</td><td>

*object:***[Map](map.zh.md)**</td><td>

返回一个 **[Map](map.zh.md)**，其中包含为命令设置的修饰符（可以通过 **SetModifier** 方法设置，或者在 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的情况下，任何在调用脚本的按钮上设置的修饰符）。
</td></tr><tr><td>
IsSet</td><td>

\<string:condition\>  
\[\<string:command\>\]</td><td>

*bool*</td><td>

如果指定的 **[Set](../../command_reference/internal_commands/set.zh.md)** 命令条件为真，则返回 **True**。这等效于 **@ifset** [命令修饰符。](../../command_reference/command_modifier_reference.zh.md) 可选的第二个参数允许您测试基于除 **Set** 以外的命令的条件 - 例如，在查看器中，**IsSet("VIEWERCMD=mark", "Show")** 用于测试当前图像是否已标记。
</td></tr><tr><td>
RemoveFile</td><td>

\<string:path\>  
或 \<**[Path:](path.zh.md)**path\>  
或 \<**[Item](item.zh.md)**:item\>  
或 \<int:index\></td><td>

*int*</td><td>

从 **[Items](items.zh.md)** 集合中删除指定的文件。您可以将文件的路径作为 *string* 或 **[Path](path.zh.md)** 对象传递。您还可以传递 **[Item](item.zh.md)** 本身，或它在集合中的索引（从 0 开始）。返回值是集合中新的项目数。
</td></tr><tr><td>
Run</td><td>

*none*</td><td>

*int*</td><td>

运行使用此对象构建的命令。返回的值指示命令是否成功运行。零表示无法运行命令或命令已中止；任何其它数字表示命令至少已针对某些文件运行。（请注意，这不是外部命令的“退出代码”。对于外部命令，它仅指示 Opus 是否已启动该命令。如果您需要外部命令的退出代码，请使用 WScript.Shell Run 或 Exec 方法来运行该命令。）您可以使用 **Results** 属性来查找有关命令结果的更多信息，并发现使用 **files** 集合中每个 **[Item](item.zh.md)** 的 **failed** 属性失败的文件（如果有）。
</td></tr><tr><td>
RunAsync</td><td>

*none*</td><td>

*int*</td><td>
异步运行使用此对象构建的命令，而不等待它返回。返回的值指示命令是否已成功启动，但无法获得有关命令结果的更多信息。
</td></tr><tr><td>
RunCommand</td><td>

\<string:instruction\></td><td>

*int*</td><td>

运行 *instruction* 参数给出的单行命令。调用此方法等效于使用 **AddLine** 方法添加单行，然后调用 **Run** 方法。
</td></tr><tr><td>
RunCommandAsync</td><td>

\<string:instruction\></td><td>

*int*</td><td>

异步运行 *instruction* 参数给出的单行命令，而不等待它返回。调用此方法等效于使用 **AddLine** 方法添加单行，然后调用 **RunAsync** 方法。
</td></tr><tr><td>
SetDest</td><td>

\<string:path\></td><td>

*none*</td><td>

将命令的目标设置为指定的路径。您可以将路径作为 *string* 或 **[Path](path.zh.md)** 对象传递。调用此方法会清除命令中的目标标签页属性。
</td></tr><tr><td>
SetDestTab</td><td>

\<**[Tab](tab.zh.md)**:tab\></td><td>

*none*</td><td>

将命令的目标设置为指定的标签页。目标路径将从标签页自动初始化（因此您不需要同时调用 **SetDest** 和 **SetDestTab**）。
</td></tr><tr><td>
SetFiles</td><td>

*object:***[Items](items.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Item](item.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Path](path.zh.md)**  
或 ***[Vector](vector.zh.md)**:string*  
或 ***[StringSet](stringset.zh.md)***  
或 ***[UnorderedSet](unorderedset.zh.md)***</td><td>

*none*</td><td>

配置命令以使用指定 **[Items](items.zh.md)** 集合中的文件作为命令将要操作的项目。

您也可以传递其它集合类型之一，与 **AddFiles** 方法相同。
</td></tr><tr><td>
SetModifier</td><td>

\<string:modifier\>  
\<string:value\></td><td>

*none*</td><td>

打开此命令的修饰符。支持的修饰符是完整 [命令修饰符](../../command_reference/command_modifier_reference.zh.md) 列表的子集：  
**admin**、**async**、**codepage**、**externalonly**、**leavedoswindowopen**、**nodeselect**、**noexpandenv**、**nofilenamequoting**、**nolocalizefiles**、**noprogress**、**norunbatch**、**resolvelinks**、**runmode**。

使用此方法等效于使用 **AddLine** 方法将修饰符作为指令添加到命令中；例如，**Command.SetModifier("admin")** 与 **Command.AddLine("@admin")** 相同。如果修饰符需要值，则将其作为第二个参数传递，例如 **Command.SetModifier("runmode", "hide")**。
</td></tr><tr><td>
SetProgress</td><td>

\<**[Progress](progress.zh.md)**:progress\></td><td>

*none*</td><td>

允许您将一个命令的进度指示器与另一个命令共享。您可以将此方法传递从另一个 **Command** 对象获得的 **progress** 属性的值。
</td></tr><tr><td>
SetQualifiers</td><td>

\<string:qualifiers\></td><td>

*none*</td><td>

此方法允许您控制由此对象运行的命令在被调用时将考虑哪些限定符键已按下。例如，一些内部命令在按住某些限定符键时会改变其行为 - 调用此方法允许您设置它们将看到的键。

*qualifiers* 参数必须包含以下一个或多个字符串（以逗号分隔）：**none**、**shift**、**ctrl**、**alt**、**lwin**、**rwin**、**win**。
</td></tr><tr><td>
SetSource</td><td>

\<string:path\></td><td>

*none*</td><td>

将命令的源设置为指定的路径。您可以将路径作为 *string* 或 **[Path](path.zh.md)** 对象传递。调用此方法会清除命令中的源标签页属性。
</td></tr><tr><td>
SetSourceTab</td><td>

\<**[Tab](tab.zh.md)**:tab\></td><td>

*none*</td><td>

将命令的源设置为指定的标签页。源路径将从标签页自动初始化（因此您不需要同时调用 **SetSource** 和 **SetSourceTab**）。
</td></tr><tr><td>
SetType</td><td>

\<string:type\></td><td>

*none*</td><td>

设置此命令将运行的函数类型。这相当于 [高级命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.zh.md) 中的下拉控件。*type* 参数必须是以下字符串之一：**std**、**msdos**、**script**、**wsl**。如果类型未明确设置，则默认值为标准（**std**）。
</td></tr><tr><td>
UpdateToggle</td><td>

*none*</td><td>

*none*</td><td>

此方法可用于更新使用变量来确定其标签或状态的工具栏按钮的外观。例如，按钮可能会使用 **[@toggle:if](../../command_reference/command_modifier_reference.zh.md)** 来设置其选择状态，具体取决于 *全局*、*标签页* 或 *文件窗口范围* 变量的存在。如果您从脚本中更改了 such a variable，则需要调用此方法以强制使用它的按钮更新。
</td></tr></tbody>
</table>