# 用于传递文件名代码

以下代码用于将所选文件的名字传递给外部程序。可用的文件名代码提供了以下五个标准的所有可能组合：

- **完整路径** 或 **仅文件名** - 是否传递所选项目的完整路径和名称（例如 *C:\Program Files\GPSoftware\Directory Opus\dopus.exe*）还是只传递文件名（例如 *dopus.exe*）。
- **一次一个** 或 **一次全部** - 当选择多个文件时，这将确定是否对每个选定文件重复执行一次命令，或者只执行一次，并将所有选定文件名传递到同一个命令行上（用空格隔开）。
- **需要选择项目** 或 **不需要选择项目** - 当需要选择项目且没有选择任何项目时，命令将根本不会运行。当不需要选择项目时，命令仍将运行，并且它将表现得好像文件名代码根本不存在。
- **长文件名** 或 **短文件名** - 短文件名对于运行 16 位程序或其它无法处理长文件名的旧软件很有用。
- **源** 或 **目标文件列表** - 在双栏文件窗口中，您可以传递来自目标文件列表的所选文件，以及来自源的所选文件。

每个代码的长格式都是由反映五个标准的关键词组合而成的。如果长代码以 **\$** 符号结尾，则它是代码的“需要选择项目”形式 - 它被称为“需要”选择项目。

<table>
<thead><tr><th>
长格式</th><th>
短格式</th><th>
说明
</th></tr></thead><tbody><tr><td>
{filepath}</td><td>
{f!}</td><td>

传递每个选定项目的完整路径和文件名。一次传递一个文件 - 使用此代码的命令将针对每个额外的选定项目重复执行一次。如果没有选择任何文件，命令仍将运行，为该代码传递一个空字符串。  
*完整路径，一次一个，不需要选择项目，长文件名，源文件列表*
</td></tr><tr><td>

{filepath\$}</td><td>
{f}</td><td>

**{filepath}** 的“需要”形式（需要文件列表中至少选择一个项目）。  
*完整路径，一次一个，需要选择项目，长文件名，源文件列表*
</td></tr><tr><td>
{file}</td><td>
{o!}</td><td>

传递每个选定项目的仅文件名（不带其路径）。一次传递多个文件。  
仅文件名，一次一个，不需要选择项目，长文件名，源文件列表
</td></tr><tr><td>

{file\$}</td><td>
{o}</td><td>

**{file}** 的“需要”形式。  
*仅文件名，一次一个，需要选择项目，长文件名，源文件列表*
</td></tr><tr><td>
{allfilepath}</td><td>
{F!}</td><td>

一次传递所有选定项目的完整路径和文件名。命令将只运行一次，无论选择了多少项目 - 所有选定项目的名称将在命令行中用空格隔开传递。您可以使用 **sep=** 修饰符（在下面描述）指定替代分隔符。  
*完整路径，一次全部，不需要选择项目，长文件名，源文件列表*
</td></tr><tr><td>

{allfilepath\$}</td><td>
{F}</td><td>

**{allfilepath}** 的“需要”形式。  
*完整路径，一次全部，需要选择项目，长文件名，源文件列表*
</td></tr><tr><td>
{allfile}</td><td>
{O!}</td><td>

一次传递所有选定项目的仅文件名。不会传递文件路径。  
仅文件名，一次全部，不需要选择项目，长文件名，源文件列表
</td></tr><tr><td>

{allfile\$}</td><td>
{O}</td><td>

**{allfile}** 的“需要”形式。  
仅文件名，一次全部，需要选择项目，长文件名，源文件列表
</td></tr><tr><td>
{filepathshort}</td><td>
{fs!}</td><td>

传递每个选定项目的完整路径和文件名，以短格式（8.3）。这对于运行 16 位程序或其它无法处理长文件名的旧软件很有用。  
*完整路径，一次一个，不需要选择项目，短文件名，源文件列表*
</td></tr><tr><td>

{filepathshort\$}</td><td>
{fs}</td><td>

**{filepathshort}** 的“需要”形式。  
*完整路径，一次一个，需要选择项目，短文件名，源文件列表*
</td></tr><tr><td>
{fileshort}</td><td>
{os!}</td><td>

传递每个选定项目的仅文件名（不带路径），以短格式（8.3）。  
仅文件名，一次一个，不需要选择项目，短文件名，源文件列表
</td></tr><tr><td>

{fileshort\$}</td><td>
{os}</td><td>

**{fileshort}** 的“需要”形式。  
仅文件名，一次一个，需要选择项目，短文件名，源文件列表
</td></tr><tr><td>
{allfilepathshort}</td><td>
{Fs!}</td><td>

一次传递所有选定项目的完整路径和文件名的短格式（8.3）。  
*完整路径，一次全部，不需要选择项目， 短文件名，源文件列表*
</td></tr><tr><td>

{allfilepathshort\$}</td><td>
{Fs}</td><td>

**{allfilepathshort}** 的“需要”形式。  
*完整路径，一次全部，需要选择项目， 短文件名，源文件列表*
</td></tr><tr><td>
{allfileshort}</td><td>
{Os!}</td><td>

一次传递所有选定项目的仅文件名，以短格式（8.3）。  
仅文件名，一次全部，不需要选择项目，短文件名，源文件列表
</td></tr><tr><td>

{allfileshort\$}</td><td>
{Os}</td><td>

**{allfileshort}** 的“需要”形式。  
仅文件名，一次全部，需要选择项目，短文件名，源文件列表
</td></tr><tr><td>
{filepathdest}</td><td>
{fd!}</td><td>

传递目标文件列表中每个选定项目的完整路径和文件名。一次传递一个文件 - 使用此代码的命令将针对每个额外的选定项目重复执行一次。如果目标中没有选择任何文件，或者当前没有目标，命令仍将运行，为该代码传递一个空字符串。  
*完整路径，一次一个，不需要选择项目，长文件名， 目标文件列表*
</td></tr><tr><td>

{filepathdest\$}</td><td>
{fd}</td><td>

**{filepathdest}** 的“需要”形式。如果目标中没有选择任何文件，或者当前没有目标，命令将不会执行。  
*完整路径，一次一个，需要选择项目，长文件名， 目标文件列表*
</td></tr><tr><td>
{filedest}</td><td>
{od!}</td><td>

传递来自 目标文件列表的每个选定项目的仅文件名（不带其路径）。一次传递多个文件。  
仅文件名，一次一个，不需要选择项目，长文件名，目标文件列表
</td></tr><tr><td>

{filedest\$}</td><td>
{od}</td><td>

**{filedest}** 的“需要”形式。  
*仅文件名，一次一个，需要选择项目，长文件名，目标文件列表*
</td></tr><tr><td>
{allfilepathdest}</td><td>
{Fd!}</td><td>

一次传递来自目标文件列表的所有选定项目的完整路径和文件名。命令将只运行一次，无论选择了多少项目 - 所有选定项目的名称将在命令行中用空格隔开传递。  
*完整路径，一次全部，不需要选择项目，长文件名， 目标文件列表*
</td></tr><tr><td>

{allfilepathdest\$}</td><td>
{Fd}</td><td>

**{allfilepathdest}** 的“需要”形式。  
*完整路径，一次全部，需要选择项目，长文件名， 目标文件列表*
</td></tr><tr><td>
{allfiledest}</td><td>
{Od!}</td><td>

一次传递所有选定项目的仅文件名，来自目标文件列表。不会传递文件路径。  
仅文件名，一次全部，不需要选择项目，长文件名，目标文件列表
</td></tr><tr><td>

{allfiledest\$}</td><td>
{Od}</td><td>

**{allfiledest}** 的“需要”形式。  
仅文件名，一次全部，需要选择项目，长文件名，目标文件列表
</td></tr><tr><td>
{filepathshortdest}</td><td>
{fsd!}</td><td>

传递每个选定项目的完整路径和文件名，以短格式（8.3），来自目标文件列表。这对于运行 16 位程序或其它无法处理长文件名的旧软件很有用。  
*完整路径，一次一个，不需要选择项目，短文件名， 目标文件列表*
</td></tr><tr><td>

{filepathshortdest\$}</td><td>
{fsd}</td><td>

**{filepathshortdest}** 的“需要”形式。  
*完整路径，一次一个，需要选择项目，短文件名， 目标文件列表*
</td></tr><tr><td>
{fileshortdest}</td><td>
{osd!}</td><td>

传递目标文件列表中每个选定项目的仅文件名（不带路径），以短格式（8.3）。  
仅文件名，一次一个，不需要选择项目，短文件名， 目标文件列表
</td></tr><tr><td>

{fileshortdest\$}</td><td>
{osd}</td><td>

**{fileshortdest}** 的“需要”形式。  
*仅文件名，一次一个，需要选择项目，短文件名， 目标文件列表*
</td></tr><tr><td>
{allfilepathshortdest}</td><td>
{Fsd!}</td><td>

一次传递所有选定项目的完整路径和文件名的短格式（8.3），来自目标文件列表。  
*完整路径，一次全部，不需要选择项目， 短文件名， 目标文件列表*
</td></tr><tr><td>

{allfilepathshortdest\$}</td><td>
{Fsd}</td><td>

**{allfilepathshortdest}** 的“需要”形式。  
*完整路径，一次全部，需要选择项目， 短文件名， 目标文件列表*
</td></tr><tr><td>
{allfileshortdest}</td><td>
{Osd!}</td><td>

一次传递所有选定项目的仅文件名，以短格式（8.3），来自目标文件列表。  
仅文件名，一次全部，不需要选择项目，短文件名， 目标文件列表
</td></tr><tr><td>

{allfileshortdest\$}</td><td>
{Osd}</td><td>

**{allfileshortdest}** 的“需要”形式。  
仅文件名，一次全部，需要选择项目，短文件名， 目标文件列表
</td></tr></tbody>
</table>

文件名代码都支持以下修饰符。可以使用竖线（**\|**）将文件名代码与修饰符分隔开来，将这些修饰符添加到控制代码序列中 - 例如，**{file\|noext}** 从返回的文件名中删除文件扩展名。可以使用额外的竖线分隔符来提供多个修饰符 - 例如，**{file\|noext\|escwild}** 将 **noext** 和 **escwild** 组合在一起。

<table>
<thead><tr><th>
修饰符</th><th>
说明
</th></tr></thead><tbody><tr><td>

**noext**</td><td>

从文件名中删除文件扩展名。例如，如果 **{file}** 返回 *cat_photo.jpg*，那么 **{file\|noext}** 将返回 *cat_photo*。请注意，如果该项目是文件夹，则其名称不会改变，即使它包含一个点，因为文件夹不被认为具有文件扩展名。
</td></tr><tr><td>

**ext**</td><td>

仅返回文件扩展名（与 **noext** 相反）。例如，如果 **{file}** 返回 *cat_photo.jpg*，那么 **{file\|ext}** 将返回 *.jpg*。请注意，如果该项目是文件夹，则不会返回任何内容，即使文件夹的名称包含一个点。
</td></tr><tr><td>

**ext2**</td><td>

返回没有点的文件扩展名。例如，如果 **{file\|ext}** 返回 *.jpg*，那么 **{file\|ext2}** 将返回 *jpg*。
</td></tr><tr><td>

**ext=***\<ext\>*</td><td>

将原始文件扩展名替换为指定的扩展名。例如，**{file\|ext=tmp}** 将返回每个选定文件的名称，其扩展名更改为 *.tmp*。文件夹名称不会更改，即使它们包含点。
</td></tr><tr><td>

**escbackslash**</td><td>

自动转义文件名中出现的任何 **\\**，将其转换为 **\\**。  
当使用像 **{filepath}** 这样的代码将路径插入到将像 \n 和 \\ 这样的序列专门解释的字符串中时，这可能是必要的。  
例如，一个命令将来自源的选定文件和来自目标的选定文件添加到剪贴板中的单独行：

**[Clipboard](../internal_commands/clipboard.zh.md) EXPANDNEWLINES SET {filepath\|escbackslash}\n{filepathdest\|escbackslash}**.

在这个例子中，如果源文件是 *C:\New Folder\test.txt*，那么它将被转换为 *C:\\New Folder\\text.txt*。如果 *\N* 序列没有被转义，它将从路径中删除字母 *N*，并将 *ew Folder\text.txt* 放在单独的一行上。（在处理文件夹路径时，还有更微妙的情况，但在文件路径中不太重要。）
</td></tr><tr><td>

**escforfilter**</td><td>

用于将路径插入内联过滤器定义中。  
与 **escbackslash** 和 **escwild** 相同，但更容易记忆，而且输入更少。
</td></tr><tr><td>

**escnl**</td><td>

自动转义文件名中出现的任何 **\n**，将其转换为 **\\n**。  
（这是上面 **escbackslash** 的一个较弱的版本。您应该使用 **escbackslash** 代替。）  
使用 **escnl** 有助于在使用像 **{filepath}** 这样的代码作为像 **[{dlgstring}](codes_to_display_dialogs.zh.md)** 这样的对话框代码的消息文本时。例如，路径 *C:\New Folder\test.txt* 将被转换为 *C:\\New Folder\test.txt*。如果 *\N* 序列没有被转义，它将被转换为对话框消息文本中的换行符。
</td></tr><tr><td>

**escregex**  
**escregexp**</td><td>

自动转义文件名中出现的任何正则表达式字符。在将文件名传递给理解 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 的内部命令时使用，以防文件名包含像 **\\**、**.**、**(** 和 **)** 这样的字符，这些字符对某些函数具有特殊含义。例如，**{file\|escregexp\|noext}** 将 *Accounts (2010).xls* 转换为 *Accounts \\2010\\*。  
为了方便起见，允许使用“regex”和“regexp”拼写，并且它们执行相同操作。
</td></tr><tr><td>

**escwild**</td><td>

自动转义文件名中出现的任何通配符字符。在将文件名传递给理解 [标准通配符](../../wildcard_reference/pattern_matching_syntax.zh.md) 的内部命令时使用，以防文件名包含像 **(** 和 **)** 这样的字符，这些字符对某些函数具有特殊含义。例如，**{file\|escwild\|noext}** 将 *Accounts (2010).xls* 转换为 *Accounts '(2010')*。
</td></tr><tr><td>

**file**</td><td>

将文件名重定向到一个临时文本文件。这对于能够从文本文件而不是命令行接收文件列表的外部程序很有用。（反过来，这很有用，因为命令行有最大长度，这可能会限制您可以直接传递的文件名的数量。）临时文件的名称将在命令行中传递，以代替文件名本身。在文本文件中，每个文件名用空格隔开。如果文件名或其路径包含嵌入的空格，它将用引号包围。例如，**{allfilepath\|file}**.
</td></tr><tr><td>

**filem**</td><td>

与 **file** 相同，只是每个文件名都在文本文件中写在一行上。例如，**{allfilepath\|filem}**.
</td></tr><tr><td>

**fileq**</td><td>

与 **file** 相同，只是每个文件名总是用引号包围，无论它是否包含嵌入的空格。例如，**{allfilepath\|fileq}**.
</td></tr><tr><td>

**filemq**</td><td>

与 **filem** 相同，只是每个文件名总是用引号包围。例如，**{allfilepath\|filemq}**.
</td></tr><tr><td>

**utf8**</td><td>

强制 **file**、**filem** 或 **fileq** 写入的文件使用 UTF-8 格式。例如，**{allfilepath\|filem\|utf8}**.
</td></tr><tr><td>

**ucsle**</td><td>

强制 **file**、**filem** 或 **fileq** 写入的文件使用 UCS-16LE 格式。例如，**{allfilepath\|filem\|ucsle}**.
</td></tr><tr><td>

**ucsbe**</td><td>

强制 **file**、**filem** 或 **fileq** 写入的文件使用 UCS-16BE 格式。例如，**{allfilepath\|filem\|ucsbe}**.
</td></tr><tr><td>

**urlencode**</td><td>

对它添加到命令行中的文件名进行 URL 编码。如果要以某种方式将文件名传递到 Internet，这很有用。 例如，您可以有一个上下文菜单命令，它对选定的文件名执行自动 Google 搜索：**[https://www.google.com/search?q={file\|urlencode](https://www.google.com/search?q=%7Bfile%7Curlencode)}**
</td></tr><tr><td>

**nobom**</td><td>

防止写入 BOM，该 BOM 用于识别文件类型。例如，**{allfilepath\|filem\|utf8\|nobom}**.
</td></tr><tr><td>

**cronly**</td><td>

在与 **filem** 或 **filemq** 一起使用时，使文件只有 CR（回车）字符位于每行之间。默认值为 CR、LF 对，这是 Windows 上的标准。例如，**{allfilepath\|filem\|cronly}**.
</td></tr><tr><td>

**lfonly**</td><td>

在与 **filem** 或 **filemq** 一起使用时，使文件只有 LF（换行符）字符位于每行之间。默认值为 CR、LF 对，这是 Windows 上的标准。例如，**{allfilepath\|filem\|lfonly}**.
</td></tr><tr><td>

**nopath**</td><td>

仅返回路径的最后一个组件。例如，如果 **{filepath}** 返回 *C:\Program Files\GPSoftware\Directory Opus\\*，**{filepath\|nopath}** 将返回 *Directory Opus\\*。您通常会使用类似 **{file}** 的东西来获取某个东西的名称，但使用 **{filepath\|nopath}** 有一个微妙的区别，即当该项目是文件夹时，它会在名称的末尾包含 \\。
</td></tr><tr><td>

**noroot**</td><td>

从文件的路径中删除根（即第一个组件）。例如，如果 **{filepath}** 返回 *C:\Windows\Notepad.exe*，**{filepath\|noroot}** 将返回 *Windows\Notepad.exe*。对于 UNC 网络路径，结果相对于共享，计算机和共享本身将被删除。对于 FTP 路径，结果相对于站点的根，并且不包含站点本身。您可以将 **noroot** 与 **..** 组合在一起，以获得删除根的父路径。例如，**{filepath\|..\|noroot}**
</td></tr><tr><td>

**noshort**</td><td>

抑制自动缩短超过 260 个字符的文件路径。Opus 本身可以处理非常长的路径，但许多 Windows 程序不能。在将非常长的路径发送到外部程序时，Opus 通常使用短格式（8.3）来减少问题。如果知道目标程序可以处理，请使用 **noshort** 来防止这种情况。例如，**{filepath\|noshort}**.
</td></tr><tr><td>

**noterm**</td><td>

从文件夹路径中删除尾随路径分隔符。例如，**{filepath}** 可能会返回 *C:\Program Files\\*，而 **{filepath\|noterm}** 将返回 *C:\Program Files*。
</td></tr><tr><td>

**notermdrive**</td><td>

类似于 **noterm**，但如果结果路径是驱动器根，没有子目录，也会删除尾随路径分隔符。例如，**{sourcepath}** 和 **{sourcepath\|noterm}** 都可能返回 *C:\\*，而 **{sourcepath\|notermdrive}** 将返回 *C:*。驱动器根是 Windows 中的一个特例，通常需要尾随反斜杠，但有一些例外（比如 Windows **subst** 命令），反斜杠必须省略。
</td></tr><tr><td>

**subdir**</td><td>

替换文件路径中的字符，以便可以将完整路径添加到另一个路径下方。例如，**{filepath\|subdir}** 可能会返回 *C;\Windows\Notepad.exe*。请注意，分号已替换了冒号，允许路径相对于另一个目录使用，例如，如果您想创建名为 *D:\Backups\C;\Windows\Notepad.exe* 的文件的备份。
</td></tr><tr><td>

**regex**</td><td>

允许测试和操作文件名。

|                                                     |                                                                                              |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| **{file\|regex=*\<pattern\>*)**                     | 仅当模式匹配时才处理文件；否则将跳过                                                     |
| **{file\|regex=*\<pattern\>*\|to=*\<new name\>*)**  | 输出正则表达式搜索和替换的结果（仅当模式匹配时）                                      |
| **{file\|regex!=*\<pattern\>*\|to=*\<new name\>*)** | 与上面相同，但如果模式不匹配，则输出原始文件名，保持不变                         |

如果您的正则表达式包含 \| 符号，您应该将整个模式括在引号中。
</td></tr><tr><td>

**cleanfilename**</td><td>

替换字符串中任何非法的文件名字符，以及替换所有路径分隔符和冒号，以便字符串可以用作文件名，而不会添加任何额外的路径级别。在这种情况下，类似于 **subdir**，但它也替换了路径分隔符。
</td></tr><tr><td>

**cleanfilepath**</td><td>
替换字符串中任何非法的文件名字符，同时保留路径分隔符和冒号。（如果冒号是字符串开头的驱动器字母的一部分，则只保留冒号。）如果字符串可以是绝对路径，则应使用它。（在这种情况下通常不会有任何影响，因为输入应该已经是有效的文件名或路径。在处理剪贴板数据时更有用。）
</td></tr><tr><td>

**cleanfilepathrel**</td><td>

替换字符串中任何非法的文件名字符，也替换冒号和 "\\" UNC 路径启动器，以便字符串可以用作另一个路径下的子目录。在这种情况下，类似于 **subdir**，因为输入已经是文件名或路径。（与 **subdir** 不同，**cleanfilepathrel** 也可以用于任意剪贴板输入。）
</td></tr><tr><td>

**wsl**</td><td>

以 WSL（Windows 针对 Linux 的子系统）格式返回路径（例如 **/mnt/c/Program Files/** 而不是 **C:\Program Files**）。
</td></tr><tr><td>

**sep=**</td><td>

允许您为在同一行上插入多个文件名的代码指定替代分隔符。例如，**{allfilepath}** 通常会插入所有选定的文件路径，并用空格隔开。您可以使用 **{allfilepath\|sep=,}** 使文件路径用逗号隔开。
</td></tr><tr><td>

**..**</td><td>

修改代码以引用选定项目的父文件夹，而不是项目本身。您可以通过 **\\** 分隔传递多个 **..** 修饰符，以返回树中更高层的文件夹。例如，**{filepath\|..\\.}** 将返回项目的父项目的名称。
</td></tr><tr><td>

**\\**</td><td>

修改代码以引用选定项目驱动器的根。例如，**{filepath\|\\** 可能返回 **C:\\**。
</td></tr><tr><td>

**driveletter**</td><td>

修改代码以引用选定项目路径开头的驱动器字母，单独存在。例如，**{filepath\|driveletter}** 可能返回 *C*。如果路径不是相对于驱动器字母，则将插入整个路径，保持原样。  
您也可以使用 **{filepath\|\\** 来获取类似 *C:\\* 的东西，或者使用 **{filepath\|\\notermdrive}** 来获取类似 *C:* 的东西，同时以不同的方式处理非驱动器根（例如 UNC 路径）。
</td></tr><tr><td>

**drivelabel**</td><td>

修改代码以引用选定项目路径开头的驱动器字母的标签。例如，**{filepath\|drivelabel}** 可能返回 *System*。如果路径不是相对于驱动器字母，则将插入整个路径，保持原样。
</td></tr></tbody>
</table>

除了上面的代码之外，还支持以下控制代码，以提供与 Windows 资源管理器的兼容性。它们不能在 MS-DOS 批处理函数中使用。

<table>
<thead><tr><th>
修饰符</th><th>
等效于
</th></tr></thead><tbody><tr><td>

**%1**</td><td>
{filepath}
</td></tr><tr><td>

**%2**</td><td>
{filepath}
</td></tr><tr><td>

**%L**</td><td>
{filepath}
</td></tr><tr><td>

**%V**</td><td>
如果选择了任何内容，则为 {filepath}；否则为 {sourcepath}
</td></tr><tr><td>

**%**\*</td><td>
{allfilepath}
</td></tr></tbody>
</table>