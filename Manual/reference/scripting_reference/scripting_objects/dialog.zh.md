# Dialog

**Dialog** 对象允许你显示对话框，提示用户进行确认，允许他们输入文本字符串或密码，以及选择复选框选项或从下拉列表中选择。你还可以使用此对象在屏幕上显示弹出菜单。

你可以使用 **[DOpus](dopus.zh.md).Dlg**、**[文件窗口](lister.zh.md).Dlg**、**[Tab](tab.zh.md).Dlg**、**[Func](func.zh.md).Dlg** 和 **[Command](command.zh.md).Dlg** 方法创建 **Dialog** 对象。

有关使用示例，请参阅 [示例脚本](/Manual/scripting/example_scripts/README.zh.md) 部分。

有两种不同的方法可以使用 **Dialog** 对象。你可以：

- 使用一次性方法（**Folder**、**GetString**、**Multi**、**Open**、**Request** 或 **Save**）来显示各种类型的简单对话框，或者
- 首先通过设置各种属性的值来配置对话框，然后调用 **Show** 函数来显示它。此方法还允许你创建和使用 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)。

一次性方法接受多个参数，但通常不如构建对话框然后调用 **Show** 灵活。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
buttons</td><td>

*string*</td><td>

指定在对话框底部显示的按钮。这些按钮用于关闭对话框。**Show** 方法返回一个值，指示选择了哪个按钮（此值也存在于 **result** 属性中）。

多个按钮字符串必须用竖线字符（|）分隔。如果一个按钮有多个按钮，那么最后一个按钮就是“取消”按钮。例如：

    dlg.buttons = "OK|Retry|Cancel"

要为按钮指定 *加速键*，请在所需键之前添加一个与符号（&）字符。例如：

    dlg.buttons = "&OK|&Retry|&Cancel"

按钮也可以附加下拉菜单，方法是用加号（+）分隔下拉菜单项。例如：

    dlg.buttons = "OK|Retry+Retry All|Cancel"

在下拉菜单中，你可以指定某些菜单项可以通过按住 <kbd>Shift</kbd>、<kbd>Ctrl</kbd> 或 <kbd>Shift+Ctrl</kbd> 来直接访问。这可以通过添加等号和按钮在按住键时显示的标签来完成（通常是菜单项标签的缩写版本，或者如果标签本身已经足够短，则重复标签本身）。键会自动分配，你最多只能为三个项目执行此操作。例如：

\<WRAP prewrap\>

    dlg.buttons = "OK|Retry+Retry All=Retry All|Skip+Skip if same modified time=Skip Same Time|Cancel"

\</WRAP\>
</td></tr><tr><td>
choices</td><td>

*object:***[Vector](vector.zh.md)***(string)*  
或 *array(string)*</td><td>

此属性使用 **[Vector](vector.zh.md)** 或字符串数组来提供一个可显示给用户的多个选项列表。列表可以通过三种方式之一显示：

- **下拉列表**: 默认情况下，对话框将显示一个下拉列表，允许用户选择一个选项。当 **Show** 方法返回时，通过 **selection** 属性可以获得所选项目的索引。
- **复选框列表**: 如果也提供了 **list** 属性，则对话框将显示一个滚动项目列表，每个项目都有一个复选框，允许将其打开或关闭。
- **弹出菜单**: 如果也提供了 **menu** 属性，则将在当前鼠标坐标处显示一个弹出菜单。使用单个连字符（-）作为菜单标签来插入分隔符。

当以复选框列表的形式显示时，对话框是可调整大小的；你可以使用 **cx** 和 **cy** 属性设置初始大小（如果要保存大小，则可以在之后检索它们）。
</td></tr><tr><td>
confirm</td><td>

*bool*</td><td>

在文本输入对话框中（即 **max** 属性已指定），将 **confirm** 设置为 **True** 将要求用户再次输入输入的文本（在第二个文本字段中）以确认它（例如，对于密码）。
</td></tr><tr><td>
cx</td><td>

*int*</td><td>

对于标记为可调整大小的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)，此属性允许你覆盖资源中定义的对话框宽度 - 尽管注意你无法将对话框调整为小于其初始大小。
</td></tr><tr><td>
cy</td><td>

*int*</td><td>

对于标记为可调整大小的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)，此属性允许你覆盖资源中定义的对话框高度 - 尽管注意你无法将对话框调整为小于其初始大小。
</td></tr><tr><td>
defvalue</td><td>

*string*</td><td>

在文本输入对话框中（即 **max** 属性已指定），此属性允许你使用默认值初始化文本字段。

（旧脚本可能使用“default”而不是“defvalue”；这是不推荐使用的，因为它在 JScript 中不起作用，因为“default”是一个保留关键字。）
</td></tr><tr><td>
defid</td><td>

*int*</td><td>

允许你更改对话框中的默认按钮（即用户按回车键时将执行的操作）。通常第一个按钮是默认按钮 - 它的 **defid** 为 1。第二个按钮的 **defid** 为 2，依此类推。如果一个对话框有多个按钮，那么最后一个按钮就是“取消”按钮，它的 **defid** 为 0。
</td></tr><tr><td>
detach</td><td>

*bool*</td><td>

如果要使 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 以“分离”模式运行，请将其设置为 **True**，在这种模式下，你的脚本将提供其 [消息循环](/Manual/scripting/script_dialogs/the_dialog_message_loop/README.zh.md)。
</td></tr><tr><td>
disable_window</td><td>

*object:***[文件窗口](lister.zh.md)**  
或 *object:***[Tab](tab.zh.md)**   
*或 object:***Dialog\\** 或 *int*</td><td>

使用它可以使对话框在显示时自动禁用另一个窗口。用户将无法在禁用的窗口中单击或输入，直到对话框关闭。通常，如果你使用它，你将将其设置为与 **window** 属性相同的值。

你可以提供 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象，或另一个 **Dialog**。如果你是为了响应 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 事件而显示此对话框，你也可以传递 **[AboutData](aboutdata.zh.md).window** 属性的值。
</td></tr><tr><td>
icon</td><td>

*string* 或  
*object:***[Image](image.zh.md)**</td><td>

在对话框的左上角显示几个标准图标之一，这些图标可用于指示错误条件的严重程度。此属性的有效值为 *warning*、*error*、*info* 和 *question*。

与 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 一起使用时，此属性允许你控制在对话框标题栏中显示的图标。在这种情况下，除了字符串之外，你还可以提供一个 **[Image](image.zh.md)** 对象，该对象是从 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法获得的。请注意，图像必须是从 **.ico** 文件加载的。
</td></tr><tr><td>
input</td><td>

*string*</td><td>

在文本输入对话框中，此属性返回用户输入的文本字符串（即 **Show** 方法返回后）。
</td></tr><tr><td>
language</td><td>

*string*</td><td>

设置此属性以在特定语言中创建 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)（如果提供了一个或多个 [语言覆盖](/Manual/scripting/script_editor/editors/dialog_editor/language_overlays.zh.md)），而不是当前选择的语言。
</td></tr><tr><td>
list</td><td>

*object:***[Vector](vector.zh.md)***(bool)*  
或 *array(bool)\\* 或// int//</td><td>

与 **choices** 属性结合使用时，这将导致选择以复选框列表的形式显示。你可以使用与 choices 属性相同数量的项目初始化此 **Vector** 或数组，并将每个项目设置为 **True** 或 **False** 以控制每个复选框的默认状态。或者，只需将此值设置为\*\* 0\*\* 即可激活复选框列表，而无需初始化每个复选框的状态。

当 **Show** 方法返回时，此属性将返回一个 *bools* 的 **[Vector](vector.zh.md)**，它提供用户设置的每个复选框的状态。
</td></tr><tr><td>
max</td><td>

*int*</td><td>

此属性在对话框中启用文本输入 - 将显示一个文本字段，允许用户输入字符串。将此属性设置为要允许用户输入的字符串的最大长度（或 **0** 表示没有限制）。

当 **Show** 方法返回时，用户输入的文本将出现在 **input** 属性中。
</td></tr><tr><td>
menu</td><td>

*object:***[Vector](vector.zh.md)***(int)*  
或 *array(int)*  
或 *int*</td><td>

与 **choices** 属性结合使用时，这将导致选择以弹出菜单的形式显示，而不是在对话框中显示。该菜单将在当前鼠标坐标处显示。

你可以使用与 choices 属性相同数量的项目初始化此 **Vector** 或数组，并将每个项目设置为一个值，该值表示控制菜单项外观的各种标志。可用的标志如下 - 如果你需要为每个项目指定多个标志，则必须将它们的值加在一起。

|       |                                                         |
|-------|---------------------------------------------------------|
| **1** | 粗体（表示默认项目）                       |
| **2** | 已选中（将在项目旁边显示一个复选标记）      |
| **4** | 单选（将在项目旁边显示一个单选按钮）     |
| **8** | 已禁用（用户将无法选择该项目） |

你也可以简单地将此值设置为 **0** 或 **1** 即可激活弹出菜单，而无需为每个项目提供标志（如果设置为 **1**，则菜单中的顶部项目将以粗体显示）。

**Show** 方法返回用户选择的菜单项的索引（其中 **1** 是第一个项目），或者如果菜单被取消，则返回 **0**。
</td></tr><tr><td>
message</td><td>

*string*</td><td>
指定在对话框中显示的消息文本。
</td></tr><tr><td>
msgonly</td><td>

*bool*</td><td>

在创建对话框之前将其设置为 **True** 以创建 *仅消息* 对话框。仅消息对话框永远不会可见，但仍然运行正常的消息循环。这使你能够使用诸如 `WatchTab` 或 `HTTPRequest` 之类的东西，而无需可见对话框（或求助于不透明度技巧）。在使用此模式时，不需要对话框模板。请注意，只有分离的对话框支持此选项。
</td></tr><tr><td>
opacity</td><td>

*int*</td><td>

对于 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)，此属性检索或设置当前对话框的不透明度级别，从 **0**（完全透明）到 **255**（完全不透明）。
</td></tr><tr><td>
options</td><td>

*collection:***[DialogOption](dialogoption.zh.md)**</td><td>

这是一个包含五个选项的集合，这些选项将以复选框的形式显示在对话框中。与 **choices** / **list** 滚动复选框列表不同，这些选项以物理复选框控件的形式显示。默认情况下，五个复选框未初始化且不会显示，但如果你为其中任何一个分配一个标签，它们将显示给用户。

当 **Show** 方法返回时，你可以使用每个 **[DialogOption](dialogoption.zh.md)** 对象的 **state** 属性获取复选框的状态。
</td></tr><tr><td>
password</td><td>

*bool*</td><td>

在文本输入对话框中，将此属性设置为 **True** 以使文本输入字段成为密码字段。在密码字段中，用户输入的字符不会显示。
</td></tr><tr><td>
position</td><td>

*string*</td><td>

与 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 一起使用时，此属性允许你控制对话框在屏幕上的位置。接受的值为：

|              |                                                                   |
|--------------|-------------------------------------------------------------------|
| **center**   | 将对话框居中在父窗口之上（默认值）            |
| **absolute** | 使用 **x** 和 **y** 属性指定绝对位置 |
| **parent**   | 相对于父窗口的位置（使用 **x** 和 **y**）    |
| **monitor**  | 相对于当前显示器的位置（使用 **x** 和 **y**）  |

除了设置为“center”之外，**x** 和 **y** 属性还可以用于调整对话框的位置。
</td></tr><tr><td>
position_fix</td><td>

*bool*</td><td>

默认情况下，Opus 会在你的对话框打开之前检查它的尺寸和位置，如果它们会将任何部分的对话框放置到屏幕外，则会修复它们。将对话框放置在屏幕外通常是意外造成的，原因是将窗口位置保存在一个系统上，并在另一个具有不同显示器分辨率或排列的系统上恢复它们。在极少数情况下，你希望你的对话框打开在屏幕外，用户看不到部分或全部，请将此属性设置为 **False**。
</td></tr><tr><td>
result</td><td>

*int*</td><td>

此属性返回用户选择关闭对话框的按钮的索引。最左边的按钮是索引 **1**，下一个按钮是索引 **2**，依此类推。如果一个对话框有多个按钮，那么最后一个（最右边的）按钮就是“取消”按钮，因此这将返回索引 **0**。

如果任何按钮有相关的下拉菜单，那么菜单的内容也会对索引值产生影响。例如，如果按钮索引 2 在下拉菜单中有一个额外的项目，那么该项目将是索引 3，下一个按钮将是索引 4。
</td></tr><tr><td>
select</td><td>

*bool*</td><td>

在文本输入对话框中，将此属性设置为 **True** 以在对话框打开时自动选择输入字段的内容（如 **defvalue** 属性所指定）。



# 对话框

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
selection</td><td>

*int*</td><td>

在下拉列表对话框中（带有 **choices** 属性但没有 **list** 或 **menu** 属性），此属性返回用户从下拉列表中选择项目的索引，该索引在 **Show** 方法返回后返回。
</td></tr><tr><td>
singleton</td><td>

*string*</td><td>

如果你只想在一次打开一个对话框实例，请在创建对话框之前将此属性设置为一个唯一名称。创建对话框时，Opus 将检查是否存在另一个具有相同 singleton 名称的对话框正在打开。如果已打开，则现有对话框将被置于最前面，并且你的脚本将从 `Create` 或 `Show` 方法中收到 **False** 返回值。在这种情况下，你应该检查这种情况并退出脚本。
</td></tr><tr><td>
sort</td><td>

*bool*</td><td>

如果 **choices** 属性提供的选择列表应该按字母顺序排序，则将此属性设置为 **True**。
</td></tr><tr><td>
state</td><td>

*string*</td><td>
返回一个字符串，指示对话框的当前状态。可能的值为 "visible"（正常状态，已打开且可见）、"hidden"（对话框已被隐藏）、"min"（对话框已最小化）、"max"（对话框已可见且已最大化）。
</td></tr><tr><td>
template</td><td>

*string*</td><td>

允许你创建一个 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)。**template** 属性可以设置为要显示的脚本对话框的名称（如你的脚本资源中定义），也可以设置为包含定义对话框的原始 XML 的字符串。
</td></tr><tr><td>
title</td><td>

*string*</td><td>
指定对话框的标题文本。
</td></tr><tr><td>
top</td><td>
bool</td><td>

将此属性设置为 **True** 以使对话框“顶层”，或设置为 **False** 以允许其位于其它非顶层窗口的后面。
</td></tr><tr><td>
want_close</td><td>

*bool*</td><td>

如果希望脚本对话框在用户单击窗口关闭按钮时在你的消息循环中生成关闭事件，则将此属性设置为 **True**。你需要使用 **EndDlg** 方法自己关闭对话框。
</td></tr><tr><td>
want_resize</td><td>

*bool*</td><td>

如果希望脚本对话框在用户调整对话框大小时在你的消息循环中生成 **resize** 事件，则将此属性设置为 **True**。
</td></tr><tr><td>
window</td><td>

*object:***[文件窗口](lister.zh.md)**  
或 *object:***[Tab](tab.zh.md)**  
或 *object:***Dialog**  
或 *int*</td><td>

使用它来指定对话框的父窗口。对话框将显示在指定的窗口顶部居中。你可以提供 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象，或另一个 **Dialog**。如果你是为了响应 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 事件而显示此对话框，你也可以传递 **[AboutData](aboutdata.zh.md).window** 属性的值。

如果你从 **[DOpus](dopus.zh.md).Dlg** 方法中获得 **Dialog** 选项，则只需要设置此属性。如果 **Dialog** 对象来自其它对象（例如 **[Tab](tab.zh.md).Dlg**），则其父窗口将已设置为启动你的脚本正在响应的操作的窗口。
</td></tr><tr><td>
x</td><td>

*int*</td><td>

指定 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的 x 坐标。使用 **position** 属性来控制如何解释位置。在对话框显示后，你可以更改此属性以在屏幕上移动对话框。
</td></tr><tr><td>
y</td><td>

*int*</td><td>

指定 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的 y 坐标。使用 **position** 属性来控制如何解释位置。在对话框显示后，你可以更改此属性以在屏幕上移动对话框。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddCustomMsg</td><td>

\<string:name\>  
\[\<bool:force\>\]</td><td>

*bool*</td><td>

允许脚本对话框注册一个或多个自定义消息，这些消息可以从其它脚本发送到它。

消息是按名称注册的。如果消息已注册，则该方法将失败，除非你将可选的 *force* 参数设置为 true。

使用 **[DOpus](dopus.zh.md).SendCustomMsg** 将消息发送到对话框。该对话框将在其消息循环中接收一个 "custom" **[Msg](msg.zh.md)**。
</td></tr><tr><td>
AddHotkey</td><td>

\<string:name\>  
\<string:key\></td><td>

*bool*</td><td>

为指定的键组合创建一个热键（或键盘加速键）。当用户在你的对话框中按此键组合时，将触发 **hotkey** 事件。

name 参数是你分配的名称，它允许你识别热键。key 参数指定实际的键组合；这可以可选地将限定符 **ctrl**、**shift** 和 **alt** 与字符或特殊键的名称组合起来。例如，**ctrl+t** 或 **alt+shift+F7**。

此方法在成功时返回 true，在失败时返回 false（例如，如果热键已存在）。
</td></tr><tr><td>
AutoSize</td><td>

*none*</td><td>

*none*</td><td>
如果对话框具有取决于其它控件大小的自动调整大小控件，并且你在运行时更改了它们的大小，则可以调用此方法强制对话框重新计算所有相对控件大小，直到你完成所需的更改为止。
</td></tr><tr><td>
CancelWatchClipboard</td><td>

*none*</td><td>

*none*</td><td>

取消对系统剪贴板的监控，这些监控之前是由对 **WatchClipboard** 方法的调用建立的。
</td></tr><tr><td>
CancelWatchDir</td><td>

\<string:id\></td><td>

*none*</td><td>

取消文件夹或文件更改监控，这些监控之前是由对 **WatchDir** 方法的调用建立的。**id** 参数是你创建监视器时分配给它的 ID。
</td></tr><tr><td>
Create</td><td>

*none*</td><td>

*none*</td><td>

创建 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 时，调用此方法将创建底层对话框，但不会显示它。这允许你创建对话框，然后在将其显示给用户之前初始化其控件。

使用 **Create** 表示 [分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md)；**detach** 属性将自动设置为 **True**。但是，如果你不需要自定义消息循环，并且只想在显示对话框之前设置一些控件，则可以在之后调用 **RunDlg**。

创建对话框并初始化其控件后，你应该调用 **Show** 或 **RunDlg** 以使其对用户可见。如果它尚未显示，它也将在第一个 **GetMsg** 调用时变为可见。
</td></tr><tr><td>
CreateFont</td><td>

\<string:name\>  
\[\<int:size\>\]  
\[\<string:styles\>\]</td><td>

*int*</td><td>

创建一个字体对象，可以将其提供给对话框控件以使其使用非标准字体。*name* 参数指定字体的名称（例如，"Arial"）- 你也可以使用 "\*"，表示默认对话框字体。*size* 参数指定所需的大小（使用 0 以获取默认对话框字体大小）。*styles* 字符串可以包含一个或多个字符，表示所需的字体样式 -"b" 表示粗体，"i" 表示斜体，"u" 表示下划线。

返回值可以与 **[Control](control.zh.md).SetFont** 方法一起使用。

你创建的字体在对话框关闭时会自动销毁，但如果你要手动删除它们以释放资源，请使用 **DestroyFont** 方法。
</td></tr><tr><td>
Control</td><td>

\<string:name\>  
\[\<string:dialog\>\]  
\[\<string:tab\>\]</td><td>

*object:***[Control](control.zh.md)**</td><td>

返回一个 **[Control](control.zh.md)** 对象，该对象对应于脚本对话框上的一个控件。该控件由其 *name* 标识，如脚本对话框资源中定义的那样。

可选的第二个和第三个参数仅在控件位于 *标签控件* 中时使用（也就是说，当它位于另一个对话框的子对话框中时）。*dialog* 参数指定其父对话框的名称。*tab* 参数指定承载子对话框的标签控件的名称。只有在你有多个标签控件并且同一个对话框在多个标签控件中承载时，才需要指定标签的名称（这将是一个非常罕见的情况）。

请注意，在调用 **Create** 之前，所有控件都不会存在。
</td></tr><tr><td>
DelHotkey</td><td>

\<string:name\></td><td>

*bool*</td><td>

删除你之前使用 **AddHotkey** 方法创建的热键。

此方法在成功时返回 true，在失败时返回 false（例如，如果热键不存在）。
</td></tr><tr><td>
Drag</td><td>

*object:***[Items](items.zh.md)**  
\<string:actions\></td><td>

*string*</td><td>

允许用户从你的对话框中拖放一个或多个文件（并将它们放在另一个窗口或应用程序中）。

你通常会在收到来自 **static** 或列表视图控件的 **drag** 事件时调用此方法。

第一个参数是一个 **[Items](items.zh.md)** 对象，它代表要拖动的文件。（你也可以传递 **[Vector](vector.zh.md)** 的 **[Item](item.zh.md)** 或 **[Path](path.zh.md)** 对象，或完整路径字符串，而不是 **[Items](items.zh.md)** 对象。或者 **[StringSet](stringset.zh.md)** 或 **[UnorderedSet](unorderedset.zh.md)** 的完整路径字符串。）

可选的第二个参数允许你控制哪些操作可用。这应该是一个字符串，包含 **copy**、**move**、**link** 中的一个或多个。默认操作可以通过在它之前添加一个 \* 来表示（例如，**copy,\*move,link**）。如果你没有指定此参数，则默认情况下只允许 **copy**。

此方法返回的字符串指示拖放的结果。对于左键拖放，这将是 "copy"、"move"、"link" 或 "drop"。对于右键拖放，它始终是 "drop"。如果拖放被取消，它将返回 "cancel"。
</td></tr><tr><td>
DestroyFont</td><td>

\<int:id\></td><td>

*none*</td><td>

使用 **CreateFont** 方法返回的 ID 销毁指定的字体。
</td></tr><tr><td>
EndDlg</td><td>

\<int:result\></td><td>

*none*</td><td>

结束以分离模式运行的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)。通常，对话框在用户单击关闭按钮或另一个其 **Close Dialog** 属性设置为 **True** 的按钮时会自动结束。此方法允许你在脚本控制下结束对话框。可选参数指定 **Dialog.result** 属性将返回的结果代码。
</td></tr><tr><td>
Folder</td><td>

\<string:title\>  
\<string:default\>  
\<bool:expand\>  
\<object:window\></td><td>

*object:***[Path](path.zh.md)**</td><td>

显示一个“浏览文件夹”对话框，让用户选择一个文件夹。可选参数为：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认路径
- *expand* - 指定 **True** 以自动展开初始路径
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。

返回一个 **[Path](path.zh.md)** 对象，以指示用户选择的文件夹。此对象将有一个额外的 **result** 属性，如果用户取消了对话框，该属性将为 **False** - 其它正常的 **Path** 属性只有在 **result** 为 **True** 时才有效。
</td></tr><tr><td>
FlushMsg</td><td>

*none*</td><td>

*int*</td><td>
刷新对话框的消息队列。任何未检索的消息都将被丢弃。返回值告诉你队列中有多少条消息。
</td></tr><tr><td>
GetMsg</td><td>

*none*</td><td>

*object:***[Msg](msg.zh.md)**</td><td>

返回一个 **[Msg](msg.zh.md)** 对象，它表示 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中最新的输入事件（仅在 [分离模式](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md) 中使用）。

当对话框关闭时，返回值将计算为 **False**，此时你应该退出你的 [消息循环](/Manual/scripting/script_dialogs/the_dialog_message_loop/README.zh.md)。

如果对话框尚未可见（因为尚未调用 **Show**），那么当你第一次调用 **GetMsg** 时，它将变为可见。
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

显示一个文本输入对话框，允许用户输入一个字符串。可选参数为：

- *message* - 指定对话框中的消息字符串
- *default* - 指定默认字符串值
- *max* - 指定最大字符串长度
- *buttons* - 指定按钮标签（与上面描述的 **buttons** 属性的格式相同）
- *title* - 指定对话框窗口标题
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。
- *result* - 对于支持 *ByRef* 参数的脚本语言，这可以指定一个变量来接收用户输入的字符串。

返回值是输入的字符串，如果对话框被取消，则为空值。用户选择的按钮的索引将在此方法返回后通过 **result** 属性提供。最左边的按钮是索引 **1**，下一个按钮是索引 **2**，依此类推。如果一个对话框有多个按钮，那么最后一个（最右边的）按钮就是“取消”按钮，因此这将返回索引 **0**。
</td></tr><tr><td>
KillTimer</td><td>

\<string:name\></td><td>

*none*</td><td>

停止指定的计时器。计时器必须先前已通过调用 **SetTimer** 方法创建。
</td></tr><tr><td>



# 对话框

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
LoadPosition</td><td>

\<string:id\>  
\<string:type\></td><td>

*none*</td><td>

恢复先前保存的 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的位置。该位置必须先前已通过调用 **SavePosition** 方法保存。

**id** 字符串是 Opus 可以用来识别你的对话框或它来自的脚本的字符串。对话框的模板名称将自动附加到此。例如，你可以将 **id** 指定为 *"kundal"* - 然后 Opus 将在内部将名为 *"dialog1"* 的对话框的位置保存为 *"kundal!dialog1"*。确保你选择的字符串是其它脚本作者不太可能使用的，因为 Opus 没有其它方法来区分保存的位置。

可选的 type 参数允许你控制要恢复哪些位置元素 - 指定 *"pos"* 仅恢复位置，*"size"* 仅恢复大小，或者 *"pos,size"* 恢复两者（这也是默认值，因此你也可以完全省略参数）。
</td></tr><tr><td>
Multi</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\>  
\<string:type\></td><td>

*object:***[Items](items.zh.md)**</td><td>

显示一个“浏览以打开文件”对话框，让用户选择一个或多个文件。可选参数为：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认文件（如果指定了文件夹，则指定默认位置，但不会选择任何文件）
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。（如果你不想使用它，请完全省略 *window* 参数；如果使用 *type* 参数，则无论第三个还是第四个参数都能起作用。）
- *type* - 在保存对话框中填充“保存为类型”下拉列表的文件类型列表。（见下文。）

可选的 *type* 参数由一个或多个字符串对组成，用感叹号（**!**）分隔。每一对中的第一个字符串是下拉菜单中显示的纯文本字符串，而每一对中的第二个字符串是实际的文件扩展名。你也可以通过分号将多个扩展名指定为一种类型。如果你希望将默认的“所有文件”项添加到列表中，请在字符串的开头添加一个 **\#** 字符。例如，*\#Text Files!\*.txt!Doc Files!\*.doc.*

返回一个 **[Items](items.zh.md)** 对象，以指示用户选择的文件夹。返回的对象将有一个 **result** 属性，你应该首先检查它 - 只有在 **result** 返回 **True** 时，项目集合才有效。如果返回 **False**，则表示用户取消了对话框。
</td></tr><tr><td>
NewHTTPReq</td><td>

*none*</td><td>

*object:***[HTTPRequest](httprequest.zh.md)**</td><td>

创建一个新的 [HTTPRequest](httprequest.zh.md) 对象，该对象附加到此对话框。此对象提供了一种简单的方法，可以异步地向服务器发送 HTTP 请求，并检索响应。

来自 HTTP 请求的事件将通过你的对话框的消息循环进行传递，因此你必须使用分离的对话框才能使用此功能。
</td></tr><tr><td>
NotifyIcon</td><td>

\<string:method\>  
*arguments...*</td><td>

*none*</td><td>

允许脚本将图标添加到系统任务栏通知区域。

*method* 参数指定四个操作之一，每个操作都有自己的一组参数。

<table>
<thead>
<tr class="header">
<th>method</th>
<th>Arguments</th>
<th>Description</th>
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

对于 **add** 和 **update** 方法，*icon* 参数可以是字符串或 **[Image](image.zh.md)** 对象 - 有关详细信息，请参阅上面有关 **icon** 属性的文档。如果通过此属性已将图标分配给对话框，则如果没有提供任何图标，将自动使用该图标。

*tooltip* 参数提供一个工具提示字符串，当用户将鼠标悬停在图标上时，系统将显示该字符串。如果已设置对话框的 **title** 属性，则如果没有给出明确的工具提示，则将使用标题。

**notify** 方法允许你显示与你的对话框关联的系统通知。此方法类似于 **[DOpus](dopus.zh.md).Notify** 方法 - 有关参数的更多信息，请参阅该方法的描述。

在你的脚本添加图标后，用户可以使用鼠标与之交互。鼠标活动将在你的对话框的消息循环中生成 **click**、**dblclk** 和 **rclick** 事件。**[Msg](msg.zh.md).control** 属性将设置为 **notifyicon**。

图标在你的对话框关闭时会自动删除。如果在添加图标后资源管理器重新启动，它也会自动恢复。

请注意，每个对话框只支持一个图标。
</td></tr><tr><td>
Open</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\>  
\<string:type\></td><td>

*object:***[Item](item.zh.md)**</td><td>

显示一个“浏览以打开文件”对话框，让用户选择一个文件。可选参数为：

- *title* - 指定对话框的标题
- *default* - 指定对话框中选择的默认文件（如果指定了文件夹，则指定默认位置，但不会选择任何文件）
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。（如果你不想使用它，请完全省略 *window* 参数；如果使用 *type* 参数，则无论第三个还是第四个参数都能起作用。）
- *type* - 在保存对话框中填充“保存为类型”下拉列表的文件类型列表。（见下文。）

可选的 *type* 参数由一个或多个字符串对组成，用感叹号（**!**）分隔。每一对中的第一个字符串是下拉菜单中显示的纯文本字符串，而每一对中的第二个字符串是实际的文件扩展名。你也可以通过分号将多个扩展名指定为一种类型。如果你希望将默认的“所有文件”项添加到列表中，请在字符串的开头添加一个 **\#** 字符。例如，*\#Text Files!\*.txt!Doc Files!\*.doc.*

返回一个 **[Item](item.zh.md)** 对象，以指示用户选择的文件夹。此对象将有一个额外的 **result** 属性，如果用户取消了对话框，该属性将为 **False** - 其它正常的 **Item** 属性只有在 **result** 为 **True** 时才有效。
</td></tr><tr><td>
Request</td><td>

\<string:message\>  
\<string:buttons\>  
\<string:title\>  
\<object:window\></td><td>

*int*</td><td>

显示一个带有一个或多个按钮的对话框。可选参数为：

- *message* - 指定对话框中的消息字符串
- *buttons* - 指定按钮标签（与上面描述的 **buttons** 属性的格式相同）
- *title* - 指定对话框窗口标题
- *window* - 指定对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。

返回值是用户选择的按钮的索引，并且在方法返回后，它也存在于 **result** 属性中。最左边的按钮是索引 **1**，下一个按钮是索引 **2**，依此类推。如果一个对话框有多个按钮，那么最后一个（最右边的）按钮就是“取消”按钮，因此这将返回索引 **0**。
</td></tr><tr><td>
RunDlg</td><td>

*none*</td><td>

*int*</td><td>

通过接管并运行默认的消息循环，将先前 [分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md) 转换为非分离的对话框。 **RunDlg** 方法在对话框关闭之前不会返回。如果你使用 **Create** 创建了对话框，为了初始化其控件，但实际上不想运行交互式消息循环，你可能会使用它。

返回值与对象的 **result** 属性相同，表示用户选择的关闭按钮的索引。

如果对话框尚未可见（因为尚未调用 **Show** 或 **GetMsg**），那么当你调用 **RunDlg** 时，它将变为可见。（兼容性说明：在 Opus 12.22 之前，脚本需要显式调用 **Show**。）
</td></tr><tr><td>
Save</td><td>

\<string:title\>  
\<string:default\>  
\<object:window\>  
\<string:type\></td><td>

*object:***[Path](path.zh.md)**</td><td>

显示一个“浏览以保存文件”对话框，让用户选择一个文件或输入一个新的文件名以保存。可选参数为：

- *title* - 对话框的标题。
- *default* - 对话框中选择的默认文件。（如果给出了文件夹，则设置对话框的起始位置，但不会选择任何文件。）
- *window* - 对话框的父窗口（**[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）。如果未指定，则使用 **Dialog** 对象的 **window** 属性。（如果你不想使用它，请完全省略 *window* 参数；如果使用 *type* 参数，则无论第三个还是第四个参数都能起作用。）
- *type* - 在保存对话框中填充“保存为类型”下拉列表的文件类型列表。（见下文。）

可选的 *type* 参数由一个或多个字符串对组成，用感叹号（**!**）分隔。每一对中的第一个字符串是下拉菜单中显示的纯文本字符串，而每一对中的第二个字符串是实际的文件扩展名。你也可以通过分号将多个扩展名指定为一种类型。如果你希望将默认的“所有文件”项添加到列表中，请在字符串的开头添加一个 **\#** 字符。例如，*\#Text Files!\*.txt!Doc Files!\*.doc.*

返回一个 **[Path](path.zh.md)** 对象，以指示用户选择的文件夹。此对象将有一个额外的 **result** 属性，如果用户取消了对话框，该属性将为 **False**，并且只有在 **result** 为 **True** 时，其它正常的 **Path** 属性才有效。
</td></tr><tr><td>
SavePosition</td><td>

\<string:id\></td><td>

*none*</td><td>

将对话框的位置（和大小）保存到你的 Opus 配置中。然后，可以稍后通过调用 **LoadPosition** 恢复该位置。

通常，你将在显示对话框之前调用 **LoadPosition**，并在对话框关闭后调用 **SavePosition**。

**id** 字符串是 Opus 可以用来识别你的对话框或它来自的脚本的字符串。对话框的模板名称将自动附加到此。例如，你可以将 **id** 指定为 *"kundal"* - 然后 Opus 将在内部将名为 *"dialog1"* 的对话框的位置保存为 *"kundal!dialog1"*。确保你选择的字符串是其它脚本作者不太可能使用的，因为 Opus 没有其它方法来区分保存的位置。
</td></tr><tr><td>
SetTimer</td><td>

\<int:period\>  
\<string:name\></td><td>

*string*</td><td>

创建一个计时器，该计时器将为你的脚本生成周期性的 **timer** 事件。**period** 必须以毫秒为单位指定（例如，1000 等于一秒）。

你也可以可选地为计时器指定一个 **name** - 如果你没有提供名称，则会自动生成一个名称（并且会返回新计时器的名称）。
</td></tr><tr><td>
Show</td><td>

*none*</td><td>

*int*</td><td>

显示已使用此对象的各种属性预先配置的对话框。有关这些属性的完整描述，请参阅上面的属性部分。

如果 **detach** 属性为 **False**，则该调用在对话框关闭之前不会返回。返回值是用户选择的按钮的索引，并且在方法返回后，它也存在于 **result** 属性中。最左边的按钮是索引 **1**，下一个按钮是索引 **2**，依此类推。如果一个对话框有多个按钮，那么最后一个（最右边的）按钮就是“取消”按钮，因此这将返回索引 **0**。

如果 **detach** 属性为 **True**，则该调用将立即返回，并且返回值毫无意义。然后，你应该为“分离”的对话框运行消息循环，或者调用 **RunDlg** 来运行标准循环。

请注意，调用 **Create** 会隐式地将 **detach** 属性设置为 **True**。如果你需要创建对话框以修改它的一些控件，然后才将其显示，但不想在显示后运行自己的消息循环，你应该调用 **RunDlg** 而不是 **Show**。
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

用于更改自定义对话框在任务栏上与其它 Opus 窗口的组合方式。指定一个组名以将窗口移动到另一个组，或者省略组参数以重置回默认组。如果一个或多个窗口被移动到同一个组中，它们将被组合在一起，与默认组分开。

这仅在 Windows 7 及更高版本上有效，并且仅在启用任务栏组合时有效。组名限制为 103 个字符，如果超过此限制，将被截断。组名中的空格和点将自动转换为下划线。

仅对自定义脚本对话框有效（即，当你使用 **template** 属性时）。必须在对话框创建后调用（即，在调用 **Show** 后 - 如果你只想为此编写自己的消息循环，请参阅 **RunDlg** 方法）。  
如果成功则返回 true。
</td></tr><tr><td>
Vars</td><td>



# 对话框

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
\<string:id\></td><td>

*object:***[Vars](vars.zh.md)**</td><td>

返回一个 **[Vars](vars.zh.md)** 对象，该对象表示作用于此特定对话框的变量。这允许脚本使用从对话框的一次使用到另一次使用持续存在的变量。

**id** 字符串是 Opus 可以用来识别你的对话框或它来自的脚本的字符串。对话框的模板名称将自动附加到此。例如，你可以将 **id** 指定为 *"kundal"* - 然后 Opus 将在内部为名为 *"dialog1"* 的对话框保存这些变量，名为 *"kundal!dialog1"*。确保你选择的字符串是其它脚本作者不太可能使用的，因为 Opus 没有其它方法来区分保存的变量。
</td></tr><tr><td>
WatchClipboard</td><td>

*none*</td><td>

*bool*</td><td>

建立对系统剪贴板的监控。每当系统剪贴板内容发生更改时，对话框的消息循环都会收到 **clipboard** 事件。

使用 **CancelWatchClipboard** 方法来取消监控。
</td></tr><tr><td>
WatchDir</td><td>

\<string:id\>  
\<string:path\>  
\<string:flags\></td><td>

*int*</td><td>

建立对文件夹或文件的更改监控。成功返回 **0**，失败返回错误代码。

**id** 参数允许你为这个监视器提供一个 ID，用于在发生更改时识别它。**dir** 是文件系统文件夹的完整路径，或者如果设置了 **i** 标志，则是文件的完整路径。

可选的标志为：

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **f** | 监控文件夹中的文件更改（例如，文件创建）           |
| **d** | 监控文件夹中的目录更改（例如，目录创建） |
| **r** | 递归 - 监控子文件夹                                 |
| **a** | 监控文件属性更改                              |
| **s** | 监控文件大小更改                                   |
| **w** | 监控上次写入时间更改                             |
| **i** | 监控单个文件而不是文件夹                      |

当监控的文件或文件夹发生更改时，对话框的消息循环会收到 **dirchange** 事件。**[Msg](msg.zh.md).control** 属性标识监视器的 ID。

使用 **CancelWatchDir** 方法来取消监控。
</td></tr><tr><td>
WatchTab</td><td>

\<object:**[Tab](tab.zh.md)**\>  
\<string:events\>  
\<string:id\></td><td>

*bool*</td><td>

允许 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 监控文件夹标签页中的事件。你将通过消息循环收到所请求事件的通知。

**tab** 参数指定你想要监视的 **[Tab](tab.zh.md)**。**events** 字符串是你要监视的事件的逗号分隔列表。**id** 字符串是一个可选参数；它允许你为标签页分配自己的 ID，以便更容易区分事件来自哪里（例如，如果你正在监视多个标签页）。

这些是你可以监视的事件。请注意，一些事件等效于现有的脚本事件（例如，**OnActivateTab**）：

|              |                                                         |
|--------------|---------------------------------------------------------|
| **select**   | 标签页中的项目被选中或取消选中             |
| **navigate** | 标签页中的文件夹发生更改                        |
| **add**      | 项目被添加到文件夹                           |
| **delete**   | 项目从文件夹中删除                       |
| **change**   | 文件夹中的项目发生更改（大小、日期、名称等） |
| **activate** | 标签页激活或停用                            |
| **srcdst**   | 源/目标状态发生更改                        |
| **view**     | 视图模式发生更改                                       |
| **flat**     | 平铺视图状态发生更改                                 |
| **filter**   | 快速过滤发生更改                                    |

建立通知后，当这些事件发生时，你将收到所有所请求事件的通知。请注意，没有特定信息与通知一起发送 - 例如，对于“change”事件，你不会被告知哪些项目发生了更改，只知道某些东西发生了更改。

你将在消息循环中收到通知事件。**[Msg](msg.zh.md)** 对象的各种属性允许你确定发生了什么。

**[Msg](msg.zh.md).event** 属性将被设置为 **tab**，用于来自监视的文件夹标签页的通知。

**[Msg](msg.zh.md).control** 属性告诉你更改发生在哪个标签页中；如果你在调用 **WatchTab** 函数时指定了 ID，则此 ID 将位于 [Msg](msg.zh.md)**.control** 属性中 - 否则，它将是标签页的数字句柄。请注意，它 \*不是\* 实际的 **[Tab](tab.zh.md)** 对象。你可以通过 [Msg](msg.zh.md)**.tab** 属性访问 **[Tab](tab.zh.md)** 对象，但这可能效率低下，因为它需要在每次调用时创建一个新的 **[Tab](tab.zh.md)** 对象。如果你只监视一个标签页，最好将 **[Tab](tab.zh.md)** 对象存储在自己的变量中 - 如果你监视多个标签页，你可以（例如）为每个标签页使用一个唯一的 ID 并将这些对象保存在 **[Map](map.zh.md)** 中。

**[Msg](msg.zh.md).value** 属性告诉你发生了哪个通知事件。可能的值为 **select**、**navigate**、**filechange**、**activate**、**srcdst**、**view**、**flat**、**filter** 和 **close**（如果你正在监视标签页时，该标签页被关闭，则发送）。

对于 **filechange** 事件，**[Msg](msg.zh.md).data** 属性包含一个位掩码，指示发生了哪些文件事件。**1** = 添加，**2** = 删除，**4** = 更改。这些值将被加在一起（所以例如 **6** 表示至少更改了一个项目，并且至少删除了一个项目）。由你的脚本确定究竟发生了什么变化。

你可以通过再次调用 **WatchTab** 方法（使用相同的标签页和新的事件列表）来更改你正在监视的事件。

要停止监视现有标签页，请调用 **WatchTab**，并将第二个参数设置为 **stop**。如果你的对话框关闭（以及标签页关闭），监控将自动取消。
</td></tr><tr><td>
WindowCmd</td><td>

\<string:command\></td><td>

*none*</td><td>

向对话框窗口发送一个命令，以更改其显示方式。可能的命令为：

|             |                                               |
|-------------|-----------------------------------------------|
| **min**     | 最小化窗口                           |
| **max**     | 最大化窗口                           |
| **restore** | 恢复窗口（从最小化/最大化状态）   |
| **show**    | 如果窗口当前隐藏，则显示它      |
| **showna**  | 显示窗口，但不要激活它         |
| **hide**    | 隐藏窗口                               |
| **front**   | 激活窗口并将其置于最前面 |
</td></tr></tbody>
</table>