# 进度

**进度**对象让你显示和控制标准的 Directory Opus 进度指示器对话框。此对象可从 **[命令](command.zh.md)。进度** 属性中获得。使用 **进度** 对象的基本步骤如下：

1. 初始化基本属性。
2. 调用 **初始化** 方法创建对话框（这创建了对话框，但没有向用户显示）。
3. 准备就绪时，调用 **显示** 方法使对话框可见。
4. 调用相应的方法使用 **步进文件** 和 **步进字节** 等方法初始化进度条的状态。
5. 随着操作的进行，使用 **步进文件** 和 **步进字节** 等方法推进进度条。
6. 在适当的情况下，使用 **获取中止状态** 轮询 *中止* 和其他控制按钮的状态。
7. 在操作完成时调用 **隐藏** 方法并销毁对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
中止</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果要显示 *Abort* 按钮，则设置为 **True**，否则设置为 **False** 以禁用它。
</td></tr><tr><td>
字节</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果对话框应显示整个文件而不是字节的进度，则设置为 **True**。
</td></tr><tr><td>
延迟</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果在调用 **显示** 方法后对话框应延迟显示，则设置为 **True**。延迟由用户在配置中配置。
</td></tr><tr><td>
全部</td><td>

*bool*</td><td>

在调用 **初始化** 之前，设置为 **True** 以启用具有两个单独进度条（一个用于文件，一个用于字节）的“全尺寸”进度指示器。
</td></tr><tr><td>
已拥有</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果对话框应由其父窗口拥有，则设置为 **True**（在通过 **初始化** 方法创建对话框时稍后给出父窗口）。
</td></tr><tr><td>
暂停</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果要显示 *Pause* 按钮，则设置为 **True**。
</td></tr><tr><td>
跳过</td><td>

*bool*</td><td>

在调用 **初始化** 之前，如果应显示 *Skip* 按钮，则设置为 **True**。 （这只是为了使 *Skip* 按钮可以启用。您仍然必须稍后调用 **EnableSkip** 才能实际启用它；通常每个文件启用一次。）
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
添加文件</td><td>

\<int:count\>  
\<**[文件大小](filesize.zh.md)**:bytes\></td><td>

*无*</td><td>

将指定的文件数添加到操作总数。 *bytes* 参数是可选的 - 在“全尺寸”进度指示器中，这允许您添加到操作的总字节数。
</td></tr><tr><td>
清除中止状态</td><td>

*无*</td><td>

*无*</td><td>

清除三个“控制”按钮（*中止* / *暂停* / *跳过*）的状态，以便当调用 **获取中止状态** 时，它们不再注册为被单击。  
如果您只想清除 *Skip* 状态，通常应该在调用 **EnableSkip** 时作为调用的一部分来执行此操作。这样，您可以避免在您调用 **获取中止状态** 和 **清除中止状态** 之间设置它们时意外清除其他状态之一。事实上，调用 **清除中止状态** 的情况非常少。
</td></tr><tr><td>
启用跳过</td><td>

*\<*bool:enable\>  
*\<*bool:delay\>  
*\<*bool:clear\></td><td>

*无*</td><td>

启用进度对话框的 *Skip* 按钮。要使用 **EnableSkip**，您必须在进度对话框由 **初始化** 方法创建之前，将 **skip** 属性设置为 **True**。  
**enable**：如果为 **True**，则应启用 *Skip* 按钮；否则，应禁用它。  
**延迟**（可选，默认为 **True**）：如果为 **True**，则在启用 *Skip* 按钮之前会有一个短暂的延迟，在此期间暂时禁用它；否则，更改将立即生效。有关为何延迟通常是一个好主意，请参见下方。  
**清除**（可选，默认为 **True**）：如果为 **True**，将清除用户按 *Skip* 的任何记录，以便 **获取中止状态** 不再返回 **“s”**。如果您要跳过刚刚移动到新项目的进度对话框，则通常希望这样做。  
如果您支持 *Skip* 按钮，通常应该在调用 **SetName** 和类似方法之后，每个文件调用一次 **EnableSkip**。以这种方式使用时，您通常希望 **延迟** 和 **清除** 都为 **True**，否则对一个文件所做的 *Skip* 按钮的单击可能影响其后的文件。例如，如果一个文件需要很长时间才能完成，但就在用户厌烦等待并单击 *Skip* 时完成，则延迟和已清除状态可确保不需要的单击无害。
</td></tr><tr><td>
完成文件</td><td>

*无*</td><td>

*无*</td><td>
完成当前文件。如果已经设置当前文件的字节大小，则总进度将按任意剩余字节推进。
</td></tr><tr><td>
获取中止状态</td><td>

\<bool:autoPause\>  
\<string:wanted\>  
\<bool:simple\></td><td>

*字符串*</td><td>

轮询三个“控制”按钮的状态。这返回一个 *字符串*，指示三个按钮中是否有任何按钮被用户单击。按钮状态由返回字符串中以下字母表示：

**a** - 中止  
**p** - 暂停  
**s** - 跳过

如果应用了 none of the states，则返回一个空字符串。  
**autoPause**（可选，默认为 **False**）：如果为 **True**，则暂停将自动为您处理。对 **GetAbortState(True)** 的调用在暂停时会阻塞，直到取消暂停才返回；永远不会返回“**p**”状态。（请注意，单击 *Skip* 或 *Abort* 会隐式取消暂停操作。）  
**wanted**（可选）：如果您只想检查其中一个或两个状态，请传递一个包含它们字母的字符串。例如，**GetAbortState(True,"ap")** 将测试 *Abort* 和 *Pause* 状态，但不测试 *Skip* 状态。如果参数是一个空字符串或根本没有给出，则将检查所有状态。  
**simple**（可选，默认为 **True**）：如果为 **True**，则结果字符串最多只有一个字母，指示最重要的状态。如果为 **False**，则可能会同时指示多个状态。例如，如果依次单击 *Skip*，然后单击 *Pause*，而脚本未清除 *Skip* 状态，则 **GetAbortState(False,"",False)** 将返回“**ps**”，而 **GetAbortState(False)** 将仅返回“**p**”。  
要清除三个按钮的状态，请调用 **ClearAbortState** 方法。要仅清除 *Skip* 按钮的状态，请使用 **EnableSkip** 方法。
</td></tr><tr><td>
隐藏</td><td>

*无*</td><td>

*无*</td><td>

隐藏进度指示器对话框。对话框对象本身仍然有效，如果需要，可以使用 **显示** 方法重新显示它。
</td></tr><tr><td>
隐藏文件字节数</td><td>

*\<*bool:show\></td><td>

*无*</td><td>

在进度对话框中隐藏或显示 “*XX bytes / YY bytes*”字符串。您可以使用它来隐藏字符串，如果进度不表示字节数（例如，当它表示百分比时）。传递 **True** 作为 *show* 参数以显示字符串，传递 **False** 以隐藏它。
</td></tr><tr><td>
Init</td><td>

\<**[Tab](tab.zh.md)**:parent\>  
或 \<**[文件窗口](lister.zh.md)**:parent\>

\<string:title\></td><td>

*无*</td><td>

初始化该对话框。此方法将导致创建实际的对话框，但直到 **Show** 方法被调用前它将不会被显示出来。必须在调用此方法前设置上面所示的基本属性 - 在该对话框被创建后它们不能被改变。  
*父级* 参数可以是 **[Tab](tab.zh.md)** 或 **[文件窗口](lister.zh.md)**- 这控制着对话框居中于哪个窗口，并且如果 **owned** 属性被设置为 **True**，则控制着该对话框归属哪个窗口（始终显示在上方）。如果没有提供父级，该对话框将不会与任何特定窗口关联。  
*title* 参数指定该对话框的窗口标题。
</td></tr><tr><td>
InitFileSize</td><td>

*无*</td><td>

*无*</td><td>
将当前文件的字节数重置为零。
</td></tr><tr><td>
Restart</td><td>

*无*</td><td>

*无*</td><td>
将总已完成的文件数和字节数重置为零。
</td></tr><tr><td>
SetBytesProgress</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*无*</td><td>
设置总已完成字节数。
</td></tr><tr><td>
SetFileSize</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*无*</td><td>
设置当前文件的字节长度。
</td></tr><tr><td>
SetFiles</td><td>

\<int:count\></td><td>

*无*</td><td>
设置总文件数。
</td></tr><tr><td>
SetFilesProgress</td><td>

\<int:count\></td><td>

*无*</td><td>
设置总已完成文件数。
</td></tr><tr><td>
SetFromTo</td><td>

\<string:header\>  
\<string:from\>  
\<string:to\></td><td>

*无*</td><td>

设置对话框顶部指示操作的源和目标的文本。*header* 参数参考通常表示 *From:* 的字符串 - 它允许你在该术语不适用于你的操作时更改它。*from* 参数是源路径，*to* 参数（如果有的话）是目标路径。请注意，如果你指定了一个目标路径，那么该路径始终有一个 *To:* header 附加在它后面。  
如果你完全省略了 *to* 参数（不仅仅是传递了一个空字符串），那么目标行将变为空白，包括 *To:* header。当你想在某些时候使用第二行但并非始终都使用它时，请使用该功能。如果你永远都不希望在第二行有任何内容，那么请使用 **SetStatus** 方法，因为它不会为额外的行添加空间。
</td></tr><tr><td>
SetName</td><td>

\<string:name\></td><td>

*无*</td><td>
设置当前文件的名称。
</td></tr><tr><td>
SetPercentProgress</td><td>

\<int:percent\></td><td>

*无*</td><td>
将当前进度设置为百分比（从 0 到 100）。
</td></tr><tr><td>
SetStatus</td><td>

\<string:status\></td><td>

*无*</td><td>
设置对话框顶部状态行中显示的文本。  
这将设置单行状态消息，而 **SetFromTo** 可用于在两行上指示源路径和目标路径。
</td></tr><tr><td>
SetTitle</td><td>

\<string:title\></td><td>

*无*</td><td>
设置对话框的标题。
</td></tr><tr><td>
SetType</td><td>

\<string:type\></td><td>

*无*</td><td>
设置当前项的类型 - *file* 或 *dir*。
</td></tr><tr><td>
Show</td><td>

*无*</td><td>

*无*</td><td>

显示进度指示器对话框。在使用 **Init** 方法创建对话框后，调用此方法。
</td></tr><tr><td>
SkipFile</td><td>

\<bool:complete\></td><td>

*无*</td><td>
跳过当前文件。将 *complete* 参数设置为 **True** 以将该文件计为“已完成”，或设置为 **False** 以将其计为“已跳过”。
</td></tr><tr><td>
StepBytes</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*无*</td><td>
将字节进度指示器按指定字节数前进。
</td></tr><tr><td>
StepFiles</td><td>

\<int:count\></td><td>

*无*</td><td>
将文件进度指示器按指定文件数前进。
</td></tr></tbody>
</table>