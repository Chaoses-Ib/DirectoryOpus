# Find
**查找**内部命令可用于：

- 显示 [查找面板](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)，您可以在其中执行文件搜索
- 自动化查找文件功能以执行简单的搜索，而无需显示用户界面
- 自动化 [重复文件查找器](/Manual/additional_functionality/duplicate_file_finder.zh.md) 功能

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示查找面板。它将以您上次使用的模式打开。

*示例 :* `Find`
</td></tr><tr><td>
高级</td><td>
/S</td><td>

*(无值)*</td><td>

以 [高级](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md) 模式显示查找面板。

*示例 :* `Find ADVANCED`
</td></tr><tr><td>
任意词</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以启用 *任意单词* 选项进行名称搜索时使用。
例如，如果已启用此功能，并且将“cat dog”用作 **名称** 参数，Opus将匹配包含“cat”或“dog”（或两者，按任何顺序）的文件名。这避免了构造复杂的 OR 通配符模式。

*示例 :* `Find NAME="cat dog" ANYWORD RECURSE IN "c:\\`
</td></tr><tr><td>
档案</td><td>
/S</td><td>

*(无值)*</td><td>

在压缩包文件中搜索（在自动化查找文件功能时）。

*示例 :* `Find *.doc IN C:\Data ARCHIVES`
</td></tr><tr><td>
双方</td><td>
/S</td><td>

*(无值)*</td><td>

使用 **SYNC** 参数自动化同步工具时，这使您可以启用 **双向复制文件** 选项。

//<示例：//>有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
案例</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以指定 **NAME** 参数应被视为区分大小写的时使用，类似于 UI 中的相关复选框。

*示例 :* `Find *.DOC IN C:\ RECURSE CASE`
</td></tr><tr><td>
CLEAR</td><td>
/O</td><td>

*(无值)*</td><td>

清除先前结果（在自动化查找文件功能时）。在开始新的查找之前，将清除输出文件集合。

*示例 :* `Find *.doc IN C:\Data CLEAR`
</td></tr><tr><td>
</td><td>
</td><td>

**不**</td><td>

不清除以前的结果。

*示例 :* `Find *.doc in C:\Data CLEAR=no`
</td></tr><tr><td>
COLLNAME</td><td>
/K</td><td>

*\<集合名称\>*</td><td>

指定将结果添加到其中的文件集合的名称。如果未提供，则使用默认集合（*查找结果* 和 *重复文件*）。

*示例 :* `Find *.doc in C:\Data COLLNAME Output`
</td></tr><tr><td>
COMPARE</td><td>
/K</td><td>

**大小**</td><td>

将同步工具与 **SYNC** 参数一起自动化时，这使您可以选择按大小比较文件。默认情况下，它将寻找不同的尺寸；您还可以指定 **size,smaller** 或 **size,larger**。

//<示例：//>有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
</td><td>
</td><td>

**日期**</td><td>

将同步工具与 **SYNC** 参数一起自动化时，这使您可以选择按日期比较文件。默认情况下，它将寻找不同的日期；您还可以指定 **较新**。这也可与 **大小** 结合使用。
</td></tr><tr><td>
</td><td>
</td><td>

**compare**</td><td>

将同步工具与 **SYNC** 参数一起自动化时，这使您可以选择通过比较文件数据（哈希）来比较文件。
</td></tr><tr><td>
计算机</td><td>
/S</td><td>

*(无值)*</td><td>

启动 Windows *搜索计算机* 功能（根据您的 Windows 版本，这可能不起作用）。

*示例 :* `Find COMPUTERS`
</td></tr><tr><td>
包含</td><td>
/K</td><td>

*\<搜索文本\>*</td><td>

指定要搜索的文本（在自动化查找文件功能时）。

*示例 :* `Find *.txt CONTAINING printf IN C:\SourceCode`
</td></tr><tr><td>
CONTANYWORD</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以指定在“任何单词”模式下处理 **包含** 参数时使用，类似于 UI 中的相关复选框。

*示例 :* `Find *.txt CONTAINING "apple pear peach plum" CONTANYWORD IN C:\Inventory`
</td></tr><tr><td>
CONTCASE</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以指定 **包含** 参数应被视为区分大小写的时使用，类似于 UI 中的相关复选框。

*示例 :* `Find *.txt CONTAINING Apple CONTCASE IN C:\Inventory`
</td></tr><tr><td>
CONTIGNOREDIACRITICS</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以指定 **包含** 参数应忽略变音符号（重音符号）时使用，类似于 UI 中的相关复选框。

*示例 :* `Find *.txt CONTAINING "aeiou" CONTIGNOREDIACRITICS IN C:\Documents`
</td></tr><tr><td>
CONTNOPARTIAL</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以防止对 **包含** 参数进行部分单词匹配时使用（然后内容必须与您确切指定的模式相匹配）。

*示例 :* `Find "moo\*cow" IN "c:\ RECURSE CONTNOPARTIAL`
</td></tr><tr><td>
CONTWILD</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件以指定 **包含** 参数应被视为通配符时使用，类似于 UI 中的相关复选框。

*示例 :* `Find *.txt CONTAINING (foo|bar) CONTWILD IN C:\Things`
</td></tr><tr><td>
CONTREGEXP</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件函数时使用，以指定 **包含** 参数应使用 [正则表达式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md)，类似于 UI 中的相关复选框。

*示例 :* `Find *.txt CONTAINING "Mr(s?) Bond" CONTREGEXP IN C:\ RECURSE`
</td></tr><tr><td>
CONTUTF8</td><td>
/S</td><td>

*(无值)*</td><td>

在自动化查找文件功能时，如果未检测到 BOM，则纯文本文件将假定为 UTF-8（类似于 UI 中的相关复选框）。

*示例 :* `Find *.txt CONTAINING printf IN C:\SourceCode CONTUTF8`
</td></tr><tr><td>
DELETE</td><td>
/O</td><td>

*(无值)*</td><td>

使用 **SYNC** 参数自动化同步工具时，这使您可以启用 **删除源代码中不存在的目标文件** 选项。

//<示例：//>有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
</td><td>
</td><td>

**首先**</td><td>

还启用 **复制前删除** 选项。
</td></tr><tr><td>
DSTCOMPENSATION</td><td>
/S</td><td>

*(无值)*</td><td>

在使用 **SYNC** 参数自动化同步工具时，这使您可以选择在比较时间戳时忽略一小时的时间差（夏令时）。

//<示例：//>有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
DUPES</td><td>
/S</td><td>

*(无值)*</td><td>

自动重复文件查找器。

*示例 :* `Find IN C:\Data DUPES`
</td></tr><tr><td>
EXCLUDEHIDDEN</td><td>
/O</td><td>
*(无值)*</td><td>

搜索时排除隐藏文件夹（设置了 **H** 属性的文件夹）。

*示例:* `Find *.txt IN D:\ EXCLUDEHIDDEN`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不排除隐藏文件夹。使用此选项可覆盖已保存的预设值。

*示例:* `Find PRESET=DocFiles EXCLUDEHIDDEN=no IN \\storage\data`
</td></tr><tr><td>
EXCLUDESYSTEM</td><td>
/O</td><td>

*(无值)*</td><td>

搜索时排除系统文件夹（设置了 **H** 和 **S** 属性的文件夹）。

*示例:* `Find *.exe IN C:\ EXCLUDESYSTEM`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不排除系统文件夹。使用此选项可覆盖已保存的预设值。

*示例:* `Find *.exe IN C:\ EXCLUDESYSTEM=no`
</td></tr><tr><td>
FILTER</td><td>
/S</td><td>

*(无值)*</td><td>

表示 **NAME** 参数的值是 [预定义过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md) 的名称。这使你能够自动执行更复杂的搜索，而不仅仅是基于文件名和包含文本的搜索。

*示例:* `Find NAME image_files IN C:\Pictures FILTER`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

允许你以 [文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 定义过滤器。与 **FILTER** 参数类似，你可以自动执行更复杂的搜索，而不仅仅是基于文件名和包含文本的搜索 - 但是不需要预定义过滤器。

这是一个 **/R** 参数，因此 **FILTERDEF** 关键字后面的所有内容都将被视为该参数的值。

*示例:* `Find FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FROM</td><td>
/K</td><td>

*\<path\>*</td><td>

通过 **SYNC** 参数自动执行“同步”工具时，这允许你指定作为同步操作源的文件夹。

//<Example://> 有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

自动执行“查找”工具时，在当前文件夹下执行搜索。

*示例:* `Find NAME *.txt HERE`
</td></tr><tr><td>
HIDEUNAFFECTED</td><td>
/S</td><td>

*(无值)*</td><td>

通过 **SYNC** 参数自动执行“同步”工具时，这使你可以在比较过程运行后选择隐藏未受影响的文件。

//<Example://> 有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
IGNOREDIACRITICS</td><td>
/S</td><td>

*(无值)*</td><td>

自动执行“查找文件”时使用，指定 **NAME** 参数应忽略变音符号（重音符号），与 UI 中相关的复选框类似。

*示例:* `Find (\[aeiou\]+)\\txt IGNOREDIACRITICS REGEXP IN C:\Documents`
</td></tr><tr><td>
IGNORELINKS</td><td>
/S</td><td>

*(无值)*</td><td>

自动执行 [“重复文件查找器”](/Manual/additional_functionality/duplicate_file_finder.zh.md) 时，这允许你打开 **忽略硬链接** 选项。

*示例:* `Find IN C:\Data DUPES IGNORELINKS`
</td></tr><tr><td>
IGNORESECONDS</td><td>
/S</td><td>

*(无值)*</td><td>

通过 **SYNC** 参数自动执行“同步”工具时，这使你可以在比较时间戳时选择忽略秒。

//<Example://> 有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
IN</td><td>
/K/M</td><td>

*\<search location\> ...*</td><td>

自动执行搜索时指定要搜索的文件夹或文件夹。请记住，如果路径包含空格，则必须用引号将值括起来。

*示例:* `Find *.txt IN "C:\Folder 1" "C:\Folder 2"`
</td></tr><tr><td>
LOADPREV</td><td>
/K</td><td>

**no**</td><td>

在“查找”面板打开时禁用加载上一次查找设置。默认情况下，“查找”面板在打开时会记住其上一次设置，除非它是通过自动搜索（即指定了 **IN** 和 **NAME** 参数）调用的。使用此参数防止该命令记住其上一次设置。

*示例:* `Find LOADPREV=no`
</td></tr><tr><td>
</td><td>
</td><td>

**yes**</td><td>

即使通过自动搜索打开，“查找”面板也会加载其上一次设置。但是，这不会恢复多个搜索路径 - 必须为此指定 **LOADPREV=all**。

*示例:* `Find *.txt IN "C:\Folder 1" LOADPREV=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

强制“查找”面板记住其上一次设置，并恢复先前在搜索列表中列出的所有路径。

*示例:* `Find LOADPREV=all`
</td></tr><tr><td>
MD5</td><td>
/O</td><td>

*(无值)*</td><td>

使用 MD5 校验和（与 **DUPES** 参数一起使用）搜索重复项。默认行为是根据文件名和大小进行搜索。

*示例:* `Find IN C:\Data DUPES MD5`
</td></tr><tr><td>
</td><td>
</td><td>

*\<percentage\>*</td><td>

仅根据文件内容的百分比计算校验和。对于大型文件，这可以极大地加快重复检查速度，但会牺牲一些准确性。

*示例:* `Find IN C:\Data DUPES MD5=75`
</td></tr><tr><td>
</td><td>
</td><td>

**cache**</td><td>

对大型文件使用校验和缓存。如果文件的校验和已在先前缓存中，并且文件似乎没有更改，则将使用缓存值而不是重新计算其校验和。

*示例:* `Find IN C:\Downloads DUPES MD5=cache,50`
</td></tr><tr><td>
MINSIZE</td><td>
/K/N</td><td>

*\<size\>*</td><td>

自动执行 [“重复文件查找器”](/Manual/additional_functionality/duplicate_file_finder.zh.md) 时，这允许你设置 **最小大小** 字段的值。以千字节为单位给出该值。

*示例:* `Find IN C:\Data DUPES MD5 MINSIZE=500`
</td></tr><tr><td>
NAME</td><td>
</td><td>

*\<filename\>*</td><td>

这是 **Find** 命令的默认参数，这意味着你无需在之前使用 **NAME** 关键字（除非你在搜索某个单词时被识别为另一个参数关键字）。

指定要搜索的文件名或通配符模式。要自动执行“查找文件”功能，你必须同时指定 **NAME** 参数和使用 **IN** 参数的搜索位置。

**NOWILD**、**ANYWORD** 和 **NOPARTIAL** 参数可用于控制在搜索名称时是否使用通配符，“任意单词”或局部匹配，就像 UI 中的复选框一样。

你可以使用 **regex:** 开头通配符模式，以使用 [正则表达式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md) 代替通配符。（在这种情况下，不要指定 **NOWILD** 参数）。

你还可以通过为 **NAME** 参数提供过滤器名称并指定 **FILTER** 开关，使用预定义过滤器进行搜索。

*示例:* `Find *.(doc|txt|bmp) IN C:\ RECURSE ARCHIVES`
*示例:* `Find regex:foo.+bar\\txt IN C:\ RECURSE`
*示例:* `Find NAME="Text File (1).txt" NOWILD IN C:\ RECURSE`

与 **DUPES** 参数一起使用时，这允许你为重复项搜索提供文件名过滤器。像这样使用时，你可以通过在通配符前面加上 **regex:** 前缀来指定正则表达式模式。
*Example:* `Find *.pdf IN C:\Documents RECURSE CLEAR MD5 DUPES`
</td></tr><tr><td>
NAMEONLY</td><td>
/O</td><td>

*(无值)*</td><td>

仅基于文件名搜索重复项（与 **DUPES** 参数同时使用）。默认行为是基于文件名和大小进行搜索。

*Example:* `Find IN C:\Data DUPES NAMEONLY`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

仅基于文件名搜索重复项，忽略其文件扩展名。

*Example:* `Find IN C:\Data DUPES NAMEONLY=noext`
</td></tr><tr><td>
NOAUTORUN</td><td>
/S</td><td>

*(无值)*</td><td>

可让你防止进行自动搜索 - 相反，“查找”，“重复项”或“同步”面板将打开，控件将初始化，但在开始搜索之前允许你做出进一步的更改。例如，当 **NAME** 和 **IN** 参数同时提供时，查找文件操作通常会自动开始。要防止这种情况的发生，请同时指定 **NOAUTORUN** 参数。

*Example:* `Find *.doc IN /mydocuments RECURSE NOAUTORUN`
</td></tr><tr><td>
NOPARTIAL</td><td>
/S</td><td>

*(无值)*</td><td>

在自动查找文件时使用，以防止部分名称匹配（然后名称必须完全匹配你指定的模式）。

*Example:* `Find *.bak IN "c:\ RECURSE NOPARTIAL`
</td></tr><tr><td>
NOWILD</td><td>
/S</td><td>

*(无值)*</td><td>

在自动查找文件时使用，以防止通配符名称匹配。与 UI 中类似的复选框相同。

*Example:* `Find "File (1).txt" IN "c:\ RECURSE NOWILD`
</td></tr><tr><td>
NUMBERGROUPS</td><td>
/S</td><td>

*(无值)*</td><td>

**重复项查找器**为找到的每组重复文件创建组，而这些组通常以用于重复项搜索的条件命名。如果你打开此选项，则每组重复项将被编号（从 1 到 *X*，按查找顺序）。

*Example:* `Find IN C:\Data DUPES MD5 NUMBERGROUPS`
</td></tr><tr><td>
OF</td><td>
/K/M</td><td>

*\<要匹配的文件\> ...*</td><td>

指定要搜索其重复项的一个或多个文件。如果你不使用此参数，则将查找指定位置中的所有重复项文件。请记住，如果你提供的文件路径包含空格，则必须用引号将值括起来。

*Example:* `Find DUPES OF C:\Report.txt IN C:\Backups MD5`
</td></tr><tr><td>
OFFLINE</td><td>
/S</td><td>

*(无值)*</td><td>

在自动执行 [重复项查找器](/Manual/additional_functionality/duplicate_file_finder.zh.md) 时，此选项可让你关闭 **忽略脱机文件** 选项（此选项的默认值为打开）。

*Example:* `Find IN E:\TapeBackup DUPES OFFLINE`
</td></tr><tr><td>
ONLYEXISTING</td><td>
/S</td><td>

*(无值)*</td><td>

使用 **SYNC** 参数自动执行同步工具时，此选项允许你选择仅同步现有文件。

//<Example://> 有关示例，请参阅 **SYNC** 参数。
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<预设名称\>*</td><td>

加载指定的查找、同步或重复项预设。你提供的其它参数将覆盖预设设置 - 例如，你可以使用 **IN** 参数覆盖搜索路径。指定 **NOAUTORUN** 参数以防止操作自动开始。

*Example:* `Find PRESET=ImageFiles IN=D:\Downloads`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

生成已保存预设列表（用作 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从列表中选择项目将打开相应的面板并运行指定的预设。

*Example:* `Find PRESET=!list DUPES`
</td></tr><tr><td>
</td><td>
</td><td>

**faves**</td><td>

修改生成的预设列表，仅显示你标记为收藏夹的预设。

*Example:* `Find PRESET=!list,faves`
</td></tr><tr><td>
</td><td>
</td><td>

**nofaves**</td><td>

修改生成的预设列表，排除你标记为收藏夹的预设。

*Example:* `Find SYNC PRESET=!list,nofaves`
</td></tr><tr><td>
</td><td>
</td><td>

**nogroups**</td><td>

将生成的预设列表显示为扁平列表，而不是将它们分隔到你可能创建的任何组中。

*Example:* `Find PRESET=!list,nofaves,nogroups`
</td></tr><tr><td>
QUERY</td><td>
/K/R</td><td>

*\<查询字符串\>*</td><td>

使用 [Windows 搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md) 系统在指定的位置执行搜索。

如果单独使用，没有其它参数，它就像在文件窗口的右上角的搜索字段中输入查询字符串以在当前文件夹下进行搜索。你还可以对指定的文件夹或自定义结果集合运行 Windows 搜索查询。

**QUERY** 参数后面的所有内容都将作为查询字符串传递给 Windows 搜索，因此 *必须* 是命令的最后一个参数。

*Example:* `Find QUERY filename:*.doc author:"Leo Davidson"`  
*Example:* `Find IN "C:\Documents" COLLNAME "Leo's Docs" QUERY filename:*.doc author:"Leo Davidson"`
</td></tr><tr><td>
RECURSE</td><td>
/O</td><td>

*(无值)*</td><td>

在自动执行查找文件、重复项查找器或同步文件功能时，搜索将扩展到指定位置下的子文件夹中。

*Example:* `Find IN C:\Data DUPES RECURSE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

防止搜索扩展到子文件夹中。

*Example:* `Find IN C:\Data DUPES RECURSE=no`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(无值)*</td><td>

在自动执行查找文件功能时，为 **NAME** 字段的值启用 [正则表达式](/Manual/file_operations/renaming_files/advanced_rename/rename_modes/regular_expressions.zh.md)。

*Example:* `Find "foo.+bar\\txt" IN C:\ RECURSE REGEXP`
</td></tr><tr><td>
RUNINPANEL</td><td>
/S</td><td>

*(无值)*</td><td>

**查找** 命令的正常自动执行会导致它在后台运行，没有可见的用户界面。**RUNINPANEL** 参数允许你打开重复项查找器或同步面板，使用其它参数对其进行初始化（包括加载预设），然后在用户界面中自动启动操作，与手动单击“Go”按钮完全相同。

将此与 **NOAUTORUN** 进行对比，它将打开面板但不会启动操作。

*Example:* `Find IN C:\Data DUPES RUNINPANEL`
</td></tr><tr><td>
SAVEQUERY</td><td>
/S</td><td>

*(无值)*</td><td>

当你当前正在查看 [Windows 搜索](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md) 查询的结果时，此命令会将搜索保存为 [已储存查询集合](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md)。

*Example:* `Find SAVEQUERY`
</td></tr><tr><td>
SHOWRESULTS</td><td>
/K</td><td>

**source**</td><td>

在当前源文件列表或文件窗口中显示自动搜索的结果。

*Example:* `Find *.txt IN C:\ RECURSE SHOWRESULTS=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

在目标文件列表中显示结果。
<tr><td>
</td><td>
</td><td>

**tab**</td><td>

结果将显示在一个新的标签中。您可以将它与 **source** 或 **dest** 参数组合使用。

*示例：* `Find IN C:\Data DUPES RECURSE SHOWRESULTS dest,tab`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*(无值)*</td><td>

在 [简单模式](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.zh.md) 中显示“查找”面板。

*示例：* `Find SIMPLE`
</td></tr><tr><td>
SIZEONLY</td><td>
/S</td><td>

*(无值)*</td><td>

仅根据文件大小搜索重复文件（与 **DUPES** 参数一起使用）。默认情况下，搜索会同时基于文件名和大小。

*示例：* `Find IN C:\Data DUPES SIZEONLY`
</td></tr><tr><td>
SYNC</td><td>
/O</td><td>

*(无值)*</td><td>

当与其它参数结合在一起时，这可以让你自动化 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 工具。其它相关参数包括 **FROM**, **TO**, **BOTHWAYS**, **DELETE**, **COMPARE**, **IGNORESECONDS**, **DSTCOMPENSATION**, **HIDEUNAFFECTED**, **ONLYEXISTING**。

该过程需要使用多个命令。 `Find SYNC` 在同步过程中执行第一步 - 比较。然后你需要使用 `Copy SYNC` 来执行所需的任何复制操作。最后，在完成后可以使用 `Set CLEARSYNC` 退出同步模式。

//<示例://>

    Find SYNC FROM "D:\Work" TO "D:\Backups" RECURSE COMPARE=newer HIDEUNAFFECTED
    Copy SYNC
    Set CLEARSYNC
</td></tr><tr><td>
</td><td>
</td><td>

**ltr**</td><td>
执行从左到右的同步，而不是从源到目标。
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<path\>*</td><td>

当你使用 **SYNC** 参数自动化同步工具时，这可以让你指定同步操作的目标文件夹。

//<示例://> 有关示例，请参见 **SYNC** 参数。
</td></tr><tr><td>
UAC</td><td>
/O</td><td>

*(无值)*</td><td>

如果搜索文件夹可能需要提升权限，则启用 UAC 提示。

\`\`Find *.txt UAC IN D:\\\`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

忽略 UAC 提示，跳过你无权访问的文件夹。（这是默认值，所以通常无需指定。如果你想覆盖启用了 UAC 提示的预设，这将很有用。）

\`\`Find PRESET=DocFiles UAC=no IN D:\\\`
</td></tr></tbody>
</table>