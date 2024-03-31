# 有关路径的代码

以下代码用于将各种路径传递给外部程序。可用的路径代码提供了以下三个条件的所有可能组合：

- **Which path -** 当前源路径或目标路径，或在双栏文件窗口中，无论其源/目标状态如何，左（上）或右（下）路径。
- **路径必需**或**路径不必需** - 如果需要路径，如果没有该路径，则根本不会运行命令 - 例如，当没有有效的目标文件夹时。当路径不必需时，命令仍然会被运行，并且它将表现得好像路径代码根本不存在一样。
- **长文件名**或**短文件名** - 短文件名对于运行 16 位程序或其他无法处理长文件名的旧版软件非常有用。

每个代码的长形式由反映这三个条件的关键字组合组成。如果长代码以**$**符号结尾，则它是代码的“路径必需”形式 - 说是“需要”一个有效的路径。请注意，**左**和**右**路径不支持“必需”形式。

<table>
<thead><tr><th>
长形式</th><th>
短形式</th><th>
描述
</th></tr></thead><tbody><tr><td>
{sourcepath}</td><td>
{s!}</td><td>
源路径，长文件名，非必需。
</td></tr><tr><td>

{sourcepath\$}</td><td>
{s}</td><td>
源路径，长文件名，必需。
</td></tr><tr><td>
{destpath}</td><td>
{d!}</td><td>
目标路径，长文件名，非必需。
</td></tr><tr><td>

{destpath\$}</td><td>
{d}</td><td>
目标路径，长文件名，必需。
</td></tr><tr><td>
{sourcepathshort}</td><td>
{ss!}</td><td>
源路径，短文件名，非必需。
</td></tr><tr><td>

{sourcepathshort\$}</td><td>
{ss}</td><td>
源路径，短文件名，必需。
</td></tr><tr><td>
{destpathshort}</td><td>
{ds!}</td><td>
目标路径，短文件名，非必需。
</td></tr><tr><td>

{destpathshort\$}</td><td>
{ds}</td><td>
目标路径，短文件名，必需。
</td></tr><tr><td>
{leftpath}</td><td>
{l}</td><td>
左（上）路径，长文件名。
</td></tr><tr><td>
{rightpath}</td><td>
{r}</td><td>
右（下）路径，长文件名。
</td></tr><tr><td>
{leftpathshort}</td><td>
{ls}</td><td>
左路径，短文件名。
</td></tr><tr><td>
{rightpathshort}</td><td>
{rs}</td><td>
右路径，长文件名。
</td></tr></tbody>
</table>

除了与当前文件窗口路径相关的路径代码之外，以下代码还允许您传递某些系统或特定于应用程序的路径的值。

<table>
<thead><tr><th>
长形式</th><th>
短形式</th><th>
描述
</th></tr></thead><tbody><tr><td>
{apppath}</td><td>
{p}</td><td>

返回已安装应用程序的路径，如下 *App Paths* 列在注册表中的键。例如，**{apppath\|winword.exe}** 将插入 Microsoft Word 的安装路径。
</td></tr><tr><td>
{apppathshort}</td><td>
{ps}</td><td>
已安装应用程序的路径，采用短（8.3）格式。
</td></tr><tr><td>
{alias}</td><td>
{A}</td><td>

返回 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md) 的路径。例如，**{alias\|mydocuments}** 将返回指向您的文档文件夹的路径。

您可以使用 **{alias\|libraries}** 来解析库文件夹的路径；例如，**{alias\|libraries}/Documents** 将返回“文档”库的真实（默认）路径。
</td></tr><tr><td>
{aliasshort}</td><td>
{As}</td><td>
文件夹别名的路径，采用短（8.3）格式。
</td></tr></tbody>
</table>

路径代码支持以下修饰符。可以使用垂直线 (**\|**) 将这些修饰符添加到控制代码序列中，以将文件名代码与修饰符分开 - 例如，**{sourcepath\|noterm}** 从路径中删除尾随终止字符。可以使用其他垂直线提供多个修饰符，以将它们分开 - 例如 **{sourcepath\|nopath\|noterm}** 将 **nopath** 和 **noterm** 结合在一起。

<table>
<thead><tr><th>
修饰符</th><th>
描述
</th></tr></thead><tbody><tr><td>

**escbackslash**</td><td>

自动转义路径中出现的所有 **\\**，将它们变为 **\\**。  
当使用 **{sourcepath}** 等代码将路径插入到将对 \n 和 \\ 等序列进行特殊解释的字符串中时，这可能是必要的。  
例如，将源路径和目标路径添加到剪贴板的命令在单独的行上：

**[剪贴板](../internal_commands/clipboard.zh.md) EXPANDNEWLINES SET {sourcepath\|escbackslash}\n{destpath\|escbackslash}**.

在此示例中，如果源路径为 *C:\New Folder\\*，则它将转换为 *C:\\New Folder\\*。如果没有转义 *N* 序列，它会将字母 *N* 从路径中删除，并将 *ew Folder\\* 放在单独的行上。更微妙的是，如果源路径末尾的 *\\* 也未转义，它将干扰示例命令中两个路径之间的 *\n*。
</td></tr><tr><td>

**escforfilter**</td><td>

旨在将路径插入到内联过滤器定义中。  
与将 **escbackslash** 和 **escwild** 结合使用相同，但更容易记住且键入的更少。
</td></tr><tr><td>

**escnl**</td><td>

自动转义路径中出现的所有 **\n**，将它们变为 **\\n**。  
（这是上面 **escbackslash** 的较弱版本。您可能应该改用 **escbackslash**。）  
当将 **{sourcepath}** 这样的代码用作 **[{dlgstring}](codes_to_display_dialogs.zh.md)** 等对话框代码的消息文本时，使用 **escnl** 会有所帮助。例如，路径 *C:\New Folder\\* 会转换为 *C:\\New Folder\\*。如果不转义 **\n** 序列，它将转换成对话框消息文本中的换行符。
</td></tr><tr><td>

**escregex**  
**escregexp**</td><td>

自动转义路径中的任何正则表达式字符。在将路径传递给理解 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 的内部命令时使用，以防路径包含诸如 **\\**、**.**、**(** 和 **)** 等对某些函数有特殊含义的字符。例如，**{sourcepath\|escregexp\|noterm}** 将 *C:\Accounts (2010)\\* 转换为 *C:\\Accounts \\2010\\*。  
为方便起见，允许同时使用“regex”和“regexp”拼写，并且它们的作用相同。
</td></tr><tr><td>

**escwild**</td><td>

自动转义路径中的任何通配符。在将路径传递给理解 [标准通配符](../../wildcard_reference/pattern_matching_syntax.zh.md) 的内部命令时使用，以防路径包含诸如 **(** 和 **)** 等对某些函数有特殊含义的字符。例如，**{sourcepath\|escwild\|noterm}** 将 *C:\Accounts (2010)\\* 转换为 *C:\Accounts '(2010')*。
</td></tr><tr><td>

**nopath**</td><td>

仅返回路径的最终组件。例如，如果 **{sourcepath}** 返回 *C:\Program Files\GPSoftware\Directory Opus\\*，则 **{sourcepath\|nopath}** 将返回 *Directory Opus\\*。
</td></tr><tr><td>

**noroot**</td><td>

返回没有根的路径，即没有第一个组件。例如，如果 **{sourcepath}** 返回 *C:\Program Files\GPSoftware\Directory Opus\\*，则 **{sourcepath\|noroot}** 将返回 *Program Files\GPSoftware\Directory Opus\\*。对于 UNC 网络路径，结果将相对于共享，同时会删除计算机和共享本身。对于 FTP 路径，结果将相对于站点的根目录并排除站点本身。您可以将 **noroot** 与 **..** 结合使用，以获取已删除根的父路径。例如，**{sourcepath\|..\|noroot}**
**noshort**

抑制对长于 260 个字符的路径的自动缩短。Opus 本身可以处理非常长的路径，但许多 Windows 程序不行。将非常长的路径发送至外部程序时，Opus 通常会使用较短的（8.3）版本以减少问题。使用 **noshort**，当你知道目标程序可以处理时，可以防止这种情况。例如，**{sourcepath\|noshort}**。

**noterm**

从返回的路径中去掉尾部路径分隔符。例如，**{sourcepath\|noterm}** 可能会返回 *C:\Program Files\GPSoftware\Directory Opus*。

**subdir**

替换路径中的字符，以便可以将它添加到另一个路径下方。例如，**{sourcepath\|subdir}** 可能会返回 *C;\Program Files*。请注意，分号已替换冒号，允许路径用作子目录，例如，如果你想将文件从那里备份到 *D:\Backups\C;\Program Files*。

**cleanfilename**

替换字符串中的所有非法文件名字符，也替换所有路径分隔符和冒号，这样该字符串就可以用作文件名而不添加任何附加路径级别。在此上下文中类似于 **subdir**，但它也替换路径分隔符。

**cleanfilepath**

替换字符串中的所有非法文件名字符，同时保留路径分隔符和冒号。（冒号仅保留在字符串开头作为驱动器号的一部分时。）当字符串可以是绝对路径时，应该使用它。（在此上下文中通常不会产生影响，因为输入应该已经是有效的文件名或路径。在剪贴板数据的情况下更有用。）

**cleanfilepathrel**

替换字符串中的所有非法文件名字符，也替换冒号和 "\\" UNC 路径发起器，这样该字符串就可以用作另一个路径下的子目录。在此上下文中类似于 **subdir**，因为输入已经是文件名或路径。（与 **subdir** 不同，**cleanfilepathrel** 也可以与任意的剪贴板输入一起使用。）

**wsl**

以 WSL（Windows 系统 dành cho Linux）格式返回路径（例如 **/mnt/c/Program Files/** 而不是 **C:\Program Files**）。

**pair**

如果相关路径有 [配对文件夹](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.zh.md)，则此修饰符会返回它的配对项。你可以将它与其他修饰符结合使用，例如 **{sourcepath\|pair\|..}** 会返回该配对项的父项。

可以使用附加修饰符来覆盖配对文件夹的“如果不存在”模式。例如，你可能需要在按钮中使用它，如果配对文件夹不存在，则创建该文件夹。支持的修饰符有 **pairgotoparent**、**pairignorepair** 和 **pairuseanyway**。

**..**

修改代码以引用路径的父项而不是路径本身。你可以传递多个 **..** 修饰符，它们由 **\\** 分隔，以返回树中较高的文件夹。例如，**{destpath\|..\\.}** 会返回当前目标路径的父项的父项。

**\\**

修改代码以引用指定路径的驱动器根目录。例如，**{sourcepath\|\\** 可能会返回 **C:\\**。