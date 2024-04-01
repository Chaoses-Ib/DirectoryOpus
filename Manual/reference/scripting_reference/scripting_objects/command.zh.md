**Command**对象被脚本用来运行Opus命令。从按钮或热键能够运行的任何命令都可以从脚本中运行 - 脚本甚至可以运行[其它脚本添加的命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md)。从根本上说，使用**Command**对象类似于配置Opus按钮。你需要像给按钮的功能添加一行或多行命令那样，给该对象添加一行或多行命令。你可以告诉要针对哪些文件和文件夹执行操作，还可以使用该对象的各种方法和属性来修改命令的行为。一旦对象被初始化，就可以使用**Run**或**RunCommand**方法来调用命令。

**Command**对象可以通过**[DOpusFactory](dopusfactory.zh.md).Command**方法创建。默认情况下，此对象没有来源、目标、要操作的文件等 - 必须在运行命令之前使用适当的方法配置该命令。你还可以从**[Func](func.zh.md).command**属性中检索**Command**对象，在这种情况下，该命令的来源、目标、要操作的文件和其它几个属性都是预先初始化的。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
deselect</td><td>

*布尔*</td><td>

将此属性设置为**False**以防止此命令使用的文件被取消选择，设置为**True**以在函数结束后取消选择它们。请注意，只有当文件来自**[Tab](tab.zh.md)**对象时，才会取消对文件的选择，并且只有在命令成功时才会取消选择。
</td></tr><tr><td>
dest</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回一个**[Path](path.zh.md)** 对象，它表示此命令的目标文件夹。如果设置了目标标签页，则这将是该标签页中的路径。你不能直接设置此属性 - 相反，可以使用**SetDest**或**SetDestTab**方法来更改目标文件夹。
</td></tr><tr><td>
desttab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)** 对象，它表示此命令的目标标签页（如果存在 - 并非所有命令都需要目标）。你不能直接设置此属性 - 相反，使用 **SetDestTab** 方法来更改目标标签页。
</td></tr><tr><td>
filecount</td><td>

*整数*</td><td>

返回**文件**对象中的项数。
</td></tr><tr><td>
files</td><td>

*对象:***[Items](items.zh.md)**</td><td>

返回一个**[Items](items.zh.md)** 对象，它表示此命令将对其执行操作的文件和文件夹。你不能直接修改此对象 - 相反，你可以使用各种方法（**ClearFiles**、**SetFiles**、**AddFile**、**RemoveFile** 等）来修改要执行操作的项的列表。
</td></tr><tr><td>
linecount</td><td>

*整数*</td><td>
返回添加到命令的指令行数。
</td></tr><tr><td>
progress</td><td>

*对象:***[Progress](progress.zh.md)**</td><td>

返回一个**[Progress](progress.zh.md)** 对象，你可以使用它向用户显示进度指示器。
</td></tr><tr><td>
results</td><td>

*对象:***[Results](results.zh.md)**</td><td>

对于通过这个对象运行的每个命令，此属性都提供了一个**Results**对象。这提供了有关命令结果的信息。
</td></tr><tr><td>
source</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回一个**[Path](path.zh.md)** 对象，它表示此命令的源文件夹。如果设置了源标签页，则这将是该标签页中的路径。你不能直接设置此属性 - 相反，可以使用**SetSource**或**SetSourceTab**方法来更改源文件夹。
</td></tr><tr><td>
sourcetab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个**[Tab](tab.zh.md)** 对象，它表示此命令的源标签页。你不能直接设置此属性 - 相反，使用 **SetSourceTab** 方法来更改源标签页。
</td></tr><tr><td>
vars</td><td>

*对象*:**[Vars](vars.zh.md)**</td><td>

此**[Vars](vars.zh.md)** 对象表示具有 **命令范围**（在此函数中进行范围限定 - 例如使用**@set**指令设置）的所有定义变量。
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

\<字符串:路径\>  
或 \<**[路径:](path.zh.md)**路径\>  
或 \<**[项:](item.zh.md)**项\></td><td>

*整数*</td><td>

将指定项添加到此命令要针对其执行操作的项集合中。你可以将项的路径作为*字符串*或**[Path](path.zh.md)** 对象传递，也可以直接传递一个**[Item](item.zh.md)** 对象。

此方法返回集合中的项总数。
</td></tr><tr><td>
AddFiles</td><td>

*对象:***[Items](items.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Item](item.zh.md)**  
或 ***[Vector](vector.zh.md)**:***[Path](path.zh.md)**  
或 ***[Vector](vector.zh.md)**:字符串*  
或 ***[StringSet](stringset.zh.md)***  
或 ***[UnorderedSet](unorderedset.zh.md)***</td><td>

*整数*</td><td>

将指定集合中的项添加到此命令要针对其执行操作的项列表中。返回值是集合中新的项数。

你还可以传递**[Vector](vector.zh.md)**的**[Item](item.zh.md)**或**[Path](path.zh.md)**对象或完整的路径字符串，而不是集合。或者是一个**[StringSet](stringset.zh.md)**或**[UnorderedSet](unorderedset.zh.md)**的完整路径字符串。
</td></tr><tr><td>
AddFilesFromClipboard</td><td>

*无*</td><td>

*整数*</td><td>
将剪贴板的内容添加到此命令要针对其执行操作的项集合中。此方法同时支持作为文本复制到剪贴板的文件和文件路径。返回值是集合中新的项数。
</td></tr><tr><td>
AddFilesFromFile</td><td>

\<字符串:路径\>  
\<字符串:编码\></td><td>

*整数*</td><td>

从指定文件的文本中读取文件路径，并将它们添加到项集合中。你可以将文件的路径作为*字符串*或**[Path](path.zh.md)** 对象提供。该文件必须包含每行一个绝对路径。  
该文件的编码假定为 ANSI，除非它在开头有 BOM（字节顺序标记），或者你指定了*编码*参数。如果你指定了编码，则它必须是一个*字符串*，等于以下某个字符串：**utf16be**、**utf16le**、**utf8**、**ansi** 或 **cp:*XXXX***，其中 *XXXX* 指定代码页号）。

返回值是集合中新的项数。
</td></tr><tr><td>
AddFilesFromFolder</td><td>

\<字符串:路径\></td><td>

*整数*</td><td>

将指定文件夹的内容添加到此命令要针对其执行操作的项集合中。你可以将文件夹的路径作为*字符串*或**[Path](path.zh.md)** 对象传递。你还可以将[通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)追加到路径中，以仅添加匹配指定模式的文件。
*none*</td><td>

Sets the command's source to the specified path. You can provide the path as either a *string* or a **[Path](path.zh.md)** object. Calling this method clears the source tab property from the command.
</td></tr><tr><td>
SetSourceTab</td><td>

\<**[Tab](tab.zh.md)**:tab\></td><td>

*none*</td><td>

Sets the command's source to the specified tab. The source path will be initialized from the tab automatically (so you don't need to call **SetSource** as well as **SetSourceTab**).
</td></tr><tr><td>
StartListening</td><td>

*none*</td><td>

*none*</td><td>

Tells the current command object to start listening for events. Typically you would just call the **Run** method without using this method, but by using this method you can prevent Opus from running the command until some event has occurred. For example, this will wait for a keypress before running the command:

```vbscript
Set cmd = CreateObject("Opus.Command")

cmd.StartListening
cmd.AddLine "Msgbox \"hello\""
cmd.Run
```
</td></tr><tr><td>
StopListening</td><td>

*none*</td><td>

*none*</td><td>

Tells the current command object to stop listening for events. See **StartListening** for more information.
</td></tr><tr><td>
ToggleModifier</td><td>

\<string:modifier\></td><td>

*bool*</td><td>

Toggles the specified modifier for this command. Returns **True** if the modifier is now set, **False** if it is now clear. The *modifier* argument is one of the supported [command modifiers](../../command_reference/command_modifier_reference.zh.md).
</td></tr>
*none*</td><td>

将命令的源设置为指定路径。你可以提供路径作为一个 *字符串* 或一个 **[路径](path.zh.md)** 对象。调用此方法会清除命令的源标签属性。
</td></tr><tr><td>
SetSourceTab</td><td>

\<**[标签](tab.zh.md)**:tab\></td><td>

*none*</td><td>

将命令的源设置为指定的标签。源路径将从标签自动初始化（因此你不需要同时调用 **SetSource** 和 **SetSourceTab**）。
</td></tr><tr><td>
SetType</td><td>

\<字符串:type\></td><td>

*none*</td><td>

设置此命令将运行的函数的类型。这等同于 [高级命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.zh.md) 中的下拉控件。*类型* 参数必须是以下字符串之一：**std**、**msdos**、**script**、**wsl**。如果没有具体设置类型，则默认值为标准 (**std**)。
</td></tr><tr><td>
UpdateToggle</td><td>

*none*</td><td>

*none*</td><td>

此方法可用于更新使用变量来确定其标签或状态的工具栏按钮的外观。例如，按钮可能使用 **[@toggle:if](../../command_reference/command_modifier_reference.zh.md)** 根据 *全局-*、*标签-* 或 *文件窗口作用域* 变量的设置其选择状态。如果你已从脚本更改此类变量，则可以调用此方法，以强制使用它的按钮进行更新。
</td></tr></tbody>
</table>