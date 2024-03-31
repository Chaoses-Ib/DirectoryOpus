# Directory Opus 13 - 详细的发行说明

# 杂项命令

## {代码}

- 现在可以要求 {clip} 代码清理剪贴板文本：
  - {clip|cleanfilename} -- 用作文件名。
  - {clip|cleanfilepath} -- 用作绝对路径。
  - {clip|cleanfilepathrel} -- 用作相对路径。
- 可以要求 {filepath} 和类似代码以 WSL（适用于 Linux 的 Windows 子系统）格式输出路径：
  - 在 WSL 脚本函数按钮中已经自动进行了此操作，但是现在您也可以在普通按钮中请求它。
  - //<示例://> {filepath|wsl}
- {file} 和类似代码现在支持正则表达式来测试和操作插入到命令中的文件名。
  - {file|regex=<pattern>} -- 如果模式不匹配，则跳过文件。
  - {file|regex=<pattern>|to=<new name>} -- 输出正则表达式搜索和替换的结果（如果模式匹配）。
  - {file|regex!=<pattern>|to=<new name>} -- 如上所述，但如果模式不匹配，则输出原始名称不变。
  - 如果模式包含 \| 字符，请用引号将其引起来。
- 可以将求值器代码的结果插入到 {=...=} 之间的命令中。例如，这将变为“Echo 60”：`Echo {=12*5=}`
- 也可以通过在最前面加上 = 字符来让整行由求值器生成。例如，这也会变为“Echo 60”：`=return "Echo " + (12*5);`.

------------------------------------------------------------------------

## @修饰符

- 增加了否定修饰符的正版本：
  - 这些使得直接表达一个肯定条件变得更加容易，而不需要用双重否定的方式来思考。
  - @showif 补充了 @hideif。
  - @enableif、@enableifpath、@enableiftab 补充了 @disableif、@disableifpath、@disableiftab。
  - @ifsel 补充了 @disablenosel。
- @perfile：新修饰符，更改多行命令对多个文件执行的顺序：
  - 影响每次传递一个文件的命令，例如使用 {filepath$}。
  - 通常，在命令中每行都会对所有文件运行，然后再转到下一行。这在某些情况下是有意义的，但在某些情况下是没有意义的。
  - 使用 @perfile，您可以指定一个代码块，其中整个代码块在转到下一个文件之前对每个文件运行。
  - @perfile：begin 标记代码块的开始，@perfile：end 标记结束。
  - 例如，选择两个文件： \<WRAP\>

    文件 Alpha.txt
    文件 Bravo.txt

此命令：

    echo 第一行 -- {file$}
    echo 第二行 -- {file$}

会输出：

    第一行 -- "文件 Alpha.txt"
    第一行 -- "文件 Bravo.txt"
    第二行 -- "文件 Alpha.txt"
    第二行 -- "文件 Bravo.txt"

而这个命令：

    @perfile:begin
    echo 第一行 -- {file$}
    echo 第二行 -- {file$}
    @perfile:end

会输出：

    第一行 -- "文件 Alpha.txt"
    第二行 -- "文件 Alpha.txt"
    第一行 -- "文件 Bravo.txt"
    第二行 -- "文件 Bravo.txt"

\</WRAP\>

- @logusage -- 新修饰符，使用传递给外部程序的任何文件以及程序本身来更新系统最近列表。
  - 为打开方式菜单自动打开了 @logusage。
- @output -- 新修饰符，从一个普通命令中将剩余行输出到脚本日志。
- @if 和类似子句现在可以使用求值器代码来测试各种事情：
  - 使用 = 开始条件以指定它是求值器代码。
  - 变量 selfiles、seldirs、selitems 返回已选择项的数量。
  - 变量 totalfiles、totaldirs、totalitems 返回项的总数。
  - 变量 source 和 dest 返回源路径和目标路径。
  - 变量 source_shell 和 dest_shell 告诉您源或目标是否显示虚拟 Shell 文件夹（例如回收站）。
  - 变量 viewmode 返回当前文件列表模式。
  - 在查看器中，变量 selimage 报告是否选择了部分图像，变量 fullscreen 报告查看器是否为全屏。
  -求值器代码还具有 IsSelected() 函数来测试选择。采用通配符模式，可选择性地添加“files:”或“dirs:”前缀，并返回匹配项的数量。
  - IsChecked() 和 IsEnabled() 也可能很有用。
  - *示例 1：* 仅当选择了正好两个 .jpg 文件时才启用按钮：\<WRAP\>

    @enableif:=IsSelected("*.jpg") == 2

\</WRAP\>

        * //示例 2:// 在全选和全不选中之间切换： <WRAP>

    @if:=(selitems==totalitems)
    选择 无
    @if:else
    选择 全部

\</WRAP\>

      * //示例 3:// 在全选和全不选中之间切换的另一种方法： <WRAP>

    选择 {=selitems==totalitems ? "无" : "全部"=}

\</WRAP\>

- @label -- 新修饰符，使用求值器代码动态更改按钮的标签。
  - 可以使用求值器函数和各种变量，具体取决于上下文。
  - 变量包括“dual”（如果为双栏则为 true）、“source”（源路径）、“dest”（目标路径）、“original_label”（按钮的正常名称，例如，如果要添加到其中而不是完全替换它）。
  - //<示例://> `@label=viewmode=="details" ? "详细模式" : "其他模式"`
  - 按钮工具提示可以动态更改。请参阅查看器工具栏的编辑 \> 复制以获取示例。
- @hideblock -- 新修饰符，允许根据条件隐藏一个或多个工具栏项。
  - 特别是，这允许基于条件隐藏整个子菜单，这在以前是不可能的。
  - 它还可以简化隐藏多个按钮，因为可以在每个按钮中定义一次条件。
  - 在默认工具栏上，如果打开了新的“收藏栏”工具栏，则用它来从“文件列表”工具栏中隐藏冗余的收藏夹菜单。
  - 在（可能）隐藏的收藏夹菜单之前，有一个按钮来运行此命令： \<WRAP\>

    @hideblock:begin
    @hideif:Toolbar 名称="收藏栏" 切换

它测试“收藏栏”工具栏是否打开，如果打开则开始隐藏内容。在其后面是包含收藏夹列表的子菜单。

最后，还有另一个按钮来停止隐藏内容：

    @hideblock:end

如果满足第一个按钮的 @hideif 条件（或未满足 @showif 条件），则介于这两个按钮之间的一切都会被隐藏。 \</WRAP\>

- @disableiftab -- 新修饰符，使用求值器代码来禁用文件夹标签页上下文菜单中的项，该菜单现在可自定义。
  - 变量 sel 给出选定的标签页索引（从 0 开始；如果右键单击标签页栏背景，则为 -1）。
  - 变量 dual 在双栏窗口中为 true。
  - 变量 countdual 给出双栏窗口另一侧的标签页数。
  - 变量 selr 给出选定标签页右侧的标签页数。
  - 示例：
    - @disableiftab:sel == -1 -- 如果没有选择标签页，则禁用。
    - @disableiftab:sel > 1 -- 除非选择了第一个或第二个标签页，否则禁用。
    - @disableiftab:selr == 0 -- 如果选择了最右边的标签页，则禁用。
    - @disableiftab:(sel == -1) || dual -- 如果未选择标签页或在双栏器中，则禁用。
- 增加了 @enableifpath:shell、@disableifpath:shell 等来测试当前文件夹是否是虚拟 Shell 命名空间。
- 默认工具栏使用此按钮在回收站等资源管理器的文件夹中禁用“详细信息 + 缩略图”按钮，因为该功能在那里不起作用。
- 还可以使用求值器与对应的 `source_shell` 和 `dest_shell` 变量。例如：`@disableif:=source_shell`
- `@eval` 和 `@evalalways` -- 运行求值器代码作为动态测试的一部分，还可以选择将其作为命令本身的一部分。
  - 通常用于设置在后面的行中使用的求值器变量。
  - 示例：\<WRAP\>

    @eval:type = PathType(source);
    fIsFileSystem = (type == "shell" || type == "filesys")
    @showif:=fIsFileSystem
    @label:fIsFileSystem ? ("在资源管理器中打开 " + FilePart(DisplayName(source)) + " ") : ("已禁用 (" + type + ")")

\</WRAP\>

      * 只有在动态更新按钮的 label、visibility 和 enabled/disabled 状态时，才运行 `<ib:inline-code><code>@eval:</code></ib:inline-code>` 后面的代码。不会在单击按钮时运行。
      * 在 //两种// 情况下，`<ib:inline-code><code>@evalalways:</code></ib:inline-code>` 后面的代码都会运行，允许您设置在执行命令和更新其标签等时都使用的变量。
      * 求值器代码还可以使用 `<ib:inline-code><code>{=...=}</code></ib:inline-code>` 语法插入到普通命令行的中间。
      * 求值器代码还可以通过以 `<ib:inline-code><code>=</code></ib:inline-code>` 字符开头命令行生成整个命令行。
    * `<ib:inline-code><code>@admin:no</code></ib:inline-code>` -- 防止后续行触发 UAC 提示。`<ib:inline-code><code>@admin:yes</code></ib:inline-code>` 可用于重新启用它们。
    * `<ib:inline-code><code>@ifexists</code></ib:inline-code>` -- 如果路径以 `<ib:inline-code><code>wild:</code></ib:inline-code>` 为前缀，则您可以在最终路径组件中指定通配符。
      * //示例：// `<ib:inline-code><code>@ifexists:wild:C:\Win*</code></ib:inline-code>`
    * `<ib:inline-code><code>@icon</code></ib:inline-code>`：
      * 现在允许引用图标路径，修复了包含逗号的路径的问题。
      * 可以在测试内部命令时运行求值器代码。                        
        * //示例：// `<ib:inline-code><code>@icon:"file.ico",=<eval code></code></ib:inline-code>`
      * 还可以使用求值器直接返回图标路径。                       
        * //示例：// `<ib:inline-code><code>@icon=InStr(source, "production")!=-1 ? "Prod.ico" : "Staging.ico"</code></ib:inline-code>`
    * `<ib:inline-code><code>@ctx</code></ib:inline-code>` -- 新的修饰符，允许求值器代码与生成按钮列表的内部命令一起使用。                 
      * 完整的手册会有更详细的说明，但 `@ctx` 非常深奥。大多数人永远不需要使用或理解它。
      * 它存在的目的是为了使新的“收藏栏”显示收藏树的一个命名分支，其中名称会根据不同的语言/区域设置而改变。

------------------------------------------------------------------------

## 新命令和参数

- 这些只是没有在其他章节中介绍的命令。
- 更改配置设置的命令：
  - `Set DELRECYCLECONFIRM` -- 打开和关闭回收站确认。
  - `Set DELRECYCLEBIN` -- 打开和关闭使用回收站。
  - `Set FRIENDLYDATES` -- 控制是否显示友好的日期（“今天”、“星期一”等）。
  - `Set MINIMIZEPROGRESS=toggle` -- 切换“自动最小化进度指示器”设置。
  - `Set QUICKFILTERFLAGS` -- 更改各种过滤栏选项：
    - 新的“set”和“clear”参数告诉它只设置或清除标志，而不是切换它们。
    - 切换行为已更改，仅影响指定的标志和任何互斥标志。
    - 新的参数用于覆盖平面视图过滤、正则表达式、“忽略变音符号”、“任何单词”和“部分匹配”的配置设置（开或关）。
  - `Set CALCFOLDERSIZES=selected` -- 将“自动计算文件夹大小”设置为“仅选定的文件夹”。
  - 您还可以在条件测试中使用它们，以查看相应选项是否打开。
- `Go BACK` 和 `Go FORWARD` 现在与 NEW、NEWTAB、OPENINDUAL 等参数配合使用，以从当前标签页的历史记录中打开一个文件夹到另一个标签页或窗口中。
- 现在，动态生成按钮列表的命令有一个 HEADING 参数，该参数可以在列表之前添加一个标题。
  - 如果列表为空，则不会添加标题。（这就是它存在的原因，而不是在没有任何列表时添加一个简单的静态标题，因为那样看起来很傻。）
  - “HEADING”本身创建了一个标签，其名称与生成列表的按钮的名称相同（生成列表的按钮）。
  - “HEADING=Xyz”而是使用“Xyz”作为标题。
  - 在新默认工具栏的各个位置使用。
  - //<示例：//> `Go DRIVEBUTTONS=lettersbeforelabels HEADING`
- `Favorites` 和 `Prefs LAYOUTLIST` 命令有新的 `MENUMARKERS` 参数，该参数会导致为生成按钮列表的顶级菜单中的任何菜单显示箭头标志。
- `Favorites EXCLUDEBRANCH` -- 允许通配符在工具栏/菜单上显示它时排除收藏列表的分支，
  - 收藏栏的“其他收藏”菜单使用它来避免显示“收藏栏”分支的第二个副本，该副本显示在工具栏本身上。
- `Favorites BRANCH` -- 根据指定的分支过滤收藏列表。（也可以通过 `PATH` 参数完成，但 `BRANCH` 对于单个分支来说具有更简单的语法。）
- `Favorites AUTOCREATE` -- 如果指定收藏分支不存在，则在工具栏/菜单上显示它时创建该分支。
- `Close SYSTEM` -- 添加了 `sleep` 和 `suspend` 选项。
- `Copy TO` -- 不再自动将使用 `TO` 参数的复制命令排队。
  - 这是因为目标路径不会在命令开始之前求值，届时其队列名称（如果有）必须已知。
  - `QUEUE` 参数仍然可以用来将操作明确地添加到命名队列中。
- `Clipboard COPYIMAGE` -- 将所选图像文件作为位图数据复制到剪贴板，以便粘贴到其他程序中。
- `Clipboard COPYNAMES=noexts` -- 从放置在剪贴板中的名称中删除文件扩展名。
- 添加了 `FILTERDEF` 参数到几个命令中，以便您可以将复杂过滤器的详细信息指定为命令本身的一部分：
  - 基本上来说，任何可以采用命名过滤器的命令现在都可以在命令本身中直接给出过滤器定义，将所有内容保存在一个位置。
  - 这还允许脚本动态修改过滤器详细信息，或在运行时生成整个过滤器。
  - 还允许将求值器代码用于过滤。
  - 在单独的 [Find](find.zh.md) 部分中进行了更多讨论。
  - `Find FILTERDEF` -- 过滤要查找的文件/文件夹。还可以与重复文件查找器和同步工具一起使用，这些工具可以通过 Find 命令运行。
  - `SetAttr FILTERDEF` -- 过滤要更改的文件/文件夹。
  - `Print FOLDER FILTERDEF` -- 过滤要包含的文件/文件夹。
  - `Copy FILTERDEF` -- 过滤要复制/移动的文件/文件夹。
- `Delete FILTERDEF` -- 过滤器，用于删除文件/文件夹。
- 一条命令现在可以在编辑器中拆分到多行，论点在后续行中。
  - 这对于上面提到的 `FILTERDEF` 特别有用。
  - 对于普通“原始”/R 论点也很有用，通常它们会吞下命令行的其他部分（因此无法在同一个命令中使用两个）。
  - 要将论点移到自己单独的一行，语法要求…
    - 所有内容都位于一行中，用 \[\[ 和 \]\] 括起来。
    - 或者：`[[` 和 `]]` 位于不同的行中，其他所有内容位于它们之间。
    - （这类似于单个 `[` 和 `]` 字符之间嵌入命令的现有语法。）
  - 示例：\<WRAP\>

    在 C:\ 中查找
    [[QUERY *.jpg]]
    [[
    FILTERDEF
    根据大小匹配 > 100 kb 和
    根据大小匹配 < 200 kb
    ]]

\</WRAP\>

- `Set FORMATLOCK`:
  - 现在只适用于当前的文件列表，没有任何“左”或“右”参数。从状态栏挂锁/信息图标的右键菜单中添加。
  - 添加了“all”参数以获得旧行为。`Set FORMATLOCK=toggle,all` 会同时切换两侧的状态。
- `Set FLATVIEW=KeepFormat` -- 新的“KeepFormat”参数允许你在触发其特殊文件夹格式的情况下切换平面视图。
  - 类似于完全禁用“平面视图”文件夹格式，但仅适用于特定命令。
  - 如果你通常想在平面视图中添加位置列，但在不使用特定按钮时不想添加，则它非常有用。
  - 如果你想在打开平面视图之前在文件列表中设置列和过滤，以减少开销（计算你不想要的列）和视觉噪音（文件列表中出现的内容会立即删除），它也很有用。
  - 例如，这会切换平面视图，其中所有文件都隐藏，完整路径列可见，并且如果存在的话，位置和相对位置列会被删除：\<WRAP\>

    @if:Set FLATVIEW=Grouped
    Set FLATVIEW=Off,KeepFormat
    Set HIDEFILTERFILENAME
    Set FORMAT=!folder
    @if:else
    Set HIDEFILTERFILENAME=*
    Set COLUMNSREMOVE=path,pathrel
    Set COLUMNSADD=fullpath(1)
    Set FLATVIEW=Grouped,KeepFormat

\</WRAP\>

- `Set NOOP` -- 保证不执行任何操作。可以用来创建一个不执行任何操作的热键，这样键盘按下就不会触发按需查找。
- 日期/时间格式化字符串用于在各种地方，现在可以采用以“A#”开头的字符串，将日期和时间代码组合成一个格式字符串。（而不是需要单独的“D#”和“T#”格式字符串。）
- 用户命令可以使用求值器通过 Arg() 函数测试它们的论点。例如，使用名称/K 的用户命令论点模板：

      @if:=InStr(Arg("NAME"), "jon")
      echo Hi Jon!
      @if:else
      echo Who are you?

- `GetSizes HASH=<type>` -- 替换旧的“GetSizes MD5”和“GetSizes SHA”（它们仍然有效）。
  - 可能的类型关键字有：md5、sha1、sha256、sha512、crc32、crc32_php、crc32_php_rev、blake3。
- `Clipboard COPYNAMES=hash:<type>` -- 替换旧的“Clipboard COPYNAMES=hash”、“hash2”、“hash3”等（它们仍然有效）。
  - 可能的类型关键字与上述 GetSizes 相同。
  - 三种不同的输出格式保持不变，现在可以使用“fmt:X”选择它们。
  - 例如，“Clipboard COPYNAMES=hash:sha1,fmt:2”相当于旧的“Clipboard COPYNAMES=hash5”。
- `Favorites NOLABELS` -- 现在只隐藏顶级标签。子菜单现在总会包含标签。
- `Set EVALUATORDISABLE` -- 可用于阻止所有求值器代码运行（直到重新启用），以进行故障排除。
- `Copy INSTALLFONT=user` -- 为当前用户安装字体，而不是所有用户。
- `Set SIDE=...` -- 可以用在条件语句中，以测试按钮是否位于绑定到左侧（顶部）或右侧（底部）的地址栏工具栏上。
- `Properties POSITION=...` -- 允许你指定属性对话框将在何处打开。

------------------------------------------------------------------------

下一篇：[其他脚本](/Manual/release_history/opus13_detailed/misc_scripting.zh.md)