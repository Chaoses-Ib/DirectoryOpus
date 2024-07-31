# Progress

**Progress** 对象可用于显示和控制标准 Directory Opus 进度指示器对话框。此对象可从 **[Command](command.zh.md).progress** 属性获取。使用 **Progress** 对象的基本步骤如下：

1. 初始化基本属性。
2. 调用 **Init** 方法创建对话框（这会创建对话框，但不会将其显示给用户）。
3. 准备就绪后，调用 **Show** 方法使对话框可见。
4. 调用适当的方法初始化进度条的状态（通过设置文件总数、总字节大小等）。
5. 随着操作的进行，使用诸如 **StepFiles** 和 **StepBytes** 之类的 方法推进进度条。
6. 如果适用，使用 **GetAbortState** 轮询 *Abort* 和其它控制按钮的状态。
7. 操作完成后，调用 **Hide** 方法并销毁对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
abort</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示 *Abort* 按钮应可用，或设置为 **False** 以禁用它。
</td></tr><tr><td>
bytes</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示对话框应以字节而不是整个文件列表进度。
</td></tr><tr><td>
delay</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示在调用 **Show** 方法后，对话框应延迟一段时间才会出现。延迟由用户在配置中配置。
</td></tr><tr><td>
full</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 以启用具有两个单独进度条（一个用于文件，一个用于字节）的“全尺寸”进度指示器。
</td></tr><tr><td>
owned</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示对话框应由其父窗口拥有（父窗口在对话框通过 **Init** 方法创建时给出）。
</td></tr><tr><td>
pause</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示 *Pause* 按钮应可用。
</td></tr><tr><td>
skip</td><td>

*bool*</td><td>

在调用 **Init** 之前，设置为 **True** 表示 *Skip* 按钮应可用。（这仅意味着 *Skip* 按钮可以启用。你仍然必须稍后调用 **EnableSkip** 以实际启用它；通常每个文件调用一次）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddFiles</td><td>

\<int:count\>  
\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*none*</td><td>

将指定数量的文件添加到操作总数。*bytes* 参数是可选的 - 在“全尺寸”进度指示器中，这使你能够将操作的总字节大小添加进去。
</td></tr><tr><td>
ClearAbortState</td><td>

*none*</td><td>

*none*</td><td>

清除三个“控制”按钮（*Abort* / *Pause* / *Skip*）的状态，以便在调用 **GetAbortState** 时不再将其注册为已单击。  
如果你只想清除 *Skip* 状态，你通常应该在调用 **EnableSkip** 的过程中清除它。这样你就可以避免在调用 **GetAbortState** 和 **ClearAbortState** 之间，意外清除其它状态之一。实际上，很少有情况下需要调用 **ClearAbortState**。
</td></tr><tr><td>
EnableSkip</td><td>

*\<*bool:enable\>  
*\<*bool:delay\>  
*\<*bool:clear\></td><td>

*none*</td><td>

启用进度对话框的 *Skip* 按钮。要使 **EnableSkip** 工作，你必须在进度对话框通过 **Init** 方法创建之前将 **skip** 属性设置为 **True**。  
**enable**: 如果为 **True**，则应启用 *Skip* 按钮；否则，应禁用它。  
**delay**（可选，默认情况下为 **True**）：如果为 **True**，则启用 *Skip* 按钮之前会有短暂的延迟，并且在延迟期间暂时禁用它；否则，更改会立即生效。请参阅下文了解为什么延迟通常是好主意。  
**clear**（可选，默认情况下为 **True**）：如果为 **True**，则将清除用户按下 *Skip* 的任何记录，这样 **GetAbortState** 就不再返回 "**s**"。如果进度对话框刚刚移至新项目，你通常希望这样做。  
如果你支持 *Skip* 按钮，你通常应该每个文件调用 **EnableSkip** 一次，就在调用 **SetName** 和类似方法之后。当你以这种方式使用时，你通常希望 **delay** 和 **clear** 都为 **True**，否则，针对一个文件的 *Skip* 按钮的点击可能会影响随后的文件。例如，如果一个文件需要很长时间，但就在用户厌烦等待并点击 *Skip* 时完成，则延迟和清除状态可确保不必要的点击无害。
</td></tr><tr><td>
FinishFile</td><td>

*none*</td><td>

*none*</td><td>
完成当前文件。如果当前文件的字节大小已设置，则总进度将按任何剩余字节推进。
</td></tr><tr><td>
GetAbortState</td><td>

\<bool:autoPause\>  
\<string:wanted\>  
\<bool:simple\></td><td>

*string*</td><td>

轮询三个“控制”按钮的状态。这将返回一个 *string*，指示三个按钮中的哪一个（如果有）已被用户单击。按钮状态由返回字符串中的以下字母表示：

**a** - Abort  
**p** - Pause  
**s** - Skip

如果没有任何状态适用，则返回空字符串。  
**autoPause**（可选，默认情况下为 **False**）：如果为 **True**，则会自动为你处理暂停。调用 **GetAbortState(True)** 会在暂停时阻塞，并且只有在取消暂停后才会返回；永远不会返回 "**p**" 状态。（注意，单击 *Skip* 或 *Abort* 会隐式取消暂停操作）。  
**wanted**（可选）：如果你只想检查一两个状态，请传递一个包含其字母的字符串。例如，**GetAbortState(True,"ap")** 将测试 *Abort* 和 *Pause* 状态，但不会测试 *Skip* 状态。如果没有给出参数或参数为空字符串，则将检查所有状态。  
**simple**（可选，默认情况下为 **True**）：如果为 **True**，则结果字符串最多包含一个字母，表示最重要的状态。如果为 **False**，则可以同时指示多个状态。例如，如果依次单击 *Skip* 然后 *Pause*，并且脚本没有清除 *Skip* 状态，则 **GetAbortState(False,"",False)** 将返回 "**ps**"，而 **GetAbortState(False)** 将只返回 "**p**"。  
要清除三个按钮的状态，请调用 **ClearAbortState** 方法。要清除 *Skip* 按钮的状态，请使用 **EnableSkip** 方法。
</td></tr><tr><td>
Hide</td><td>

*none*</td><td>

*none*</td><td>

隐藏进度指示器对话框。对话框对象本身仍然有效，如果需要，可以使用 **Show** 方法重新显示它。
</td></tr><tr><td>
HideFileByteCounts</td><td>

*\<*bool:show\></td><td>

*none*</td><td>

隐藏或显示进度对话框中的 *"XX bytes / YY bytes"* 字符串。如果进度不指示字节数（例如，当它指示百分比时），你可以使用它来隐藏字符串。将 *show* 参数传递 **True** 以显示字符串，传递 **False** 以隐藏它。
</td></tr><tr><td>
Init</td><td>

\<**[Tab](tab.zh.md)**:parent\>  
or \<**[文件窗口](lister.zh.md)**:parent\>

\<string:title\></td><td>

*none*</td><td>

初始化对话框。此方法会导致实际对话框创建，但它不会显示，直到调用 **Show** 方法。在调用此方法之前必须设置上面显示的基本属性 - 一旦对话框创建，就不能再更改它们。  
*parent* 参数可以是 **[Tab](tab.zh.md)** 或 **[文件窗口](lister.zh.md)** - 这将控制对话框居中显示在哪个窗口上，以及如果 **owned** 属性设置为 **True**，则控制对话框由哪个窗口拥有（始终显示在顶部）。如果没有提供父级，则对话框将不会与任何特定窗口关联。  
*title* 参数指定对话框的窗口标题。
</td></tr><tr><td>
InitFileSize</td><td>

*none*</td><td>

*none*</td><td>
将当前文件的字节计数重置为零。
</td></tr><tr><td>
Restart</td><td>

*none*</td><td>

*none*</td><td>
将总已完成的文件和字节计数重置为零。
</td></tr><tr><td>
SetBytesProgress</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*none*</td><td>
设置总已完成的字节计数。
</td></tr><tr><td>
SetFileSize</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*none*</td><td>
设置当前文件的大小。
</td></tr><tr><td>
SetFiles</td><td>

\<int:count\></td><td>

*none*</td><td>
设置文件的总数。
</td></tr><tr><td>
SetFilesProgress</td><td>

\<int:count\></td><td>

*none*</td><td>
设置总已完成的文件计数。
</td></tr><tr><td>
SetFromTo</td><td>

\<string:header\>  
\<string:from\>  
\<string:to\></td><td>

*none*</td><td>

设置对话框顶部显示源和目标的操作文本。*header* 参数指的是通常显示 *From:* 的字符串 - 这使你能够在该术语不适用于你的操作的情况下更改它。*from* 参数是源路径，而 *to* 参数（如果有）是目标路径。请注意，如果你指定目标路径，则始终会在其后附加 *To:* 标题。  
如果你完全省略 *to* 参数（不只是传递空字符串），则目标行将变为空白，包括 *To:* 标题。如果希望第二行有时使用，有时不使用，请使用这种方法。如果你永远不希望第二行有任何内容，请使用 **SetStatus** 方法，因为它不会为额外的行添加空格。
</td></tr><tr><td>
SetName</td><td>

\<string:name\></td><td>

*none*</td><td>
设置当前文件的名称。
</td></tr><tr><td>
SetPercentProgress</td><td>

\<int:percent\></td><td>

*none*</td><td>
将当前进度设置为百分比（从 0 到 100）。
</td></tr><tr><td>
SetStatus</td><td>

\<string:status\></td><td>

*none*</td><td>

设置对话框顶部状态行中显示的文本。  
这将设置单行状态消息，而 **SetFromTo** 可以用于在两行上指示源和目标路径。
</td></tr><tr><td>
SetTitle</td><td>

\<string:title\></td><td>

*none*</td><td>
设置对话框的标题。
</td></tr><tr><td>
SetType</td><td>

\<string:type\></td><td>

*none*</td><td>

设置当前项目的类型 - *file* 或 *dir*。
</td></tr><tr><td>
Show</td><td>

*none*</td><td>

*none*</td><td>

显示进度指示器对话框。在使用 **Init** 方法创建对话框后，调用此方法。
</td></tr><tr><td>
SkipFile</td><td>

\<bool:complete\></td><td>

*none*</td><td>

跳过当前文件。将 *complete* 参数设置为 **True** 表示该文件应计为“已完成”，或设置为 **False** 表示该文件应计为“已跳过”。
</td></tr><tr><td>
StepBytes</td><td>

\<**[FileSize](filesize.zh.md)**:bytes\></td><td>

*none*</td><td>
将字节进度指示器推进指定的字节数。
</td></tr><tr><td>
StepFiles</td><td>

\<int:count\></td><td>

*none*</td><td>
将文件进度指示器推进指定的文件数。
</td></tr></tbody>
</table>