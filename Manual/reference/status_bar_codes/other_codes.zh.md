# 其他代码

以下状态栏代码用于设置文本样式、显示有关当前驱动器或文件窗口的其他信息，或与变量和 if 条件配合使用。

# 其他代码

<table>
<thead><tr><th>
代码</th><th>
说明
</th></tr></thead><tbody><tr><td>

\<b\>...\</b\>   
\<i\>...\</i\>   
\<u\>...\</u\></td><td>

**粗体文本**  
**斜体文本**  
**下划线文本**  
使用 HTML 风格标签加粗、倾斜或给状态栏上的文本加下划线。

\<b\>This Will Be Bold Text\</b\>  
\<i\>This Will Be Italic Text\</i\>  
\<u\>This Will Be Underlined Text\</u\>
</td></tr><tr><td>

\<#RRGGBB\>...\</#\></td><td>

**文本颜色**
围绕文本使用含 RGB 十六进制值标签使其颜色有所不同。

\<#FF0000\>This Will Be Red Text\</#\>
</td></tr><tr><td>
{{</td><td>

**文字字符 {**  
连续添加两个 { 字符以将单个文字字符 { 插入状态栏文本，而无需将其解释为状态栏代码的开头。
</td></tr><tr><td>
//</td><td>

**注释**  
使用 **//** 开头行将其变成注释。注释可用于添加注释或说明，或临时移除状态栏部分。

**//** 必须置于行的开头，之前不能有空格或其他任何内容，该行才成为注释。
</td></tr></tbody>
</table>
 # 其他代码 # 其他代码

<table>
<thead><tr><th>
代码</th><th>
说明
</th></tr></thead><tbody><tr><td>
{dlet}</td><td>

**驱动器代号**  
显示当前驱动器代号。它是指源文件列表中当前显示的文件夹。
</td></tr><tr><td>
{dlab}</td><td>

**驱动器标签**  
显示源文件列表中当前打开的驱动器的标签（如果有）。
</td></tr><tr><td>
{fsys}</td><td>

**文件系统**  
显示当前驱动器的文件系统类型。
</td></tr><tr><td>
{vm}</td><td>

**视图模式**  
显示源文件列表中的当前 [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md)。
</td></tr><tr><td>
{ls}</td><td>

**文件窗口状态**  
显示文件窗口的当前 [源/目标](/Manual/basic_concepts/source_and_destination.zh.md) 状态。
</td></tr></tbody>
</table>
 # 其他代码 # 其他代码

<table>
<thead><tr><th>
代码</th><th>
说明
</th></tr></thead><tbody><tr><td>
{sel:..}</td><td>

**所选文件信息**  
显示有关最近所选文件的信息。 **sel：** 后必须跟一个关键字以指定要显示的信息；有效关键字为：

- **name**：文件或文件夹的名称。
- **size**：文件大小。在此关键字后面跟 **b** 或 **k** 以将单位指定为 *字节* 或 *KB*（否则，会自动选择单位）。
- **create**：创建日期戳。在此关键字后面跟 **d** 或 **t** 以指定 *日期* 或 *时间*（否则，两个都会显示）。
- **write**：最后写入（修改）日期戳。在此关键字后面跟 **d** 或 **t** 以指定 *日期* 或 *时间*（否则，两个都会显示）。
- **access**：最后访问日期戳。
- **attr**：文件或文件夹属性。
- **desc**：描述字符串（与在 *描述* 列中显示的字符串相同）。
- **path**：文件或文件夹的完整路径。
- **index**：文件列表中的索引。

例如，**{sel:sizek} {sel:desc}**。
</td></tr></tbody>
</table>
 # 其他代码 # 其他代码

<table>
<thead><tr><th>
代码</th><th>
说明
</th></tr></thead><tbody><tr><td>
{var:...}</td><td>

**变量**  
显示变量值。还可用于 [隐藏状态栏上的部分](hiding_sections_on_the_status_bar.zh.md)。可以使用命令通过 [@set 修饰符](../command_reference/command_modifier_reference.zh.md) 或使用脚本通过 [Vars 对象](../scripting_reference/scripting_objects/vars.zh.md) 设置变量。

变量名称必须以作用域为前缀。例如：

- **{var:glob:MyGlobalVariable}**
- **{var:lst:My文件窗口Variable}**
- **{var:tab:MyFolderTabVariable}**
- **{var:src:MySourceFolderTabVariable}**
- **{var:dst:MyDestinationFolderTabVariable}**
- **{var:left:MyLeftFolderTabVariable}**
- **{var:right:MyRightFolderTabVariable}** **tab** 作用域通常与 **src** 作用域相同，但并不总是如此。如果你的 Opus 配置为对左右文件列表使用单独的状态栏，则可以在两方的状态栏定义中使用 **tab** 作用域，它会在为每一方查找适当的文件列表中的变量。

相同的作用域前缀还用于使用变量的命令中。此外，为了与其他状态栏代码保持一致，还可以使用：

- **{varL:tab:xyz}** 作为 **{var:left:xyz}** 的同义词
- **{varR:tab:xyz}** 作为 **{var:right:xyz}** 的同义词
- **{varD:tab:xyz}** 作为 **{var:dst:xyz}** 的同义词若要 [隐藏状态栏部分](hiding_sections_on_the_status_bar.zh.md)（当未设置变量时）且在设置变量时显示该部分，可以这样操作：

- **{h!{var:glob:ShowExtraInfo}} ...额外信息已打开... {h!}**然后可以使用菜单项、按钮或热键运行此命令来开启和关闭状态栏的这部分：

@if:\$glob:ShowExtraInfo  
@set glob:ShowExtraInfo  
@if:else  
@set glob:ShowExtraInfo=on  
@if:common  
@toggle:update

有关 **@if**、**@set** 和 **@toggle** 命令指令的详细信息，请参见 [命令修饰符参考](../command_reference/command_modifier_reference.zh.md)。

可以在变量名称前添加 **！** 以对变量求反：

- **{h!{var:!glob:ShowExtraInfo}} ...额外信息已关闭... {h!}**
</td></tr></tbody>
</table>
 # 其他代码 # 其他代码

所有这些代码都会测试条件并返回结果。如果条件为真，则会返回“1”；如果条件为假，则会返回空（空字符串）。通常将它们用于显示或隐藏其他信息。单独使用它们来测试你的状态栏代码以检查它们是否按预期返回“1”可能会很有用，但是一旦测试完毕，可能只会在与 **{h!}** 和类似的 [代码配合使用来显示和隐藏状态栏部分](hiding_sections_on_the_status_bar.zh.md)中使用它们。

    {h!{ifpath:C:\}} 你位于 C:\ 的根目录。我敢肯定你之前并不知道这一点。 {h!}

计算 **{ifpath:...}** 相当便宜，请记住，其他条件测试可能会造成性能下降，尤其是在最终触及网络驱动器或求值复杂命令时。状态栏会经常更新——例如，每当选择或取消选择文件时——并且每次更新时都会重新求值添加到其中的任何条件测试。不要过度使用！

当根据多个条件显示或隐藏状态栏部分时，请在开头放置评价成本最低的那些。例如：

    {h!{ifpath:/downloads}!{ifexists:.\*.dll}} 警告：下载文件夹中有 DLL！ {h!}

**{ifpath:...}** 测试很快，因为当前路径已经知道，只需与指定路径或通配符进行比较即可。如果该测试失败，则可以跳过随之而来的 **{ifexists:...}** 测试。按此顺序进行测试意味着你仅在重要时才会进行更昂贵的测试。**{ifexists:...}** 可能很耗时，因为它必须转到磁盘/文件系统以检查是否存在任何内容，这比测试已经存在于内存中的内容要慢得多。
如果你在状态栏上多次测试相同的条件，使用完全相同的代码，你只会在第一次测试中会受到性能损失；其他测试会复用其结果。

<table>
<thead><tr><th>
代码</th><th>
描述
</th></tr></thead><tbody><tr><td>
{ifpath:...}</td><td>

**测试当前路径**  
在 {ifpath:...} 中使用以测试当前路径是否与特定的文件夹、通配符或正则表达式匹配。

**{ifpath:C:\Program Files}** -- 当“C:\Program Files”是当前文件夹时为真。

引号是可选项，但如果路径中包含 **{** 或 **}** 字符，则 *必须* 使用引号将其括起来：

**{ifpath:"C:\My {Test} Folder"}** -- 当“C:\My {Test} Folder”是当前文件夹时为真。

在路径前放置 **!** 以**否定**测试。

**{ifpath:!C:\Program Files}** -- 当“C:\Program Files”不是当前文件夹时为真。

默认情况下使用[通配符模式匹配语法](../wildcard_reference/pattern_matching_syntax.zh.md)。请注意，这意味着如果路径包含 **(** 或 **)** 字符，你需要转义这些字符：

**{ifpath:C:\Program Files '(x86')}** -- 当“C:\Program Files (x86)”是当前文件夹时为真。

如果你愿意，可以使用[别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)：

**{ifpath:/downloads}** -- 当在你的“下载”文件夹中时为真。

*通配符提示 - 匹配文件夹和子文件夹：*  
以 **(\|\\)** 结尾的路径意味着它将匹配文件夹本身和其下的任何文件夹。例如：

- 使用 **C:\MyFolder** 作为模式只会匹配 **C:\MyFolder** 本身，而不匹配 **C:\MyFolder\Child**。
- 如果你改为使用 **C:\MyFolder\\**\*，它将匹配 **C:\MyFolder\Child**，但不匹配 **C:\MyFolder** 本身。
- 如果你使用 **C:\MyFolder**\*, 它将匹配这两个文件夹，但也将匹配完全无关的文件夹，如 **C:\MyFolderBackup**。
- 使用 **C:\MyFolder(\|\\)** 将匹配文件夹本身和其下的任何文件夹（包括子文件夹的子文件夹，依此类推）。    
**{ifpath:C:\Program Files(\|\\)}** -- 当在“C:\Program Files”或其子文件夹中时为真。

你可以通过在路径前添加 **regex:** 来使用[正则表达式语法](../wildcard_reference/regular_expression_syntax.zh.md)：

**{ifpath:regex:"C:\\Program Files\\\[^\\\]+\$"}** -- 仅在“C:\Program Files”的直接子文件夹中为真。  
**{ifpath:!regex:\[0-9\]}** -- 在路径中没有数字的文件夹中为真。  
你不能同时使用别名和正则表达式。在使用正则表达式时记得转义反斜杠。  
（请注意，与[命令限定符](../command_reference/command_modifier_reference.zh.md)等效项不同，你不能使用 *ifpathr* 作为正则表达式模式的简写，因为它在这里有不同的含义。）

**{ifpath:...}** 代码测试当前活跃的文件夹标签页的文件夹。你还可以使用：

- **{ifpathL:...}** 测试左标签页的文件夹。
- **{ifpathR:...}** 测试右标签页的文件夹。
- **{ifpathD:...}** 测试目标标签页的文件夹。**L**、**R** 和 **D** 字符必须是大写。你通常只会在为两边同时共享的单个状态栏定义时才使用这些特定于一侧的变体（如今通常不推荐这种做法）。当为文件窗口的每一侧使用状态栏时，如果你从另一侧测试某一侧的路径，你可能会得到意外的结果，因为每个状态栏只更新响应于影响其自身侧面的更改，不更新对另一侧的更改。
</td></tr><tr><td>
{ifexists:...}</td><td>

**测试路径是否存在**  
使用 **{ifexists:...}** 测试文件系统中的项目是否存在。如果在指定路径处存在文件或文件夹，测试将返回真；找到文件或文件夹不会产生差别。

与 **{ifpath:...}** 代码一样，引号是可选项，但如果路径中包含 **{** 或 **}** 字符，则必须使用引号。

你可以测试绝对路径是否存在：

**{ifexists:C:\Docs\My Special File.txt}** -- 如果“C:\Docs\My Special File.txt”存在，则为真。

你还可以测试相对路径是否存在（即相对于文件夹标签页的当前位置）。相对路径 *必须* 以 **.\\**（表示当前目录）或 **..\\**（表示当前目录的父目录）开头。

**{ifexists:".\Help"}** -- 如果“Help”存在于当前目录下，则为真。

可以在最后一个路径组件中使用基本的 \* 通配符：

**{ifexists:".\\.dll"}** -- 如果当前目录下存在任何 \*.dll 文件（或文件夹！），则为真。

与 **{ifpath:...}** 一样，你可以使用路径前放置 **!** 来否定测试：

**{ifexists:!"C:\Test\\.dll"}** -- 如果“C:\Test”中不存在 \*.dll 文件，则为真。

与 **{ifpath:...}** 一样，并且有其上方章节中讨论的类似注意事项，你可以使用 **{ifexistsL:...}**、**{ifexistsR:...}** 和 **{ifexistsD:...}** 以目标左、右或目标侧，而不是活动侧。

我们不建议测试网络驱动器上的路径，因为如果驱动器速度较慢或不可访问，这可能会造成严重的延迟。（Windows 需要最多 30 秒才能决定无法访问网络路径，并且可以阻止在此期间尝试访问的程序。）在可移动驱动器上测试路径或测试它们的存在也可能产生不希望有的副作用，但这取决于你正在测试的驱动器类型。
</td></tr><tr><td>

{if:...}   
{ifset:...}</td><td>

**测试 Set 和其他命令**  
类似于 **@if** 和 **@ifset** [命令限定符](../command_reference/command_modifier_reference.zh.md)，你可以测试[内部命令](../command_reference/internal_commands/README.zh.md)的状态，以确定是否应该隐藏状态栏部分。

*“命令的状态”* 通常表示如果将命令放置在工具栏按钮上，按钮是否会显示“按下”或激活。例如，**Set VIEW=Details** 命令将在文件列表为**详细信息**模式时显示为激活。

与 **{ifpath:...}** 代码一样，引号是可选项，但如果命令中包含 **{** 或 **}** 字符，则必须使用引号。

**{if:Set VIEW=Details}** -- 如果文件列表为“详细信息”模式，则为真。  
**{if:Toolbar NAME="My Toolbar" TOGGLE}** -- 如果“My Toolbar”已打开，则为真。

**{ifset:...}** 仅仅是 **{if:Set...}** 的同义词，为了与程序其他部分中类似命令的兼容性而保留。

**{ifset:VIEW=Details}** -- 等同于 **{if:Set VIEW=Details}**

与 **{ifpath:...}** 一样，您可以使用路径前放置 **!** 来否定测试：

**{if:!Set VIEW=Details}** -- 如果文件列表不是“详细信息”模式，则为真。

作为一个示例用例，你可能希望在缩略图等模式下状态栏显示所选文件的时间和大小，而在详细信息模式下删除额外的杂项，因为详细信息模式在其中列中显示相同信息。你可以使用以下代码来实现此目的：

**{h!{if:!Set VIEW=Details}}{sel:size} {sel:write}{h!}**

与 **{ifpath:...}** 一样，并且有其上方章节中讨论的类似注意事项，你可以使用 **{ifL:...}**、**{ifR:...}** 和 **{ifD:...}** 以目标左、右或目标侧，而不是活动侧。
将以下英文文本翻译成中文：