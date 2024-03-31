# 用于传递文件名代码

下列代码用于将选定文件的名称传递给外部程序。可用的文件名代码提供以下五个标准的所有可能组合：

- **完整路径**或**仅文件名** - 传递选定项的完整路径和名称（例如, *C:\Program Files\GPSoftware\Directory Opus\dopus.exe*）或仅文件名（例如, *dopus.exe*）。
- **逐个传递**或**全部一起传递** - 当选择多个文件时，这将确定命令是针对每个选定的文件重复执行一次，还是仅执行一次，并将所有选定的文件名作为空格分隔符传递到同一命令行中。
- **需要选定项**或**不需要选定项** - 当需要选定项并且未选择任何项时，将根本不会运行命令。当不需要选定项时，命令仍将运行且会像完全不存在文件名代码一样。
- **长文件名**或**短文件名** - 短文件名对运行 16 位程序或其他无法处理长文件名的旧软件很有用。
- **源文件**或**目标文件列表** - 在双栏文件窗口中，您可以从目标文件列表和源文件中传递选定的文件。

每个代码的长格式是由反映五个标准的关键字组合而成的。如果长代码以 **\$** 符结尾，则它是代码的 “需要选定项” 格式 - 它被表示为 “需要” 选定项。

<table>
<thead><tr><th>
长格式</th><th>
短格式</th><th>
说明
</th></tr></thead><tbody><tr><td>
{filepath}</td><td>
{f!}</td><td>

传递每个选定项的完整路径和文件名。逐个传递文件 - 使用此代码的命令将针对每个附加选定项重复执行一次。如果未选择任何文件，仍然会运行此命令，为此代码传递一个空字符串。  
*逐个提供完整路径，不需要选定项，长文件名，源文件列表*
</td></tr><tr><td>

{filepath\$}</td><td>
{f}</td><td>

**{filepath}** 的 “需要” 格式（需要的文件列表中至少有一个选定项）。  
*逐个提供完整路径，需要选定项，长文件名，源文件列表*
</td></tr><tr><td>
{file}</td><td>
{o!}</td><td>

仅传递每个选定项的文件名（不带路径）。逐个传递多个文件。  
逐个提供文件名，不需要选定项，长文件名，源文件列表
</td></tr><tr><td>

{file\$}</td><td>
{o}</td><td>

**{file}** 的 “需要” 格式。  
*逐个提供文件名，需要选定项，长文件名，源文件列表*
</td></tr><tr><td>
{allfilepath}</td><td>
{F!}</td><td>

一次性传递所有选定项的完整路径和文件名。无论选择了多少项，命令都会只运行一次 - 所有已选定项的名称将作为空格分隔符传递到命令行中。您可以使用替代分隔符字符指定 **sep=** 修饰符（如下所述）。  
*一次性提供完整路径，不需要选定项，长文件名，源文件列表*
</td></tr><tr><td>

{allfilepath\$}</td><td>
{F}</td><td>

**{allfilepath}** 的 “需要” 格式。  
*一次性提供完整路径，需要选定项，长文件名，源文件列表*
</td></tr><tr><td>
{allfile}</td><td>
{O!}</td><td>

一次性传递所有选定项的仅文件名。不传递文件路径。  
一次性提供文件名，不需要选定项，长文件名，源文件列表
</td></tr><tr><td>

{allfile\$}</td><td>
{O}</td><td>

**{allfile}** 的 “需要” 格式。  
一次性提供文件名，需要选定项，长文件名，源文件列表
</td></tr><tr><td>
{filepathshort}</td><td>
{fs!}</td><td>

以短（8.3）格式传递每个选定项的完整路径和文件名。这对于运行 16 位程序或其他无法处理长文件名的旧软件很有用。  
*逐个提供完整路径，不需要选定项，短文件名，源文件列表*
</td></tr><tr><td>

{filepathshort\$}</td><td>
{fs}</td><td>

**{filepathshort}** 的 “需要” 格式。  
*逐个提供完整路径，需要选定项，短文件名，源文件列表*
</td></tr><tr><td>
{fileshort}</td><td>
{os!}</td><td>

以短（8.3）格式传递每个选定项的仅文件名（无路径）。  
逐个提供文件名，不需要选定项，短文件名，源文件列表
</td></tr><tr><td>

{fileshort\$}</td><td>
{os}</td><td>

**{fileshort}** 的 “需要” 格式。  
逐个提供文件名，需要选定项，短文件名，源文件列表
</td></tr><tr><td>
{allfilepathshort}</td><td>
{Fs!}</td><td>

一次性传递所有选定项的完整路径和文件名的短（8.3）格式。  
*一次性提供完整路径，不需要选定项，短文件名，源文件列表*
</td></tr><tr><td>

{allfilepathshort\$}</td><td>
{Fs}</td><td>

**{allfilepathshort}** 的 “需要” 格式。  
*一次性提供完整路径，需要选定项，短文件名，源文件列表*
</td></tr><tr><td>
{allfileshort}</td><td>
{Os!}</td><td>

一次性传递所有选定项的仅文件名，以短（8.3）格式。  
一次性提供文件名，不需要选定项，短文件名，源文件列表
</td></tr><tr><td>

{allfileshort\$}</td><td>
{Os}</td><td>

**{allfileshort}** 的 “需要” 格式。  
一次性提供文件名，需要选定项，短文件名，源文件列表
</td></tr><tr><td>
{filepathdest}</td><td>
{fd!}</td><td>

传递目标文件列表中每个选定项的完整路径和文件名。逐个传递文件 - 使用此代码的命令将针对每个附加选定项重复执行一次。如果目标中未选择任何文件，或当前没有目标文件夹，仍将运行此命令，为此代码传递空字符串。  
*逐个提供完整路径，不需要选定项，长文件名，目标文件列表*
</td></tr><tr><td>

{filepathdest\$}</td><td>
{fd}</td><td>

**{filepathdest}** 的 “需要” 格式。如果目标中没有选定任何文件，或者当前没有目标文件夹，那么将不会执行此命令。  
*逐个提供完整路径，需要选定项，长文件名，目标文件列表*
</td></tr><tr><td>
{filedest}</td><td>
{od!}</td><td>

仅传递目标文件列表中每个选定项的文件名（不带路径）。逐个传递多个文件。  
逐个提供文件名，不需要选定项，长文件名，目标文件列表
</td></tr><tr><td>

{filedest\$}</td><td>
{od}</td><td>

**{filedest}** 的 “需要” 格式。  
逐个提供文件名，需要选定项，长文件名，目标文件列表
</td></tr><tr><td>
{allfilepathdest}</td><td>
{Fd!}</td><td>

一次性传递来自目标文件列表的所有选定项的完整路径和文件名。无论选择了多少项，命令都会只运行一次 - 所有已选定项的名称将作为空格分隔符传递到命令行中。
</td></tr><tr><td>

{allfilepathdest\$}</td><td>
{Fd}</td><td>

**{allfilepathdest}** 的“需要”形式。  
*完整的路径，同时，不需要所选项目，长文件名，目标文件列表*
</td></tr><tr><td>
{allfiledest}</td><td>
{Od!}</td><td>

一次性传递所有所选项目的仅文件名，从目标文件列表中。不传递文件路径。  
仅文件名，同时，不需要所选项目，长文件名，目标文件列表
</td></tr><tr><td>

{allfiledest\$}</td><td>
{Od}</td><td>

**{allfiledest}** 的“需要”形式。  
仅文件名，同时，需要所选项目，长文件名，目标文件列表
</td></tr><tr><td>
{filepathshortdest}</td><td>
{fsd!}</td><td>

从目标文件列表中，以短（8.3）格式传递每个所选项目的完整路径和文件名。这对于运行 16 位程序或其他无法处理长文件名的旧版软件非常有用。  
*完整的路径，一次一个，不需要所选项目，短文件名，目标文件列表*
</td></tr><tr><td>

{filepathshortdest\$}</td><td>
{fsd}</td><td>

**{filepathshortdest}** 的“需要”形式。  
*完整的路径，一次一个，需要所选项目，短文件名，目标文件列表*
</td></tr><tr><td>
{fileshortdest}</td><td>
{osd!}</td><td>

以短（8.3）格式，从目标文件列表中传递每个所选项目的仅文件名（无路径）。  
仅文件名，一次一个，不需要所选项目，短文件名，目标文件列表
</td></tr><tr><td>

{fileshortdest\$}</td><td>
{osd}</td><td>

**{fileshortdest}** 的“需要”形式。  
仅文件名，一次一个，需要所选项目，短文件名，目标文件列表
</td></tr><tr><td>
{allfilepathshortdest}</td><td>
{Fsd!}</td><td>

一次性从目标文件列表中，以短（8.3）格式传递所有所选项目的完整路径和文件名的短形式。  
*完整的路径，同时，不需要所选项目，短文件名，目标文件列表*
</td></tr><tr><td>

{allfilepathshortdest\$}</td><td>
{Fsd}</td><td>

**{allfilepathshortdest}** 的“需要”形式。  
*完整的路径，同时，需要所选项目，短文件名，目标文件列表*
</td></tr><tr><td>
{allfileshortdest}</td><td>
{Osd!}</td><td>

一次性从目标文件列表中，以短（8.3）格式传递所有所选项目的仅文件名。  
仅文件名，同时，不需要所选项目，短文件名，目标文件列表
</td></tr><tr><td>

{allfileshortdest\$}</td><td>
{Osd}</td><td>

**{allfileshortdest}** 的“需要”形式。  
仅文件名，同时，需要所选项目，短文件名，目标文件列表
</td></tr></tbody>
</table>

文件名代码都支持以下修改器。这些修改器可以通过竖线 (**\|**) 添加到控制代码序列中，以将文件名代码与修改器分开 - 例如，**{file\|noext}** 从返回的文件名中剥离文件扩展名。可以使用额外的竖线提供多个修改器，以将它们分开 - 例如 **{file\|noext\|escwild}** 将 **noext** 和 **escwild** 同时组合在一起。

<table>
<thead><tr><th>
修改器</th><th>
描述
</th></tr></thead><tbody><tr><td>

**noext**</td><td>

从文件名中剥离文件名扩展名。例如，如果 **{file}** 返回 *cat_photo.jpg*，则 **{file\|noext}** 将返回 *cat_photo*。请注意，如果该项目是一个文件夹，则它的名称不会被更改，即使它包含一个点，因为文件夹不被认为具有文件扩展名。
</td></tr><tr><td>

**ext**</td><td>

仅返回文件名扩展名（与 **noext** 相反）。例如，如果 **{file}** 返回 *cat_photo.jpg*，则 **{file\|ext}** 将返回 *.jpg*。请注意，如果该项目是一个文件夹，即使文件夹的名称包含一个点，也不会返回任何内容。
</td></tr><tr><td>

**ext2**</td><td>

返回没有点的文件名扩展名。例如，如果 **{file\|ext}** 返回 *.jpg*，则 **{file\|ext2}** 将返回 *jpg*。
</td></tr><tr><td>

**ext=***\<ext\>*</td><td>

用指定的文件扩展名替换原始文件名扩展名。例如，**{file\|ext=tmp}** 将返回每个所选文件的名称，其扩展名更改为 *.tmp*。即使文件夹名称包含点，文件夹名称也不会更改。
</td></tr><tr><td>

**escbackslash**</td><td>

自动转义文件名中所有 **\\** 的出现，将它们变成 **\\**。  
使用诸如 **{filepath}** 之类的代码将路径插入到字符串中时，这可能很有必要，该字符串的序列（如 \n 和 \\）将被特殊解释。  
例如，将源中的所选文件和目标中的所选文件添加到剪贴板的命令，每一行都有一条单独的命令：

**[剪贴板](../internal_commands/clipboard.zh.md) EXPANDNEWLINES SET {filepath\|escbackslash}\n{filepathdest\|escbackslash}**.

在这个示例中，如果源文件是 *C:\New Folder\test.txt*，则它将被转换成 *C:\\New Folder\\text.txt*。如果 *\N* 序列没有被转义，它将从路径中删除字母 *N*，并将 *ew Folder\text.txt* 放在单独的一行中。（在处理文件夹路径时，还有一些更微妙的情况，但在处理文件路径时，它们的重要性较低。）
</td></tr><tr><td>

**escforfilter**</td><td>

旨在将路径插入到内联过滤定义中。  
与 **escbackslash** 和 **escwild** 的组合相同，但更容易记住且输入量少。
</td></tr><tr><td>

**escnl**</td><td>

自动转义文件名中所有 **\n** 的出现，将它们变成 **\\n**。  
（这是上面 **escbackslash** 的一个较弱版本。您可能应该使用 **escbackslash** 代替。）  
在将代码（如 **{filepath}**）用作诸如 **[{dlgstring}](codes_to_display_dialogs.zh.md)** 之类的对话框代码的消息文本时，使用 **escnl** 会有所帮助。例如，路径 *C:\New Folder\test.txt* 将被转换成 *C:\\New Folder\test.txt*。如果 *\N* 序列没有被转义，它将被转换成对话框消息文本中的换行符。
</td></tr><tr><td>

**escregex**  
**escregexp**</td><td>

自动转义文件名中的所有正则表达式字符。用于将文件名传递给理解 [正则表达式](../../wildcard_reference/regular_expression_syntax.zh.md) 的内部命令，以防文件名包含诸如 **\\**, **.**, **(** 和 **)** 等对某些函数具有特殊含义的字符。例如，**{file\|escregexp\|noext}** 将 *Accounts (2010).xls* 变成 *Accounts \\2010\\*。  
为方便起见，**“regex”** 和 **“regexp”** 拼写都是允许的，并且作用相同。
</td></tr><tr><td>

**escwild**</td><td>

自动转义文件名中的所有通配符。用于将文件名传递给理解 [标准通配符](../../wildcard_reference/pattern_matching_syntax.zh.md) 的内部命令，以防文件名包含诸如 **(** 和 **)** 等对某些函数具有特殊含义的字符。例如，**{file\|escwild\|noext}** 将 *Accounts (2010).xls* 变成 *Accounts '(2010')*。
**file**

将文件名重定向到一个临时文本文件中。这对于可以从文本文件（而不是命令行）接受文件列表的外部程序非常有用。（反过来，由于命令行有最大长度限制，这可能会限制您直接传递的文件名数量，因此非常有用。）临时文件的文件名在命令行中传递，以代替文件名。在文本文件中，每个文件名都用空格分隔。如果文件名或其路径包含嵌入空格，则会在文件名或路径周围加上引号。例如，**{allfilepath\|file}**。

**filem**

与**file**相同，不同之处在于每个文件名都写入到文本文件的单独行中。例如，**{allfilepath\|filem}**。

**fileq**

与**file**相同，不同之处在于每个文件名始终用引号括起来，无论是否包含嵌入空格。例如，**{allfilepath\|fileq}**。

**filemq**

与**filem**相同，不同之处在于每个文件名始终用引号括起来。例如，**{allfilepath\|filemq}**。

**utf8**

强制**file、filem**或**fileq**编写的文件使用UTF-8格式。例如，**{allfilepath\|filem\|utf8}**。

**ucsle**

强制**file、filem**或**fileq**编写的文件使用UCS-16LE格式。例如，**{allfilepath\|filem\|ucsle}**。

**ucsbe**

强制**file、filem**或**fileq**编写的文件使用UCS-16BE格式。例如，**{allfilepath\|filem\|ucsbe}**。

**urlencode**

URL-编码它添加到命令行的文件名。如果您想以某种方式将文件名传递到互联网，则很有用。例如，您可以有一个上下文菜单命令，使用以下方式自动针对选定的文件名进行Google搜索：**[https://www.google.com/search?q={file\|urlencode](https://www.google.com/search?q=%7Bfile%7Curlencode)}**

**nobom**

防止写入BOM以识别文件类型。例如，**{allfilepath\|filem\|utf8\|nobom}**。

**cronly**

如果与**filem**或**filemq**一起使用，可以使文件在每行之间仅包含CR（回车）字符。默认情况下是CR，LF对，这是Windows的标准。例如，**{allfilepath\|filem\|cronly}**。

**lfonly**

如果与**filem**或**filemq**一起使用，可以使文件在每行之间仅包含LF（换行符）字符。默认情况下是CR，LF对，这是Windows的标准。例如，**{allfilepath\|filem\|lfonly}**。

**nopath**

仅返回路径的最后一个组件。例如，如果**{filepath}**返回*C:\Program Files\GPSoftware\Directory Opus\\*，则**{filepath\|nopath}**将返回*Directory Opus\\*。通常，您会使用类似**{file}**的东西来仅获取某个名称，但是使用**{filepath\|nopath}**的细微差别在于当该项是文件夹时会包含名称末尾的\\。

**noroot**

从文件的路径中移除根（即第一个组件）。例如，如果**{filepath}**返回*C:\Windows\Notepad.exe*，则**{filepath\|noroot}**将返回*Windows\Notepad.exe*。对于UNC网络路径，结果相对于共享，其中计算机和共享本身已被移除。对于FTP路径，结果相对于站点的根目录，并且不包括站点本身。您可以将**noroot**与**..**相结合，以获取已移除根的父路径。例如，**{filepath\|..\|noroot}**

**noshort**

抑制对长度超过260个字符的文件路径的自动缩短。Opus本身可以处理非常长的路径，但许多Windows程序无法处理。在将非常长的路径发送到外部程序时，Opus通常使用短（8.3）版本来减少问题。当您知道目标程序可以应对时，请使用**noshort**来防止这种情况。例如，**{filepath\|noshort}**。

**noterm**

从文件夹路径中删除尾部路径分隔符。例如，**{filepath}**可能会返回*C:\Program Files\\*，而**{filepath\|noterm}**将返回*C:\Program Files*。

**notermdrive**

类似于**noterm**，但当结果路径是驱动器根目录且没有子目录时也会删除尾部路径分隔符。例如，**{sourcepath}**和**{sourcepath\|noterm}**可能都会返回*C:\\*，而*C:*将由**{sourcepath\|notermdrive}**返回。驱动器根目录是Windows中的特殊情况，通常需要一个尾部反斜杠，但有一些例外情况（例如Windows**subst**命令），其中必须省略反斜杠。

**subdir**

替换文件路径中的字符，以便可以将完整路径添加到另一个路径之下。例如，**{filepath\|subdir}**可能会返回*C;\Windows\Notepad.exe*。请注意，分号已替换冒号，允许路径相对于另一个目录使用，例如如果您想创建名为*D:\Backups\C;\Windows\Notepad.exe*的文件的备份。

**regex**

允许测试和操作文件名。

|                                                     |                                                                                              |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| **{file\|regex=*\<pattern\>*)**                     | 仅在模式匹配时处理文件；否则将跳过该文件                                            |
| **{file\|regex=*\<pattern\>*\|to=*\<new name\>*)**  | 输出正则表达式搜索和替换的结果（仅在模式匹配时）                                   |
| **{file\|regex!=*\<pattern\>*\|to=*\<new name\>*)** | 与上面相同，但如果模式不匹配，则输出原始文件名（保持不变）                                 |

如果您的正则表达式包含\|符号，则应将整个模式用引号括起来。

**cleanfilename**

替换字符串中的任何非法文件名字符，并替换所有路径分隔符和冒号，以便该字符串可以用作文件名，而不会添加任何其他路径级别。在此上下文中类似于**subdir**，但它也替换路径分隔符。

**cleanfilepath**

替换字符串中的任何非法文件名字符，同时保留路径分隔符和冒号。（仅当它们是字符串开头处驱动器号的一部分时，才会保留冒号。）当字符串可以是绝对路径时，应该使用此字符串。（通常在此上下文中没有效果，因为输入应该已经是有效的文件名或路径。对于剪贴板数据更有用。）

**cleanfilepathrel**

替换字符串中的任何非法文件名字符，同时替换冒号和“\\”UNC路径启动符，以便该字符串可以用作另一个路径下的子目录。在此上下文中类似于**subdir**，因为输入已经是文件名或路径。（与**subdir**不同，**cleanfilepathrel**还可以与任意剪贴板输入一起使用。）
</td></tr><tr><td>

**wsl**</td><td>

以 WSL（适用于 Linux 的 Windows 系统）格式返回路径（例如 **/mnt/c/Program Files/** 而不是 **C:\Program Files**）。
</td></tr><tr><td>

**sep=**</td><td>

允许你为在单行中插入多个文件名的代码指定备用分隔符。例如，**{allfilepath}** 通常以空格分隔插入所有选定文件路径。你可以使用 **{allfilepath\|sep=,}** 使文件路径以逗号分隔。
</td></tr><tr><td>

**..**</td><td>

将代码修改为引用所选项目的父文件夹，而不是项目本身。你可以使用多个以 **\\** 分隔的 .. 修饰符来返回树中更高级别的文件夹。例如，**{filepath\|..\\.}** 将返回项目父级的父级的名称。
</td></tr><tr><td>

**\\**</td><td>

将代码修改为引用所选项目驱动器的根。例如，**{filepath\|\\** 可能会返回 **C:\\**。
</td></tr><tr><td>

**driveletter**</td><td>

将代码修改为引用所选项目路径开头的驱动器盘符，单独引用。例如，**{filepath\|driveletter}** 可能会返回 *C*。如果路径不属于某个驱动器盘符，将按原样插入整个路径。  
你还可以使用 **{filepath\|\\** 获取类似 *C:\\* 的结果，或使用 **{filepath\|\\notermdrive}** 获取类似于 *C:* 的结果，同时对非驱动器根（例如 UNC 路径）进行不同的处理。
</td></tr><tr><td>

**drivelabel**</td><td>

将代码修改为引用所选项目路径开头的驱动器盘符的标签。例如，**{filepath\|drivelabel}** 可能会返回 *System*。如果路径不属于某个驱动器盘符，将按原样插入整个路径。
</td></tr></tbody>
</table>

除了上述代码外，还支持以下控制代码，以确保与 Windows资源管理器兼容。在 MS-DOS 批处理函数中不能使用这些代码。

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
如果已选择任何内容，则为 {filepath}；否则为 {sourcepath}
</td></tr><tr><td>

**%**\*</td><td>
{allfilepath}
</td></tr></tbody>
</table>