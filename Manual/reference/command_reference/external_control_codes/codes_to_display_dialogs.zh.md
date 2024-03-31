# 对话框显示代码

运行命令时可以使用以下代码来显示各种简单的对话框。这让你可在“运行时”提供信息（如选择文件或文件夹或输入字符串）,而不是将值合并到命令本身中。为了更灵活地进行操作,你可以使用 [脚本文本框](#/Manual/scripting/script_dialogs/README.zh.md)。

<table>
<thead><tr><th>
长格式</th><th>
短格式</th><th>
描述
</th></tr></thead><tbody><tr><td>
{dlgopen}</td><td>
{Rf}</td><td>

显示**打开文件**对话，可用于选择现有的文件名，并将其传递到命令。
</td></tr><tr><td>
{dlgmulti}</td><td>
{Rm}</td><td>

在多选模式下显示**打开文件**对话，可用于选择一个或多个现有文件。
</td></tr><tr><td>
{dlgsave}</td><td>
{RF}</td><td>

显示**保存文件**对话，可用于输入新的文件名，并将其传递到命令。
</td></tr><tr><td>
{dlgfolder}</td><td>
{Rd}</td><td>

显示**选择文件夹**对话，可用于选择文件夹，并将其传递到命令。
</td></tr><tr><td>
{dlgstring}</td><td>
{Rs}</td><td>
显示一个对话，可让你输入任意字符串。
</td></tr><tr><td>
{dlgstringS}</td><td>
{RS}</td><td>

与`{dlgstring}`相同，但字符串字段的内容会自动选中（仅在指定了默认值的情况下适用，见下文）。
</td></tr><tr><td>
{dlgpassword}</td><td>
{Rp}</td><td>

与`{dlgstring}`相同，但字符串字段的内容会模糊显示，这对于输入密码很有用。
</td></tr><tr><td>
{dlgchoose}</td><td>
{Rc}</td><td>
显示一个下拉列表，可让你从值列表中进行选择。
</td></tr><tr><td>
{dlgchooseS}</td><td>
{RC}</td><td>

与`{dlgchoose}`相同，但值列表会自动排序。
</td></tr></tbody>
</table>

### {dlgopen}、{dlgmulti}、{dlgsize}的参数

这些代码的模板是`{code|<title>|<default>}`。

*\<title\>*指定对话框的标题（未提供时将使用默认标题），*\<default\>*指定默认文件名。

例如，`{dlgopen|Select filename|dopus.txt}`将标题设置为**选择文件名**，默认文件名设置为**dopus.txt**。

对于`{dlgopen}`和`{dlgmulti}`，你可以为*\<default\>*指定通配符，以设置文件对话框的过滤器类型。

例如，`{dlgopen||*.jpg;*.bmp;*.gif}`将保留对话框标题为其默认设置，并将对话框设置为对**.jpg**、**.bmp**和**.gif**文件进行过滤。

对于`{dlgsave}`，你可以指定一个附加参数来填充保存对话框中的“另存为类型”下拉列表。

例如，`{dlgsave|Title|Default Name.txt|type=#Text Files!*.txt!Doc Files!*.doc}`。

**type=**后的`#`将会使默认的“所有文件”项添加到下拉列表中，如果你不想要这个，请去掉`#`。

在此之后是一对或多对字符串，用感叹号（`!`）分隔。每对的第一个字符串是下拉列表中显示的纯文本字符串，每对的第二个字符串是实际的文件扩展名。你还可以通过分号分隔来为一个类型指定多个扩展名，例如: `type=JPEG Files!*.jpg;*.jpeg`。

这些代码还支持[用于传递文件名的代码](codes_for_passing_filenames.zh.md)下列出的修饰符。要使用这些修饰符，你还必须包含*\<title\>*和*\<default\>*参数（如果需要，可以留空）。

例如，`{dlgopen|||noext}`会从选定的文件名中去掉扩展名。

### {dlgfolder}的参数

此代码的模板是`{dlgfolder|<title>|<default>}`。

*\<title\>*指定对话框的标题（未提供时将使用默认标题），*\<default\>*指定默认文件名。

例如，`{dlgfolder|Select folder|C:\Users}`将标题设置为**选择文件夹**，初始选定的文件夹将是**C:\Users**。

此代码支持[用于传递路径的代码](codes_for_passing_paths.zh.md)下列出的修饰符。要使用这些修饰符，你还必须包含*\<title\>*和*\<default\>*参数（如果需要，可以留空）。同样还支持另外一个修饰符`expand`。这会导致初始选定的文件夹自动展开。

例如，`{dlgfolder||C:\Program Files|expand}`将会把**C:\Program Files**设置为默认文件夹，并自动在显示的对话框中将其展开。

### {dlgstring}、{dlgstringS}和{dlgpassword}的参数

这些代码的模板是`{code|<message>|<default>}`。

*\<message\>*指定在对话框中显示的消息，*\<default\>*指定字符串字段的默认值。

你可以使用特殊代码`\n`在消息文本中包含换行符（如果你需要在文本中插入一个字面`\n`序列，则必须转义`\\`字符，如`\\n`）。

![](/Manual/images/media/dlgstring.png)

例如，`{dlgstring|Please enter the string.\nThen click OK.|default string}`。

如果希望用户输入的任何引号字符加倍（“`"`变成`""`），则可以使用可选的`doublequotes`修饰符。它必须紧跟在`*\<default\>*参数的后面，如果该参数没有被使用，则该参数应该为空。加倍引号允许用户在命令参数中包含引号字符，前提是参数本身带有明确的引号。

例如，`SetAttr META "comment:{dlgstring|Enter Comment||doublequotes}"`

此外，`{dlgpassword}`接受一个可选的`confirm`修饰符，它也必须紧跟在`*\<default\>*参数的后面。如果指定了此参数，则对话框将显示两个密码字段，在启用确定按钮之前，你必须在这两个字段中输入相同的值（作为确认）。

例如，`{dlgpassword|Please enter your password twice.||confirm}`。

如果需要同时使用`doublequotes`和`confirm`，则可以按任何顺序指定它们。

例如，`{dlgpassword|Please enter your password twice.||confirm|doublequotes}`。

### {dlgchoose}、{dlgchooseS}的参数

这些代码的模板是`{code|<message>|<option 1>[=<value 1>][+<option 2>[=<value 2>]...]}`。

*\<message\>*指定在对话框中显示的消息。你可以使用特殊代码`\n`在消息文本中包含换行符（如果你需要在文本中插入一个字面`\n`序列，则必须转义`\\`字符，如`\n`）。

*\<option 1\>*是下拉列表中第一个选项显示的文本，*\<option 2\>*是第二个选项，依此类推。多个选项用`+`号分隔。

*\<value 1\>*是与第一个选项关联的可选值。如果提供了此值，则*option*将显示在下拉列表中，*value*是通过命令行传递的值。如果未提供*value*，则*option*文本将同时用于*option*和*value*。

你可以通过在它之前添加`default:`来指定默认选定的选项；否则，第一个选项（排序后）将成为初始选择。你还可以使用`notdefault:`前缀，如果需要使用`default:`或`notdefault:`作为字面量前缀，则只会被删除。
![](/Manual/images/media/dlgchoose.png)

例如，`{dlgchoose|选择编码质量|default:High=320+Medium=256+Low=128}` 会向下拉列表中添加选项 **High**、**Medium** 和 **Low**，其中 **High** 为初始选择，并将值 **320**、**256** 或 **128**（分别）传递到命令行。

如果您需要在选项名称或其值中包含 `+` 或 `=` 字符，可以通过将字符加倍来实现。