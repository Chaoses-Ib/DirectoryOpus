**Dialog** 对象允许您显示对话框，这些对话框会提示用户进行确认、允许他们输入文本字符串或密码，并选中复选框选项或从下拉列表中选择。您还可以使用该对象在屏幕上显示弹出菜单。

您可以从 **[DOpus](dopus.zh.md).Dlg**, **[文件窗口](lister.zh.md).Dlg**, **[Tab](tab.zh.md).Dlg**, **[Func](func.zh.md).Dlg** 和 **[Command](command.zh.md).Dlg** 方法创建 **Dialog** 对象。

有关其使用示例，请参见 [示例脚本](/Manual/scripting/example_scripts/README.zh.md) 部分。

有两种不同的方法可以使用 **Dialog** 对象。您可以：

- 使用一击式方法（**Folder**、**GetString**、**Multi**、**Open**、**Request** 或 **Save**）来显示各种类型的简单对话框，或
- 首先通过设置各种属性的值配置对话框，然后调用 **Show** 函数显示它。此方法还允许您创建和使用 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)。

一击式方法接受多个参数，但通常不如构建对话框然后调用 **Show** 灵活。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
buttons</td><td>

*string*</td><td>

指定显示在对话框底部的按钮。这些按钮用于关闭对话框。**Show** 方法返回一个值，指明选择了哪个按钮（此值也在 **result** 属性中提供）。

多个按钮字符串必须用竖线字符 (\|) 分隔。如果一个按钮有多个按钮，那么按照定义，最后一个是“取消”按钮。例如：

    dlg.buttons = "OK|Retry|Cancel"

要为按钮指定*加速器*，请用一个和号 (&) 字符作为想要按键的前缀。例如：

    dlg.buttons = "&OK|&Retry|&Cancel"

按钮还可以附带下拉菜单，用加号 (+) 分隔下拉菜单项。例如：

    dlg.buttons = "OK|Retry+Retry All|Cancel"

在下拉菜单中，您可以指定通过按住 <kbd>Shift</kbd>、<kbd>Ctrl</kbd> 或 <kbd>Shift+Ctrl</kbd> 可以直接从主按钮访问某些菜单项。这可以通过添加一个等号，然后添加按钮按住该键后显示的标签（通常是菜单项标签的缩写，或者如果该标签本身已经足够短，则重复该标签）来完成。这些键会被自动分配，并且您至多只能对三个项执行此操作。例如：

\<WRAP prewrap\>

    dlg.buttons = "OK|Retry+Retry All=Retry All|Skip+Skip if same modified time=Skip Same Time|Cancel"

\</WRAP\>
</td></tr><tr><td>
choices</td><td>

*object:***[Vector](vector.zh.md)***(string)*  
或 *array(string)*</td><td>

该属性使用 **[Vector](vector.zh.md)** 或字符串数组来提供可以向用户显示的多个选项的列表。该列表可以以下三种方式之一显示：

- **下拉列表**：默认情况下，对话框会显示一个下拉列表，允许用户选择一个选项。当 **Show** 方法返回时，可以通过 **selection** 属性获得所选选项的索引。
- **复选框列表**：如果同时给出了 **list** 属性，则对话框会显示一个滚动项列表，每个项都有一个复选框，允许将其打开或关闭。
- **弹出菜单**：如果同时给出了 **menu** 属性，则会在当前鼠标坐标处显示一个弹出菜单。使用单连字符（“-”）作为菜单标签插入分隔符。

当以复选框列表形式显示时，对话框是可调整大小的；您可以使用 **cx** 和 **cy** 属性设置初始大小（如果要保存大小，可以在之后检索它们）。
</td></tr><tr><td>
confirm</td><td>

*bool*</td><td>

在文本输入对话框中（即已指定 **max** 属性），将 **confirm** 设置为 **True** 将要求用户在另一个文本字段中再次键入输入的文本以确认（例如，用于密码）。
</td></tr><tr><td>
cx</td><td>

*int*</td><td>

对于标记为可调整大小的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)，该属性允许您重写资源中定义的对话框的宽度 - 虽然请注意，您不能将对话框的大小调整为小于其初始大小。
</td></tr><tr><td>
cy</td><td>

*int*</td><td>

对于标记为可调整大小的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)，该属性允许您重写资源中定义的对话框的高度 - 虽然请注意，您不能将对话框的大小调整为小于其初始大小。
</td></tr><tr><td>
defvalue</td><td>

*string*</td><td>

在文本输入对话框中（即已指定 **max** 属性），该属性允许您使用默认值初始化文本字段。

（旧脚本可以使用“default”而不是“defvalue”；这不推荐，因为它在 JScript 中不起作用，因为“default”是保留关键字。）
</td></tr><tr><td>
defid</td><td>

*int*</td><td>

允许您更改对话框中的默认按钮（即用户按下 enter 时将发生的动作）。通常第一个按钮是默认按钮 - 此按钮的 **defid** 为 1。第二个按钮的 **defid** 将为 2，以此类推。如果一个对话框有多个按钮，那么按照定义，最后一个按钮是“取消”按钮，它的 **defid** 为 0。
</td></tr><tr><td>
detach</td><td>

*bool*</td><td>

如果您希望 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 以“分离”模式运行，则设置为 **True**，在该模式下您的脚本提供其 [消息循环](/Manual/scripting/script_dialogs/the_dialog_message_loop/README.zh.md)。
</td></tr><tr><td>
disable_window</td><td>

*object:***[文件窗口](lister.zh.md)**  
或 *object:***[Tab](tab.zh.md)**   
*或 object:***Dialog\\** 或 *int*</td><td>

用这个来让对话框在显示时自动禁用另一个窗口。在对话框关闭之前，用户将无法在禁用的窗口中单击或键入。通常，如果您使用此设置，您会将其设置为与 **window** 属性相同的值。

您可以提供一个 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象，或另一个 **Dialog**。如果您作为对 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 事件的响应显示此对话框，还可以传递 **[AboutData](aboutdata.zh.md).window** 属性的值。
</td></tr><tr><td>
icon</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

在对话框的左上角显示几个标准的图标之一，例如，可以用来指示错误条件的严重性。此属性的有效值为 *warning、error、info* 和 *question*。

当与 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 一起使用时，该属性允许您控制对话框标题栏中显示的图标。在这种情况下，您也可以提供一个 **[Image](image.zh.md)** 对象，而不是字符串，您可以从 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法获取该对象。请注意，该图像必须是从 **.ico** 文件中加载的。
title</td><td>

*string*</td><td>

This property specifies the title of the dialog to display.
</td></tr><tr><td>
x</td><td>

*int*</td><td>

When the **position** property is set to **absolute**, **parent**, or **monitor** this property is used to control the x-position of the dialog on-screen. All other values for **position** ignore this property.
</td></tr><tr><td>
y</td><td>

*int*</td><td>

When the **position** property is set to **absolute**, **parent**, or **monitor** this property is used to control the y-position of the dialog on-screen. All other values for **position** ignore this property.
</td></tr>
**标题**</td><td>

*字符串*</td><td>

指定对话框的标题文本。
</td></tr><tr><td>

顶部</td><td>

布尔值</td><td>

将此属性设置为 **True** 可使对话框称为“顶级”，或设置为 **False** 以允许其表示在其他非顶级窗口后面。
</td></tr><tr><td>

希望关闭</td><td>

*布尔值*</td><td>

当用户单击窗口关闭按钮时，如果您希望脚本对话框在您的消息循环中生成关闭事件，请将此属性设置为 **True**。您将需要使用 **EndDlg** 方法自行关闭对话框。
</td></tr><tr><td>

希望调整大小</td><td>

*布尔值*</td><td>

如果您希望脚本对话框在用户调整对话框大小时在您的消息循环中生成 **调整大小** 事件，请将此属性设置为 **True**。
</td></tr><tr><td>

窗口</td><td>

*对象:***[文件窗口](lister.zh.md)**  
或 *对象:***[Tab](tab.zh.md)**  
或 *对象:***Dialog**  
或 *int*</td><td>

使用此属性指定对话框的父窗口。对话框将显示在指定窗口顶部的中心。您可以提供 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象，或另一个 **Dialog**。如果您将在 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 事件中显示此对话框，还可以传递 **[AboutData](aboutdata.zh.md).window** 属性的值。

只有从 **[DOpus](dopus.zh.md).Dlg** 方法获取 **Dialog** 选项时，才需要设置此属性。如果 **Dialog** 对象来自其他对象之一（例如 **[Tab](tab.zh.md).Dlg**），则其父窗口将已经设置为启动您脚本响应的操作的窗口。
</td></tr><tr><td>

x</td><td>

*int*</td><td>

指定[脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的 x 位置。使用 **position** 属性控制如何解释位置。在显示对话框后，您可以更改此属性以在屏幕上移动对话框。
</td></tr><tr><td>

y</td><td>

*int*</td><td>

指定[脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的 y 位置。使用 **position** 属性控制如何解释位置。在显示对话框后，您可以更改此属性以在屏幕上移动对话框。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
添加热键</td><td>

\<字符串:名称\>  
\<字符串:键\></td><td>

*无*</td><td>

为指定键组合创建热键（或键盘加速器）。当用户在您的对话框中按此键组合时，将触发 **热键** 事件。

name 参数是您分配的用以标识热键的名称。key 参数指定了实际的键组合；这可以可选地将限定符 **ctrl**、**shift** 和 **alt** 与字符或特殊键的名称组合起来。例如，**ctrl+t** 或 **alt+shift+F7**。
</td></tr><tr><td>
自动调整大小</td><td>

*无*</td><td>

*无*</td><td>
如果对话框具有自动调整大小的控件，这些控件取决于其他控件的大小，并且您正在运行时更改其大小，则可以在完成所需更改后调用此方法以强制对话框重新计算所有相对控件大小。
</td></tr><tr><td>
取消监视目录</td><td>

\<字符串:id\></td><td>

*无*</td><td>

取消由调用 **WatchDir** 方法先前建立的文件夹或文件更改监视。**id** 参数是您在创建观察器时分配给它的 ID。
</td></tr><tr><td>
创建</td><td>

*无*</td><td>

*无*</td><td>

在创建[脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 时，调用此方法将创建底层对话框，但不会显示它。这使您可以在显示对话框给用户之前创建对话框然后初始化其控件。

使用 **Create** 意味着[分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md)；**detach** 属性将自动设置为 **True**。但是，如果您不需要自定义消息循环，并且只是希望在显示对话框之前设置一些控件，则可以在之后调用 **RunDlg**。

在创建对话框并初始化其控件后，您应该调用 **Show** 或 **RunDlg** 以使其对用户可见。如果尚未显示，它还将首次 **GetMsg** 调用时显示。
</td></tr><tr><td>
创建字体</td><td>

\<字符串:名称\>  
\[\<int:大小\>\]  
\[\<字符串:样式\>\]</td><td>

*int*</td><td>

创建一个字体对象，可以将其提供给对话框控件，以使其使用非标准字体。*name* 参数指定字体的名称（例如，“Arial”） - 您还可以使用“\*”，表示默认的对话框字体。*size* 参数指定所需的点数大小（使用 0 以获取默认的对话框字体大小）。*styles* 字符串可以由一个或多个字符组成，表示所需的字体样式 - “b” 表示粗体，“i” 表示斜体，“u” 表示下划线。

返回值可以与 **[Control](control.zh.md).SetFont** 方法一起使用。

创建的字体会在对话框关闭时自动销毁，但如果您想手动删除它们以释放资源，请使用 **DestroyFont** 方法。
</td></tr><tr><td>
控件</td><td>

\<字符串:名称\>  
\[\<字符串:对话框\>\]  
\[\<字符串:标签页\>\]</td><td>

*对象:***[Control](control.zh.md)**</td><td>

返回与脚本对话框上的某个控件对应的 **[Control](control.zh.md)** 对象。该控件由其名称标识，如脚本对话框资源中定义的那样。

可选的第二个和第三个参数仅在控件位于*标签页控件*中（即，当它位于另一个对话框的子对话框中）时使用。*dialog* 参数指定其父对话框的名称。*tab* 参数指定托管子对话框的标签页控件的名称。您只需要在具有多个标签页控件并在其中多个控件内部托管同一个对话框的情况下指定标签页的名称（这种情况很罕见）。

请注意，在调用 **Create** 之前，任何控件都不会存在。
</td></tr><tr><td>
删除热键</td><td>

\<字符串:名称\></td><td>

*无*</td><td>

删除您之前使用 **AddHotkey** 方法创建的热键。
</td></tr><tr><td>
拖动</td><td>

*对象:***[Items](items.zh.md)**  
\<字符串:动作\></td><td>

*字符串*</td><td>

允许用户从您的对话框拖放一个或多个文件（并将其放到其他窗口或应用程序中）。

通常，您会在收到 **static** 或列表视图控件发送的 **拖动** 事件时调用此方法。

第一个参数是一个 **[Items](items.zh.md)** 对象，表示要拖动的文件。（您还可以传递 **[Vector](vector.zh.md)** 的 **[Item](item.zh.md)** 或 **[Path](path.zh.md)** 对象，或完整路径字符串，而不是 **[Items](items.zh.md)** 对象。或 **[StringSet](stringset.zh.md)** 或 **[UnorderedSet](unorderedset.zh.md)** 包含完整路径字符串。）

可选的第二个参数允许您控制哪些操作可用。这应包含 **copy**、**move**、**link** 中的一个或多个字符串。可以通过前缀 \*（例如 **copy,\*move,link**）指示默认操作。如果您不指定此参数，则默认为仅允许 **copy**。
此方法返回的字符串指示了拖拽的结果。对于左键拖拽，结果将是“复制”、“移动”、“链接”或“删除”。对于右键拖拽，结果将始终是“删除”。如果拖拽被取消，则将返回“取消”。
</td></tr><tr><td>
DestroyFont</td><td>

\<int:id\></td><td>

*none*</td><td>

使用由 **CreateFont** 方法返回的 ID 销毁指定的字体。
</td></tr><tr><td>
EndDlg</td><td>

\<int:result\></td><td>

*none*</td><td>

结束在分离模式下运行的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)。在用户单击关闭按钮或其 **关闭对话框** 属性设置为 **True** 的另一个按钮时，对话框通常会自动结束。通过此方法，可以结束脚本当中的对话框。可选参数指定 **Dialog.result** 属性将返回的结果代码。
</td></tr><tr><td>
Folder</td><td>

\<string:title\>  
\<string:default\>  
\<bool:expand\>  
\<object:window\></td><td>

*object:***[Path](path.zh.md)**</td><td>

显示“浏览文件夹”对话框，使用户可以选择一个文件夹。可选参数为：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认路径
- *expand* - 指定 **True** 以自动展开初始路径
- *window* - 为对话框指定父窗口 (**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**)。如果不指定，将使用 **Dialog** 对象的 **window** 属性。

**[Path](path.zh.md)** 对象将返回以指示用户选择的文件夹。如果用户取消对话框，此对象将具有一个附加的 **result** 属性，该属性的值为 **False** - 只有在 **result** 为 **True** 时，其他正常的 **Path** 属性才有效。
</td></tr><tr><td>
GetMsg</td><td>

*none*</td><td>

*object:***[Msg](msg.zh.md)**</td><td>

返回一个 **[Msg](msg.zh.md)** 对象，表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中最近的输入事件 (仅在 [分离模式](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md) 下使用)。

当关闭对话框时，返回值将求值为 **False**，此时你应该退出 [消息循环](/Manual/scripting/script_dialogs/the_dialog_message_loop/README.zh.md)。

如果对话框尚未显示 (因为尚未调用 **Show**)，则在你首次调用 **GetMsg** 时它将变为可见。
</td></tr><tr><td>
GetString</td><td>

\<string:message\>  
\<string:default\>  
\<string:max\>  
\<string:buttons\>  
\<string:title\>  
\<object:window\>  
\<byref string:result\></td><td>

*string*</td><td>

显示文本输入对话框，允许用户输入字符串。可选参数为：

- *message* - 指定对话框中的消息字符串
- *default* - 指定默认字符串值
- *max* - 指定最大字符串长度
- *buttons* - 指定按钮标签 (格式与上述描述的 **buttons** 属性相同)
- *title* - 指定对话框窗口标题
- *window* - 为对话框指定父窗口 (**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**)。如果不指定，将使用 **Dialog** 对象的 **window** 属性。
- *result* - 对于支持 *ByRef* 参数的脚本语言，可以指定一个变量来接收用户输入的字符串。

返回值是输入的字符串，如果取消对话框，则为空值。此方法返回之后，用户选择的按钮的索引将通过 **result** 属性提供。最左边的按钮索引为 **1**，下一个按钮索引为 **2**，以此类推。如果对话框有多个按钮，则根据定义，最后一个 (最右边的) 按钮是“取消”按钮，因此它将返回索引 **0**。
</td></tr><tr><td>
KillTimer</td><td>

\<string:name\></td><td>

*none*</td><td>

停止指定的计时器。计时器之前必须已通过调用 **SetTimer** 方法创建。
</td></tr><tr><td>
LoadPosition</td><td>

\<string:id\>  
\<string:type\></td><td>

*none*</td><td>

恢复 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的先前保存的位置。必须先通过调用 **SavePosition** 方法保存该位置。

**id** 字符串是 Opus 可以用来标识你的对话框或来源脚本的字符串。对话框的模板名称将自动附加到此字符串。例如，你可以将 **id** 指定为 *"kundal"* - 然后 Opus 将在内部将名为 *"dialog1"* 的对话框的位置保存为 *"kundal!dialog1"*. 确保选择其他脚本作者不太可能使用的字符串，因为 Opus 没有其他方法来区分已保存的位置。

可选类型参数允许你控制哪些位置元素被恢复 - 指定 *"pos"* 仅恢复位置，指定 *"size"* 仅恢复大小，或指定 *"pos,size"* 恢复两者 (这也是默认设置，因此你也可以完全省略该参数)。
</td></tr><tr><td>
Multi</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\></td><td>

*object:***[Items](items.zh.md)**</td><td>

显示“浏览打开文件”对话框，使用户可以选择一个或多个文件。可选参数为：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认文件 (如果指定了文件夹，则指定默认位置，但不会选择文件)
- *window* - 为对话框指定父窗口 (**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**)。如果不指定，将使用 **Dialog** 对象的 **window** 属性。

**[Items](items.zh.md)** 对象将返回以指示用户选择的文件夹。返回的对象将具有一个 **result** 属性，你应该首先检查该属性 - 仅当 **result** 返回 **True** 时，该集合的项目才有效。如果它返回 **False**，则表示用户取消了对话框。
</td></tr><tr><td>
NotifyIcon</td><td>

\<string:method\>  
*arguments...*</td><td>

*none*</td><td>

允许脚本来系统任务栏通知区域中添加图标。

*method* 参数指定四个操作之一，每个操作都有自己的一组参数。

<table>
<thead>
<tr class="header">
<th>方法</th>
<th>参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>add</strong></td>
<td>&lt;icon&gt;,<br />
&lt;tooltip&gt;</td>
<td>将图标添加到工具栏。</td>
</tr>
<tr class="even">
<td><strong>update</strong></td>
<td>&lt;icon&gt;,<br />
&lt;tooltip&gt;</td>
<td>更新图标或工具提示。</td>
</tr>
<tr class="odd">
<td><strong>remove</strong></td>
<td><em>none</em></td>
<td>删除图标。</td>
</tr>
<tr class="even">
<td><strong>notify</strong></td>
<td>&lt;title&gt;,<br />
&lt;message&gt;,<br />
&lt;flags&gt;</td>
<td>显示系统通知消息（或 Windows 7 中的气泡工具提示）。</td>
</tr>
</tbody>
</table>

对于 **add** 和 **update** 方法，*icon* 参数可以是字符串或 **[Image](image.zh.md)** 对象 - 有关详细信息，请参阅上文有关 **icon** 属性的文档。如果已通过此属性为对话框分配了一个图标，则如果没有提供图标，将自动使用该图标。
*tooltip* 参数提供了提示字符串，当用户将鼠标移动到图标上方时，系统将显示此字符串。如果已设置对话框的 **title** 属性，则在未给出明确提示时将使用标题。

**notify** 方法可让你显示与对话框关联的系统通知。此方法类似于 **[DOpus](dopus.zh.md).Notify** 方法 - 有关此方法的更多信息，请参阅对该方法的说明。

脚本添加图标后，用户可以使用鼠标与此图标进行交互。鼠标活动将在对话框的消息循环中生成 **click**、**dblclk** 和 **rclick** 事件。**[Msg](msg.zh.md).control** 属性将设置为 **notifyicon**。

当对话框关闭时，将自动删除该图标。如果资源管理器在添加图标后重新启动，它也会自动还原。

请注意仅支持每个对话框一个图标。
</td></tr><tr><td>
打开</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\></td><td>

*object:***[Item](item.zh.md)**</td><td>

显示“浏览文件以打开”对话框，以便用户可以选择单个文件。可选参数有：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认文件（如果指定文件夹，则此项将指定默认位置，但不会选择任何文件）
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则将使用 **Dialog** 对象的 **window** 属性。

返回一个 **[Item](item.zh.md)** 对象来表示用户选择的文件。该对象将具有一个附加 **result** 属性，如果用户取消了对话框，该属性将为 **False** - 其他正常的 **Item** 属性仅当 **result** 为 **True** 时才有效。
</td></tr><tr><td>
请求</td><td>

\<string:message\>  
\<string:buttons\>  
\<string:title\>  
\<object:window\></td><td>

*int*</td><td>

显示包含一个或多个按钮的对话框。可选参数有：

- *message* - 指定对话框中的消息字符串
- *buttons* - 指定按钮标签（格式与其上文描述的 **buttons** 属性相同）
- *title* - 指定对话框窗口标题
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则将使用 **Dialog** 对象的 **window** 属性。

返回值是用户选择的按钮的索引，且方法返回后，此索引也在 **result** 属性中可用。最左边的按钮索引为 **1**，下一个按钮索引为 **2**，依此类推。如果某个对话框有多个按钮，则根据定义最右侧的按钮为“取消”按钮，因此它将返回索引 **0**。
</td></tr><tr><td>
运行对话框</td><td>

*none*</td><td>

*int*</td><td>

通过接管并运行默认消息循环，将以前 [分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md)转换为非分离对话框。在对话框关闭之前，**RunDlg** 方法将不会返回。如果你使用 **Create** 创建了对话框，以便初始化其控件，但实际上不想运行交互式消息循环，则可以使用此方法。

返回值与对象的 **result** 属性相同，表示用户选择的关闭按钮的索引。

如果对话框尚未显示（因为没有调用 **Show** 或 **GetMsg**），则在你调用 **RunDlg** 时，对话框将变为可见。（兼容性说明：在 Opus 12.22 之前，脚本需要显式调用 **Show**。）
</td></tr><tr><td>
保存</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\>  
\<string:type\></td><td>

*object:***[Path](path.zh.md)**</td><td>

显示“浏览文件以保存”对话框，以便用户可以选取单个文件或输入新的文件名进行保存。可选参数有：

- *title* - 对话框标题。
- *default* - 对话框中选择的默认文件。（如果给出文件夹，则它会设置对话框的起始位置，但不会选择任何文件。）
- *window* - 对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则将使用 **Dialog** 对象的 **window** 属性。（如果你不想要使用该 *window* 参数，则可以完全省略它；如果使用了 *type* 参数，它无论处于第三还是第四位都能起作用。）
- *type* - 一系列文件类型，可用来填充保存对话框中的“另存为类型”下拉菜单。（见下文。）

可选的 *type* 参数由一个或多个字符串对组成，每个字符串对由感叹号（**!**）分隔。每一对的第一个字符串为下拉菜单中显示的纯文本字符串，每一对的第二个字符串为实际文件扩展名。你还可以通过分号将其分隔开来，从而为同一种类型指定多个扩展名。如果你希望将默认“所有文件”项添加到列表，则可在字符串开头添加 **\#** 字符。例如， *\#文本文件!\*.txt!文档文件!\*.doc.*

返回一个 **[Path](path.zh.md)** 对象，表示用户选择的文件。该对象将具有一个附加 **result** 属性，如果用户取消了对话框，该属性将为 **False**，并且其他正常的 **Path** 属性仅当 **result** 为 **True** 时才有效。
</td></tr><tr><td>
保存位置</td><td>

\<string:id\></td><td>

*none*</td><td>

将对话框的位置（和大小）保存到 Opus 配置中。然后可以通过调用 **LoadPosition** 在以后恢复位置。

通常，你应该在显示对话框之前调用 **LoadPosition**，并在对话框关闭后调用 **SavePosition**。

**id** 字符串是一个字符串，Opus 可以用它来标识你的对话框或其来源的脚本。对话框的模板名称会自动追加到此字符串。例如，你可以将 **id** 指定为 *"kundal"* - 然后 Opus 会在内部将名为 *"dialog1"* 的对话框的位置保存为 *"kundal!dialog1"*. 请确保选择其他脚本作者不太可能使用的字符串，因为 Opus 没有其他方式来区分已保存的位置。
</td></tr><tr><td>
设定计时器</td><td>

\<int:period\>  
\<string:name\></td><td>

*string*</td><td>

创建计时器，此计时器会为你的脚本生成周期性的 **timer** 事件。**period** 必须以毫秒为单位指定（例如，1000 等于一秒）。

你可以选择为计时器指定 **name** - 如果你没有提供名称，则系统会自动生成一个名称（并且会返回新计时器的名称）。
</td></tr><tr><td>
显示</td><td>

*none*</td><td>

*int*</td><td>

显示使用此对象的各种属性进行预配置的对话框。有关这些属性的完整说明，请参阅上面的“属性”部分。

如果 **detach** 属性为 **False**，则在对话框关闭之前，此调用将不会返回。返回值是用户选择的按钮的索引，且方法返回后，此索引也在 **result** 属性中可用。最左边的按钮索引为 **1**，下一个按钮索引为 **2**，依此类推。如果某个对话框有多个按钮，则根据定义最右侧的按钮为“取消”按钮，因此它将返回索引 **0**。
如果 **detach** 属性为 **True**，调用将立即返回，返回空值。然后，您可以运行一个“detached”对话框的消息循环，或调用 **RunDlg** 运行标准循环。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

用于更改自定义对话框在任务栏上与其他 Opus 窗口分组的方式。指定一个组名以将窗口移至替代组，或省略 group 参数以重置回默认组。如果将一个或多个窗口移至同一个组，它们将被分到一起，与其他默认组分开。

这仅适用于 Windows 7 及以上版本，并且仅在启用任务栏分组时。组名限制在 103 个字符，如果超过则会被截断。组名中的空格和点会自动转换为下划线。

仅适用于自定义脚本对话框（即使用 **template** 属性时）。必须在创建对话框后调用（即在 **Show** 被调用之后 - 如果要避免仅为此编写自己的消息循环，请参阅 **RunDlg** 方法）。

成功时返回 true。
</td></tr><tr><td>
Vars</td><td>

\<string:id\></td><td>

*object:***[Vars](vars.zh.md)**</td><td>

返回一个 **[Vars](vars.zh.md)** 对象，它表示特定对话框的范围变量。这允许脚本从对话框的一种用途持续使用到另一种用途。

**id** 字符串是一个字符串，Opus 可使用其来标识您的对话框或来自该对话框的脚本。对话框的模板名称将自动附加到此字符串。例如，您可以将 **id** 指定为 *"kundal"* - 随后，Opus 会在内部将这些变量保存为名为 *"dialog1"* 的对话框，格式为 *"kundal!dialog1"*. 确保选择其他脚本作者不太可能使用的字符串，因为 Opus 没有其他方法来区分保存的变量。
</td></tr><tr><td>
WatchDir</td><td>

\<string:id\>  
\<string:path\>  
\<string:flags\></td><td>

*int*</td><td>

建立对某个文件夹或文件进行监视以跟踪改动。返回 **0** 表示成功，或在失败时返回一个错误代码。

**id** 参数允许您为该观察器提供一个 ID，当发生变化时用于标识它。**dir** 是一个文件系统文件夹的完整路径，如果设置了 **i** 标志，则可以是文件。

可选标志有：

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **f** | 监视文件夹中的文件更改（例如文件创建）           |
| **d** | 监视文件夹中的目录更改（例如目录创建） |
| **r** | 递归 - 监视子文件夹                                 |
| **a** | 监视文件属性更改                              |
| **s** | 监视文件大小更改                                   |
| **w** | 监视最后写入时间更改                             |
| **i** | 监视单个文件，而不是文件夹                      |

当对受监视的文件或文件夹发生更改时，对话框的消息循环会收到 **dirchange** 事件。**[Msg](msg.zh.md).control** 属性标识观察器的 ID。

使用 **CancelWatchDir** 方法取消监视。
</td></tr><tr><td>
WatchTab</td><td>

\<object:**[Tab](tab.zh.md)**\>  
\<string:events\>  
\<string:id\></td><td>

*bool*</td><td>

允许 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 监视文件夹标签页中的事件。您将通过消息循环收到请求的事件的通知。

**tab** 参数指定要监视的 **[Tab](tab.zh.md)**。**events** 字符串是您要监视的事件的分隔符列表。**id** 字符串是可选参数；它允许您为该标签页指定您自己的 ID，以便于了解事件来自何处（例如，如果您正在监视多个标签页）。

您可以监视的事件如下。请注意，其中一些相当于现有脚本事件（例如 **OnActivateTab**）：

|              |                                                         |
|--------------|---------------------------------------------------------|
| **select**   | 选择或取消选择标签页中的项             |
| **navigate** | 在该标签页中更改文件夹                        |
| **add**      | 添加项到文件夹                           |
| **delete**   | 从文件夹中删除项                       |
| **change**   | 文件夹中的项已更改（大小、日期、名称等） |
| **activate** | 标签页已激活或已停用                            |
| **srcdst**   | 源/目标状态更改                        |
| **view**     | 视图模式已更改                                       |
| **flat**     | 平面视图状态已更改                                 |
| **filter**   | 快速过滤器已更改                                    |

建立通知后，当请求的事件发生时，您将收到所有通知。请注意，没有特定的信息与通知一起发送 - 例如，对于“更改”事件，您不会被告知哪些项已更改，只会知道有所更改。

您将在消息循环中收到通知事件。**[Msg](msg.zh.md)** 对象的各种属性允许您确定发生了什么。

对于来自受监视文件夹标签页的通知，**[Msg](msg.zh.md).event** 属性将设置为 **tab**。

**[Msg](msg.zh.md).control** 属性会告诉您更改发生在哪个标签页中；如果您在调用 **WatchTab** 函数时指定了 ID，则它将位于 [Msg](msg.zh.md)**.control** 属性中 - 否则，它将是标签页的数字句柄。请注意，它\*不是\*实际 **[Tab](tab.zh.md)** 对象。您可以通过 [Msg](msg.zh.md)**.tab** 属性访问 **[Tab](tab.zh.md)** 对象，但此操作可能效率较低，因为它要求每次都创建一个新的 **[Tab](tab.zh.md)** 对象。如果您只监视一个标签页，最好将其 **[Tab](tab.zh.md)** 对象存储在自己的变量中 - 如果您监视多个标签页，则可以为每个标签页使用一个唯一的 ID，并将对象保存在 **[Map](map.zh.md)** 中。

**[Msg](msg.zh.md).value** 属性告诉您发生了哪个通知事件。可能的值包括 **select**、**navigate**、**filechange**、**activate**、**srcdst**、**view**、**flat**、**filter** 和 **close**（如果您在监视标签页时将其关闭，则会发送该事件）。

对于 **filechange** 事件，**[Msg](msg.zh.md).data** 属性包含一个位掩码，表示发生了哪些文件事件。**1** = 添加，**2** = 删除，**4** = 更改。这些值会相加（因此，例如，**6** 表示至少有一项已更改，且至少有一项已删除）。由您的脚本确定具体发生了哪些更改。

您可以再次使用相同的标签和新事件列表调用 **WatchTab** 方法来更改您正在监视的事件。

要停止监视现有标签页，请调用 **WatchTab**，并将第二个参数设置为 **stop**。如果您的对话框关闭（以及标签页关闭），监视将自动取消。
将以下英文文本翻译成中文：