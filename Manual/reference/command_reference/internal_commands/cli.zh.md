# CLI

**CLI** 内部命令可用于：

- 打开 [CLI/临时脚本编辑器](/Manual/additional_functionality/cli.zh.md) 窗口
- 打开 MS-DOS 提示符（其当前目录设置为文件窗口中当前文件夹）
- 让 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段以各种模式显示。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*无参数*</td><td>
-</td><td>
-</td><td>

打开 [CLI/临时脚本编辑器](/Manual/additional_functionality/cli.zh.md) 窗口的实例。
</td></tr><tr><td>
DOSPROMPT</td><td>
/O</td><td>

*(无值)*</td><td>

打开 DOS 提示符，其当前目录设置为源文件列表中显示的文件夹。你可以在 **CLI** 命令之前使用 **cd** 指令来覆盖当前目录（需要使用高级命令编辑器）。

*示例：* `CLI DOSPROMPT`
</td></tr><tr><td>
</td><td>
</td><td>

**selfolder**</td><td>

使用源显示中第一个选定的子文件夹作为 DOS 提示符的光盘。

*示例：* `CLI DOSPROMPT=selfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**admin**</td><td>

在 Vista 及以上系统中，提升 DOS 提示符（在 UAC 提示符之后）。

*示例：* `CLI DOSPROMPT=admin`
</td></tr><tr><td>
</td><td>
</td><td>

**noadmin**</td><td>

防止 DOS 提示符被提升。

*示例：* `CLI DOSPROMPT=noadmin`
</td></tr><tr><td>
</td><td>
</td><td>

**powershell**</td><td>

打开 PowerShell 提示符，而不是 DOS 提示符。

*示例：* `CLI DOSPROMPT=powershell,admin`

可以分别使用 **EXEC** 和 **TITLE** 参数来选择要运行的 PowerShell 版本并设置窗口标题。
</td></tr><tr><td>
</td><td>
</td><td>

**powershellise**</td><td>

打开 PowerShell ISE，而不是 DOS 提示符。

*示例：* `CLI DOSPROMPT=powershellise`

在启动 PowerShell ISE 时，将忽略任何颜色参数。此限制仅影响 ISE；DOS 提示符和常规 PowerShell 窗口都可以指定颜色。
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<color\>*</td><td>

设置 DOS 窗口的文本和背景颜色。你可以单独使用它，也可以与 admin 参数结合使用，以在提示符提升时覆盖默认颜色。\<color\> 值由两个十六进制数字指定 - 第一个对应于背景颜色，第二个对应于前景。可能的颜色取决于你的系统设置，但默认如下：

**支持的颜色值**  
\<WRAP\>

|               |                  |                  |                  |
|---------------|------------------|------------------|------------------|
| 0 = 黑色     | 1 = 蓝色         | 2 = 绿色        | 3 = 浅蓝色        |
| 4 = 红色       | 5 = 紫色       | 6 = 黄色       | 7 = 白色        |
| 8 = 灰色      | 9 = 浅蓝色   | A = 浅绿色  | B = 浅绿色   |
| C = 浅红色 | D = 浅紫色 | E = 浅黄色 | F = 亮白色 |

\</WRAP\>\<wrap clear/\>

请注意，在使用 **color** 参数时，你必须将 **DOSPROMPT** 参数的整个值用引号括起来（否则嵌入的 **=** 符号会让命令解析器感到困惑）。

*示例：* `CLI DOSPROMPT="admin,color=97"`
</td></tr><tr><td>
</td><td>
</td><td>

**nocolor**</td><td>

防止提升时设置 DOS 提示符的颜色。

*示例：* `CLI DOSPROMPT=admin,nocolor`
</td></tr><tr><td>
</td><td>
</td><td>

**wsl**</td><td>

打开 WSL (Windows 子系统 for Linux) shell 窗口。请注意，必须从 Windows Store 安装 WSL。

*示例：* `CLI DOSPROMPT=wsl`
</td></tr><tr><td>
EXEC</td><td>
/K</td><td>

*\<command\>*</td><td>

打开 PowerShell 提示符时，覆盖默认可执行文件以启动。例如，你可能希望创建一个按钮，该按钮运行 PowerShell 7 而不是 Windows PowerShell。

*示例：* `CLI DOSPROMPT=powershell EXEC="C:\Program Files\PowerShell\7\pwsh.exe"`
</td></tr><tr><td>
QUICKCMD</td><td>
/O/R</td><td>

*(无值)*</td><td>

在命令模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，这让你可以输入一个临时 Opus 命令并在当前文件列表中执行。这让你可以将一个 [热键](/Manual/customize/the_customize_dialog/keys.zh.md) 绑定到以特定模式显示即时查找字段。

*示例：* `CLI QUICKCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

在命令模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的命令对其进行初始化。

以 **noselect:** 为前缀，将光标放在命令的末尾，而不是最初选中它进行覆盖。

*示例：* `CLI QUICKCMD Help`  
*示例：* `CLI QUICKCMD noselect:Help`
</td></tr><tr><td>
QUICKDOSCMD</td><td>
/O/R</td><td>

*(无值)*</td><td>

在 DOS 命令模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，这让你可以输入一个命令在 DOS 提示符中执行。

*示例：* `CLI QUICKDOSCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

在 DOS 命令模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的命令对其进行初始化。

以 **noselect:** 为前缀，将光标放在命令的末尾，而不是最初选中它进行覆盖。

*示例：* `CLI QUICKDOSCMD dir`  
*示例：* `CLI QUICKDOSCMD noselect:dir`
</td></tr><tr><td>
QUICKFILTER</td><td>
/O/R</td><td>

*(无值)*</td><td>

在 Filter 模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，这让你可以过滤当前文件列表。

*示例：* `CLI QUICKFILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

在 Filter 模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的模式对其进行初始化。

以 **noselect:** 为前缀，将光标放在模式的末尾，而不是最初选中它进行覆盖。

*示例：* `CLI QUICKFILTER \*.(jpg\|png)`  
*示例：* `CLI QUICKFILTER noselect:\*.jpg`
</td></tr><tr><td>
QUICKFIND</td><td>
/O/R</td><td>

*(无值)*</td><td>

在 Find 模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，这让你可以滚动到与输入字符串匹配的第一个文件。

*示例：* `CLI QUICKFIND`
</td></tr><tr><td>
</td><td>
</td><td>

*\<search string\>*</td><td>

在 Find 模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的字符串对其进行初始化。

以 **noselect:** 为前缀，将光标放在字符串的末尾，而不是最初选中它进行覆盖。

*示例：* `CLI QUICKFIND di`  
*示例：* `CLI QUICKFIND noselect:di`
</td></tr><tr><td>
QUICKFINDREPEAT</td><td>
/O</td><td>

*(无值)*</td><td>

重复上次 **QUICKFIND**。此命令的行为取决于 **在关闭字段后保留高亮是否可见** 配置设置的状态。
</td></tr>
如果在即时查找字段关闭后仍显示高亮，**QUICKFINDREPEAT** 会将焦点转移到下一个匹配项。如果没有显示高亮，**QUICKFINDREPEAT** 会重复上次查找，使用上次使用的相同搜索字符串在当前文件夹中再次搜索匹配项。

*示例：* `CLI QUICKFINDREPEAT`
</td></tr><tr><td>
</td><td>
</td><td>

**next**</td><td>

明确地搜索下一个匹配项，无论是否可见高亮。

*示例：* `CLI QUICKFINDREPEAT=next`
</td></tr><tr><td>
</td><td>
</td><td>

**prev**</td><td>

明确地搜索上一个匹配项，无论是否可见高亮。

*示例：* `CLI QUICKFINDREPEAT=prev`
</td></tr><tr><td>
QUICKFOLDERS</td><td>
/O/R</td><td>

*(无值)*</td><td>

在文件夹模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，该字段会显示一个从标签历史记录列表、最近列表、收藏夹和快速访问中提取的文件夹列表。此列表的来源可以从 [文件夹模式](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/folders_mode.zh.md) 配置页面进行配置。

*示例：* `CLI QUICKFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<search string\>*</td><td>

在文件夹模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的搜索字符串对其进行初始化。

使用 **noselect：** 作为前缀以将光标置于字符串末尾，而不是最初选中它以便进行覆盖键入。

\`\`CLI QUICKFOLDERS noselect:C:\\\`
</td></tr><tr><td>
QUICKFTPCMD</td><td>
/O/R</td><td>

*(无值)*</td><td>

以特殊模式显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，该模式允许你输入一个命令，可以将其直接发送到远程 FTP 服务器。此命令仅在你当前已连接到 FTP 站点时起作用。你可以在 [FTP 日志](/Manual/ftp/ftp_log.zh.md) 中查看命令的结果。

*示例：* `CLI QUICKFTPCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

使用 FTP 命令模式在 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段中显示，并使用指定的命令对其进行初始化。

使用 **noselect：** 作为前缀以将光标置于命令末尾，而不是最初选中它以便进行覆盖键入。

*示例：* `CLI QUICKFTPCMD chmod \* 755`  
*示例：* `CLI QUICKFTPCMD noselect:chmod` \*
</td></tr><tr><td>
QUICKGO</td><td>
/O/R</td><td>

*(无值)*</td><td>

在特殊模式下（“快速进入”模式）显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，该模式允许你导航到当前文件列表中的另一个文件夹。

*示例：* `CLI QUICKGO`
</td></tr><tr><td>
</td><td>
</td><td>

*\<path\>*</td><td>

在“快速进入”模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的路径对其进行初始化。

使用 **noselect：** 作为前缀以将光标置于路径末尾，而不是最初选中它以便进行覆盖键入。

*示例：* `CLI QUICKGO C:\Program Files`  
\`\`CLI QUICKGO noselect:C:\\\`
</td></tr><tr><td>
QUICKRANGE</td><td>
/O/R</td><td>

*(无值)*</td><td>

在范围模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，该模式允许你按索引（或索引范围）选择文件。这仅在已将索引列添加到文件列表中时起作用。

*示例：* `CLI QUICKRANGE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<range\>*</td><td>

在范围模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的范围字符串对其进行初始化。

使用 **noselect：** 作为前缀以将光标置于范围字符串末尾，而不是最初选中它以便进行覆盖键入。

*示例：* `CLI QUICKRANGE 1-10,20-30`  
*示例：* `CLI QUICKRANGE noselect:1-10`
</td></tr><tr><td>
QUICKSEARCH</td><td>
/O/R</td><td>

*(无值)*</td><td>

在搜索模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，该模式允许你启动对当前文件夹的 [Windows 搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md)。

*示例：* `CLI QUICKSEARCH`
</td></tr><tr><td>
</td><td>
</td><td>

*\<query term\>*</td><td>

在搜索模式下显示 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的查询术语对其进行初始化。

使用 **noselect：** 作为前缀以将光标置于查询字符串末尾，而不是最初选中它以便进行覆盖键入。

*示例：* `CLI QUICKSEARCH author:davidson`  
*示例：* `CLI QUICKSEARCH noselect:author:davidson`
</td></tr><tr><td>
QUICKSEARCHENGINE</td><td>
/K</td><td>

*\<engine\>\[,\<options\>\]*</td><td>

与 **QUICKSEARCH** 参数一起使用以指定在搜索模式下要使用的搜索引擎。每个搜索引擎都有自己的一组选项，这些选项也可以包含在命令中。

请注意，**everything** 和 **everythingglobal** 引擎要求安装 [Everything](/Manual/additional_functionality/everything_integration.zh.md)。

| 引擎           | 说明                                                                           | 可选项        |
|------------------|---------------------------------------------------------------------------------------|----------------|
| everything       | 使用 *Everything* 搜索当前文件夹                                          | case           |
|                  |                                                                                       | diacritics     |
|                  |                                                                                       | wholeword      |
|                  |                                                                                       | regexp         |
| everythingglobal | 使用 *Everything* 搜索整个系统                                            | case           |
|                  |                                                                                       | diacritics     |
|                  |                                                                                       | wholeword      |
|                  |                                                                                       | regexp         |
| opus             | 使用 Opus [查找工具](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md) 进行搜索 | anywords       |
|                  |                                                                                       | case           |
|                  |                                                                                       | content        |
|                  |                                                                                       | nodiacritics   |
|                  |                                                                                       | nonames        |
|                  |                                                                                       | nopartial      |
|                  |                                                                                       | nowild         |
|                  |                                                                                       | utf8           |
| windows          | 使用 Windows 搜索搜索当前文件夹                                        | noautowildcard |
|                  |                                                                                       | nqs            |

*示例:* `CLI QUICKSEARCH A\*.jpg QUICKSEARCHENGINE everything,case`
</td></tr><tr><td>
QUICKSELECT</td><td>
/O/R</td><td>

*(无值)*</td><td>

在选择模式下显示 [按输入搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，通过该字段，您可以通过 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 选择当前文件夹中的文件。

*示例:* `CLI QUICKSELECT`
</td></tr><tr><td>
</td><td>
</td><td>

*\<模式\>*</td><td>

在选择模式下显示 [按输入搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定模式进行初始化。

在前面加上 **noselect：** 以将光标放置在模式的末尾，而不是最初选择它来进行输入覆盖。

*示例:* `CLI QUICKSELECT \*.doc`  
*示例:* `CLI QUICKSELECT noselect:\*.doc`
</td></tr><tr><td>
QUICKTABS</td><td>
/O/R</td><td>

*(无值)*</td><td>

在标签模式下显示 [按输入搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，通过该字段，您可以搜索并切换文件夹标签。

*示例:* `CLI QUICKTABS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<模式\>*</td><td>

在标签模式下显示 [按输入搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段并使用指定的文本对其进行初始化。

在前面加上 **noselect：** 以将光标放置在文本的末尾，而不是最初选择它来进行输入覆盖。

*示例:* `CLI QUICKTABS docu`  
*示例:* `CLI QUICKTABS noselect:docu`
</td></tr><tr><td>
QUICKWSLCMD</td><td>
/O/R</td><td>

*(无值)*</td><td>

在 WSL 脚本模式中显示 [按键搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，通过该字段，您可以在 WSL（针对 Linux 的 Windows 系统）窗口中输入要执行的命令。请注意，需要从 Windows 商店安装 WSL。

*示例:* `CLI QUICKWSLCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<命令\>*</td><td>

在 WSL 脚本模式中显示 [按输入搜索](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段，并使用指定的命令对其进行初始化。

在前面加上 **noselect：** 以将光标放置在命令的末尾，而不是最初选择它来进行输入覆盖。

*示例:* `CLI QUICKWSLCMD ls`  
*示例:* `CLI QUICKWSLCMD noselect:ls`
</td></tr><tr><td>
SCRIPTMODE</td><td>
/O</td><td>

*(无值)*</td><td>

在脚本模式下显示 CLI，它提供了一种在将 [脚本](/Manual/scripting/README.zh.md) 添加到按钮之前对其进行测试的简单方法。

*示例:* `CLI SCRIPTMODE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<语言\>*</td><td>

在脚本模式下显示 CLI，其中语言类型设置为指定的语言。如果您未指定语言，CLI 会记住以前使用的语言。

*示例:* `CLI SCRIPTMODE=jscript`
</td></tr><tr><td>
TITLE</td><td>
/K</td><td>

*\<命令\>*</td><td>

打开 PowerShell 提示符时定义窗口标题。

*示例:* `CLI DOSPROMPT=powershell TITLE="Windows PowerShell"`
</td></tr></tbody>
</table>