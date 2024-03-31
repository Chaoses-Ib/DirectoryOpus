# Set
**Set**内部命令可以用来：

- 在当前文件窗口中打开或关闭各种文件窗口元素（[文件夹树](/Manual/basic_concepts/the_lister/navigation/folder_tree.zh.md)、[元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)、[查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)、[双屏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 等）
- 添加或移除当前文件列表中的信息列
- 打开或关闭 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)、[平铺视图模式](/Manual/basic_concepts/flat_view.zh.md) 和 [导航锁定](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.zh.md)
- 更改 [过滤](/Manual/basic_concepts/searching_and_filtering/README.zh.md)、[排序](/Manual/basic_concepts/sorting_and_grouping/README.zh.md)、[分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 和 [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 设置
- 打开或关闭 [管理员模式](/Manual/file_operations/uac_and_administrator_mode.zh.md)
- 启用或禁用复制和删除 [递归过滤器](/Manual/file_operations/filtered_operations/README.zh.md)
- 启用或禁用整行选择和网格线
- 调整当前文件窗口窗口的大小和位置
- ...还有更多 :)

你可以在一个命令行中组合多个 **Set** 命令参数，以一次性对文件窗口进行多处更改。例如，\<nobr\>`Set DUAL=on TREE=off`\</nobr\> 将在一次操作中开启双屏模式，并关闭文件夹树。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>
ADMIN</td><td>
/K</td><td>

**on**</td><td>

在活动文件窗口中启用 [管理员模式](/Manual/file_operations/uac_and_administrator_mode.zh.md)。Opus 将提示你输入超时，之后管理员模式将自动停用。此功能在 Windows XP 中无效，或在 UAC 禁用时无效。

*示例：* `Set ADMIN=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件窗口中关闭管理员模式。

*示例：* `Set ADMIN=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭管理员模式。

*示例：* `Set ADMIN=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

*\<超时\>*</td><td>

指定一个超时（以分钟为单位）来抑制超时对话框的出现。

*示例：* `Set ADMIN=toggle,10`

如果指定 0（零），则超时将被禁用，管理员模式将一直保持在文件窗口中，直到再次按下按钮或关闭窗口。

*示例：* `Set ADMIN=toggle,0`
</td></tr><tr><td>
AUTOSIZE</td><td>
/K</td><td>

**on**</td><td>

打开当前文件列表中的 *自动调整“详细信息”和“功能”模式中的所有列* 文件格式选项。它将覆盖所有列宽，使它们表现为“自动”，直到选项再次关闭为止。请注意，任何已配置的最大列宽仍然适用。

*示例：* `Set AUTOSIZE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 *自动调整“详细信息”和“功能”模式中的所有列* 选项。

*示例：* `Set AUTOSIZE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件列表中打开或关闭 *自动调整“详细信息”和“功能”模式中的所有列* 选项。

*示例：* `Set AUTOSIZE=toggle`
</td></tr><tr><td>
AUTOSIZECOLUMNS</td><td>
/O</td><td>

*(无值)*</td><td>

自动调整源文件列表中的所有列（仅适用于详细信息和功能模式）。这是一个基于当前列内容的一次性宽度更改，而不是像 **AUTOSIZE** 参数所做的那样将列设置为自动调整模式。另一个区别在于，这不会覆盖已设置最大宽度或设置为 *折叠* 等的列。

*示例：* `Set AUTOSIZECOLUMNS`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

自动调整目标文件列表中的所有列。

*示例：* `Set AUTOSIZECOLUMNS=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

调整双屏文件窗口的左（或上）文件列表中的所有列。

*示例：* `Set AUTOSIZECOLUMNS=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

调整双屏文件窗口的右（或下）文件列表中的所有列。

*示例：* `Set AUTOSIZECOLUMNS=right`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

调整双屏文件窗口的两个文件列表（或单屏文件窗口的唯一显示）中的所有列。

*示例：* `Set AUTOSIZECOLUMNS=both`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

调整当前具有输入焦点的文件列表中的所有列。（这几乎总是与源文件列表相同）

*示例：* `Set AUTOSIZECOLUMNS=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**widest**</td><td>

调整双屏文件窗口两侧的列，将两侧的列设置为相同宽度（两者中的最宽）。

*示例：* `Set AUTOSIZECOLUMNS=widest`
</td></tr><tr><td>
BLURFILENAMES</td><td>
/K</td><td>

**on**</td><td>

打开源文件窗口中的文件名模糊处理。你可能希望这样做，以便使用外部屏幕截图工具截取屏幕截图，同时隐藏潜在的敏感信息。

*示例：* `Set BLURFILENAMES=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭源文件窗口中的文件名模糊处理。

*示例：* `Set BLURFILENAMES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭文件名模糊处理。

*示例：* `Set BLURFILENAMES=toggle`
</td></tr><tr><td>
CALCFOLDERSIZES</td><td>
/K</td><td>

**all**</td><td>

打开配置选项以自动计算文件夹大小（适用于所有文件夹）。请注意，这仅仅修改了配置设置——任何当前打开的文件窗口都不会计算其文件夹大小，直到它们被刷新为止。

*示例：* `Set CALCFOLDERSIZES=all`
</td></tr><tr><td>
</td><td>
</td><td>

**local**</td><td>

打开为所有本地驱动器自动计算文件夹大小的选项。

*示例：* `Set CALCFOLDERSIZES=local`
</td></tr><tr><td>
</td><td>
</td><td>

**fixed**</td><td>

为所有固定的本地驱动器打開该选项。

*示例：* `Set CALCFOLDERSIZES=fixed`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭自动计算文件夹大小的选项。

*示例：* `Set CALCFOLDERSIZES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**selected**</td><td>

打开仅在选定文件夹中计算文件夹大小的选项。文件夹列表是通过 [文件夹大小](/Manual/preferences/preferences_categories/folders/folder_sizes/README.zh.md) 配置页面配置的。

*示例：* `Set CALCFOLDERSIZES=selected,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

为指定的文件夹类型打开或关闭计算功能。

*示例：* `Set CALCFOLDERSIZES=local,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**skipjunctions**</td><td>
也指定此标志以启用 *跳过交点和软链接* 选项。

*示例:* `Set CALCFOLDERSIZES=local,toggle,skipjunctions`
</td></tr><tr><td>
CHECKBOXMODE</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中启用 [复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)。

*示例:* `Set CHECKBOXMODE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在源文件列表中关闭复选框模式。

*示例:* `Set CHECKBOXMODE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换复选框模式开关。

*示例:* `Set CHECKBOXMODE=toggle`
</td></tr><tr><td>
CLEARFILTERS</td><td>
/S</td><td>

*(无值)*</td><td>

清除当前源文件列表中的所有文件和文件夹过滤器。清除的过滤器受 **HIDEFILTERFILENAME**, **HIDEFILTERFOLDERS**, **SHOWFILTERFILENAME** 和 **SHOWFILTERFOLDERS** 参数控制。

*示例:* `Set CLEARFILTERS`
</td></tr><tr><td>
CLEARSYNC</td><td>
/S</td><td>

*(无值)*</td><td>

使用 **查找同步** 和 **复制同步** 命令自动化 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 操作后，可以使用 `Set CLEARSYNC` 退出同步模式并使文件窗口恢复正常。

//<Example://> 有关示例，请参阅 `查找同步` [命令](find.zh.md#SYNC)。
</td></tr><tr><td>
COLUMNS</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

更改当前源文件列表中显示的列。可以指定一个或多个使用逗号分隔的 [列关键字](../../metadata_keywords/keywords_for_columns.zh.md) - 列将按照指定的顺序显示。请注意，**名称** 列必须始终存在，如果您未指定它，它将自动添加。

*示例:* `Set COLUMNS name,sizeauto,desc,attr`
</td></tr><tr><td>
</td><td>
</td><td>

*\<format\>*</td><td>

将命名的收藏夹文件夹格式中的列应用于当前源文件列表。格式必须通过 **[文件夹/文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)** 偏好设置页面事先创建。请注意，如果收藏夹格式的名称与实际列的名称冲突，列名称将“获胜”。

*示例:* `Set COLUMNS "Photo Viewing"`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

应用适用于源文件列表路径的文件夹类型格式中的列。例如，如果当前路径是网络驱动器，将应用 **网络驱动器** 格式中的列。

*示例:* `Set COLUMNS=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!factory**</td><td>

将硬编码的出厂默认文件夹格式中的列应用于当前源文件列表。

*示例:* `Set COLUMNS !factory`
</td></tr><tr><td>
</td><td>
</td><td>

**!folder**</td><td>

使用与初始加载文件夹时相同的规则查找并应用列。这通常会为您提供将当前目录加载到新窗口中时可能获得的列。有关 Opus 为路径选择文件夹格式时应用的规则的说明，请参阅 **[文件夹/文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)** 偏好设置页面。

*示例:* `Set COLUMNS !folder`
</td></tr><tr><td>
</td><td>
</td><td>

**!user**</td><td>

将 **用户默认** 文件夹格式中的列应用于当前源文件列表。

*示例:* `Set COLUMNS !user`
</td></tr><tr><td>
COLUMNSADD</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

向当前源文件列表中添加指定列。也可以用于移动或调整现有列的大小。可以指定一个或多个使用逗号分隔的 [列关键字](../../metadata_keywords/keywords_for_columns.zh.md)。

每个列名称可以选择随后是插入列的位置和新列的宽度。格式如下：

<table>
<tbody>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;</em><strong>)</strong></td>
<td>指定列的位置。这可以是一个数字，其中 <strong>0</strong> 表示最左边的列，<strong>1</strong> 表示第二列，以此类推。也可以相对于另一列的当前位置指定 - 更多信息见下文。</td>
</tr>
<tr class="even">
<td><strong>(</strong><em>&lt;pos&gt;</em><strong>,<br />
</strong><em>&lt;size&gt;</em><strong>)</strong></td>
<td>同时指定位置和大小。<em>&lt;size&gt;</em> 参数表示新列的宽度。这可以是像素数、<strong>a</strong> 代表<em>自动</em>、<strong>f</strong> 代表<em>填充</em>、<strong>e</strong> 代表<em>展开</em>和 <strong>c</strong> 代表<em>折叠</em>。</td>
</tr>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;</em><strong>)</strong></td>
<td>指定位置、大小和最大宽度。<em>&lt;max&gt;</em> 参数允许您为自动调整大小的列指定最大宽度。这可以是像素数，也可以是 <strong>f</strong> 代表<em>填充</em>。</td>
</tr>
<tr class="even">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;,<br />
&lt;min&gt;</em><strong>)</strong></td>
<td>指定位置、大小、最大和最小宽度。<em>&lt;min&gt;</em> 参数允许您为自动调整大小的列指定最小宽度。这应为像素数。</td>
</tr>
<tr class="odd">
<td><strong>(</strong><em>&lt;pos&gt;,<br />
&lt;size&gt;,<br />
&lt;max&gt;,<br />
&lt;min&gt;,<br />
</em><strong>z)</strong></td>
<td>指定位置、大小、最大宽度、最小宽度，并在此处冻结列。此列及其之前列保持左对齐且不滚动 - 任何后续列都在冻结列下方滚动。</td>
</tr>
</tbody>
</table>

*\<pos\>* 参数还可以相对于另一列的当前位置指定。例如：

- **0+Name** 将新列放在 *名称* 列所在的位置，将 *名称* 及其之后的所有内容向右移动一个位置。
- **1+Name** 将其直接放在 *名称* 的右侧。
- **2+Name** 将其放在 *名称* 的右侧两个位置。
- **1-Name** 将其放在 *名称* 的左侧两个位置（即位于 *名称* 左侧一列的位置）。还可以将 *\<pos\>* 设置为 **!** 以保持不变，或在前面加上 **!** 以表示如果列已经存在就应该保持不变，但如果将其添加则使用 **!** 后面指定的​​位置。

要指定 *\<pos\>* 以外的任何参数，必须包括它前面的参数。如果不想要为先前的参数之一提供值，请使用 \* 代替。例如，如果您想指定大小 80 但不指定位置，可以使用 **(\*, 80)**。

还可以通过为 *\<pos\>* 指定 **!** 来更改现有列的 *\<size\>*, *\<max\>* 和 *\<min\>* 值。

在 **文件窗口列标题** **[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)** 中，可以使用几个特殊值为位置：
|                    |                                                                                                                                                                                                                            |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **％header%**       | 切换为右键单击的列的 ID。通常用于删除右键单击的列。                                                                                                                                                                                                                          |
| **％headerinsert%** | 切换为距离右键单击位置最近的位置。通常用于在距离右键单击位置最近的位置插入列。如果未指定位置，则列将被添加到现有列的末尾。 |

*示例:* `Set COLUMNSADD picwidth`  
*示例:* `Set COLUMNSADD desc(2),author(\*,\*)`  
*示例:* `Set COLUMNSADD picwidth(\*,a)`  
*示例:* `Set COLUMNSADD=Status(!1+Name)`
</td></tr><tr><td>
COLUMNSFREEZE</td><td>
/K</td><td>

*\<columns\>*</td><td>

设置当前源显示中的冻结列数。冻结列保持左对齐且不滚动 - 任何后续列都会在冻结列下方滚动。

此命令充当一个切换开关 - 如果指定的列数已经冻结，则其将被解冻。

*示例:* `Set COLUMNSFREEZE=3` // - 冻结前三列 //
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前源显示中的冻结列。

*示例:* `Set COLUMNSFREEZE=off`
</td></tr><tr><td>
COLUMNSREMOVE</td><td>
/O</td><td>

*\<column\>, ...*</td><td>

从当前源显示中删除指定的列。你可以指定一个或多个用逗号分隔的[列关键字](../../metadata_keywords/keywords_for_columns.zh.md)。

*示例:* `Set COLUMNSREMOVE=mp3bitrate,mp3samplerate`

在**列表列标题**的**[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)**中，你可以使用**％header%**来引用已右键单击的列。

*示例:* `Set COLUMNSREMOVE=%header%`
</td></tr><tr><td>
COLUMNSTOGGLE</td><td>
/K</td><td>

*\<column\>, ...*</td><td>

在当前源显示中切换指定的列的显示和隐藏。已添加列的位置和大小可以像**COLUMNSADD**一样指定。

你可以指定一个或多个用逗号分隔的[列关键字](../../metadata_keywords/keywords_for_columns.zh.md)。如果提供了多个列名，则仅当**所有**指定的列当前都存在时，才会将命名列关闭。否则，将添加当前不存在的列。

*示例:* `Set COLUMNSTOGGLE=desc(2),author`  
*示例:* `Set COLUMNSTOGGLE=Status(1+Name)`

（有关如何指定位置的详细内容，请参阅上述**COLUMNSADD**参数，如果示例不够清楚。）

仅在**列表列标题**的**[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)**中：

- 对于插入列，你可以使用**％headerinsert%**将这些列插入到你右键单击的位置附近，而不是在末尾。

*示例:* `Set COLUMNSTOGGLE=picwidth(%headerinsert%)`
</td></tr><tr><td>
</td><td>
</td><td>

**any**</td><td>

使命令将类似的列视为在切换方面相同。

例如，有几列以不同的单位显示文件大小。如果*大小（字节）*是唯一正在使用的列大小，并且未使用**any**，则切换*大小（KB）*列的命令将同时显示这两个大小列。在这种情况下，添加**any**会关闭*大小（字节）*列，并且在第一次不会打开任何列。如果再次运行该命令，并且没有大小列，则它将添加*大小（KB）*列。

*示例:* `Set COLUMNSTOGGLE=any,sizekb`
</td></tr><tr><td>
</td><td>
</td><td>

**columnlist**</td><td>

指定**columnlist**关键字可让 Opus 自动生成可切换的列列表。

列表将显示为多个子菜单，其中每个子菜单对应一个列类别（*名称和路径*、*日期和时间*、*图片元数据*等）。这与默认**列表列标题**的**[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)**中的列表类似。

*示例:* `Set COLUMNSTOGGLE=columnlist`

**columnlist**关键字仅受**COLUMNSTOGGLE**参数支持；类似的**COLUMNSADD**和**COLUMNSREMOVE**参数无法使用它，但不太可能需要它。
</td></tr><tr><td>
</td><td>
</td><td>

**insert**</td><td>

**insert**关键字在与**columnlist**关键字结合使用并用于**列表列标题**的**[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)**中时，Opus 会在你右键单击标题之处附近的最近位置插入新列。如果没有它，新列将被添加到末尾。

*示例:* `Set COLUMNSTOGGLE=columnlist,insert`

如果没有**columnlist**关键字或在**列表列标题**菜单外部使用，则**insert**关键字不起作用。要在切换一特定列的命令中进行类似操作，请对上述所述的位置使用**％headerinsert%**。
</td></tr><tr><td>
CONFIRM</td><td>
/S</td><td>

*(无值)*</td><td>

用于显示特定于正在运行的命令的确认消息，通常带有用于使更改永久化的配置设置的链接。只有某些命令才支持此功能，并且通常在你创建自己的按钮时不会使用它。它用在默认的工具栏上，帮助人们了解某些东西仅影响当前的窗口或标签页，以及如何全局进行同样的更改。

*示例:* `Set EXPANDABLEFOLDERS=Toggle CONFIRM`
</td></tr><tr><td>
CONTENTFORMAT</td><td>
/K</td><td>

*\<content group\>*</td><td>

设置当前源文件列表以使用具名[内容类型](/Manual/basic_concepts/folder_options/content_types.zh.md)的文件夹格式。

*示例:* `Set CONTENTFORMAT Images`
</td></tr><tr><td>
COPYFILTER</td><td>
/K</td><td>

**on**</td><td>

为活动列表打开递归[复制过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。

*示例:* `Set COPYFILTER=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭活动列表中的复制过滤器。

*示例:* `Set COPYFILTER=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动列表中切换复制过滤器的显示和关闭。

*示例:* `Set COPYFILTER=toggle`
</td></tr><tr><td>
DARKMODE</td><td>
/K</td><td>

**on**</td><td>

对 Opus 强制使用暗模式，无论当前的 Windows 设置如何。

*示例:* `Set DARKMODE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

对 Opus 强制关闭暗模式，无论当前的 Windows 设置如何。

*示例:* `Set DARKMODE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

如果目前活动的是暗模式，则强制关闭它；否则，强制打开暗模式。
**示例：**`Set DARKMODE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**togglesmart**</td><td>

切换暗模式，如果新模式与 Windows 设置相同，则表现为 **reset**；如果新模式相反，则表现为 **toggle**。

**示例：**`Set DARKMODE=togglesmart`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

在 Opus 中重置暗模式，以使用并跟踪 Windows 设置。

**示例：**`Set DARKMODE=reset`
</td></tr><tr><td>
</td><td>
</td><td>

**noreset**</td><td>

如果 Opus 设置为使用 Windows 设置，则阻止按钮被突出显示为“活动”状态，即使 Windows 设置与命令激活的模式匹配也是如此。

**示例：**`Set DARKMODE=on,noreset`
</td></tr><tr><td>
DELFILTER</td><td>
/K</td><td>

**on**</td><td>

打开活动文件窗口的递归 [删除过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。

**示例：**`Set DELFILTER=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭活动文件窗口中的删除过滤器。

**示例：**`Set DELFILTER=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动文件窗口中打开或关闭删除过滤器。

**示例：**`Set DELFILTER=toggle`
</td></tr><tr><td>
DELRECYCLEBIN</td><td>
/K</td><td>

**on**</td><td>

打开 [删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md) 偏好设置页上的 *尽可能删除到回收站* 选项。

**示例：**`Set DELRECYCLEBIN=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 *尽可能删除到回收站* 选项。

**示例：**`Set DELRECYCLEBIN=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭 *尽可能删除到回收站* 选项。

**示例：**`Set DELRECYCLEBIN=toggle`
</td></tr><tr><td>
DELRECYCLECONFIRM</td><td>
/K</td><td>

**on**</td><td>

打开配置中 [删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md) 页面上的 *删除到回收站时跳过确认* 选项。

**示例：**`Set DELRECYCLECONFIRM=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 *删除到回收站时跳过确认* 选项。

**示例：**`Set DELRECYCLECONFIRM=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭 *删除到回收站时跳过确认* 选项。

**示例：**`Set DELRECYCLECONFIRM=toggle`
</td></tr><tr><td>
DEST</td><td>
/K</td><td>

**left**</td><td>

将双栏器文件窗口中的左（或顶部）文件列表设置为主位置。

**示例：**`Set DEST=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

将右（或底部）文件列表设置为主位置。

**示例：**`Set DEST=right`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

将当前有输入焦点的文件列表设置为主位置。

**示例：**`Set DEST=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换左右文件列表的状态（源/主位置）。

**示例：**`Set DEST=toggle`
</td></tr><tr><td>
DISABLEGLOBALHOTKEYS</td><td>
/K</td><td>

**on**</td><td>

暂时禁用所有全局热键。适用于文件窗口的本地热键将继续发挥作用。

**示例：**`Set DISABLEGLOBALHOTKEYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

重新启用所有全局热键。

**示例：**`Set DISABLEGLOBALHOTKEYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭所有全局热键。

**示例：**`Set DISABLEGLOBALHOTKEYS=toggle`
</td></tr><tr><td>
DUAL</td><td>
/K</td><td>

**on**</td><td>

打开活动文件窗口中的 [双栏器](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式。

**示例：**`Set DUAL=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭活动文件窗口中的双栏器模式。

**示例：**`Set DUAL=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动文件窗口中打开或关闭双栏器模式。

**示例：**`Set DUAL=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

将双栏器模式设置为使用横向布局（一个文件列表在另一个上方）。此值本身将打开双栏器模式，但你可以将其与 **toggle** 结合使用，以打开或关闭横向双栏器。如果双栏器模式已经打开，但布局设置为垂直，则布局将更改为水平。

**示例：**`Set DUAL=horiz,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

将双栏器模式设置为使用垂直布局（一个文件列表在另一个旁边）。

**示例：**`Set DUAL=vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

在横向和垂直之间切换双栏器模式的布局。如果双栏器模式当前未处于活动状态，则此命令不会产生任何效果，除非还提供了 **toggle** 关键字和 **horiz** 关键字或 **vert** 关键字。

如果与其他关键字结合，则在以下情况下该功能将打开双栏器模式：尚未打开该模式；双栏器模式已经打开，但未处于预期方向，则切换布局（从横向到纵向或反之） ；如果双栏器模式已打开且已经处于预期方向，则关闭该模式。

**示例：**`Set DUAL=togglelayout`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

在打开双栏器模式后，新打开的文件列表将变为主位置。此值必须与实际导致双栏器模式打开的其他值之一组合使用。

**示例：**`Set DUAL=toggle,source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

在打开双栏器模式后，新打开的文件列表将变为主位置。

**示例：**`Set DUAL=toggle,dest`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

当双栏器模式关闭时，将关闭右（或底部）文件列表。

**示例：**`Set DUAL=off,right`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

当双栏器模式关闭时，将关闭左（或顶部）文件列表。

**示例：**`Set DUAL=toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**remember**</td><td>

将此值与 **toggle** 关键字结合使用，以在关闭然后重新打开第二个文件列表时，使其记住其路径。如果没有指定此项，则新打开的文件列表的路径将由配置中 **[文件列表/选项](/Manual/preferences/preferences_categories/file_displays/options/README.zh.md)** 页面上的 **切换到双栏时指定初始文件夹** 选项控制。

**示例：**`Set DUAL=toggle,horiz,remember`
</td></tr><tr><td>
DUALSIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*</td><td>

调整活动文件窗口中双栏之间的分隔符。如果垂直排列显示，则命令将影响其宽度；如果水平排列，则将影响其高度。

大小以百分比表示，指定第一个文件列表应使用多少可用空间，第二个文件列表获得剩余空间。
例如，指定 50 使两个文件列表相同大小（与双击它们之间的分隔符相同）：

*示例：* `Set DUALSIZE 50`

另一个示例，指定 75 使第一个文件列表使用 75% 的空间，为第二个文件留出 25% 的空间：

*示例：* `Set DUALSIZE 75`

也可以指定两个大小，使命令在它们之间切换。这允许创建按钮或热键，快速切换以向一个显示提供大部分空间并使其再次相等。

*示例：* `Set DUALSIZE 75,50`

还可以通过指定正或负增量按相对量调整分隔符的大小。

*示例：* `Set DUALSIZE +10`
</td></tr><tr><td>
ENABLELABELFILTER</td><td>
/K</td><td>

*\<name\>*</td><td>

此命令允许启用或禁用命名的 [通配符标签和标签过滤器](/Manual/file_operations/labels.zh.md)。在可以通过此命令对其进行控制之前，必须已将指定名称分配给过滤器。支持全局和基于文件夹格式的标签过滤器。可以指定 **local:*\<name\>*** 和 **global:*\<name\>*** 来限制要控制的过滤器类型，或者只提供名称，Opus 将在两种类型的过滤器中查找它。

*示例：* `Set ENABLELABELFILTER my_filter,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**on**</td><td>

启用指定的标签过滤器。

*示例：* `Set ENABLELABELFILTER my_filter,on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

禁用指定的标签过滤器。

*示例：* `Set ENABLELABELFILTER my_filter,off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

启用或禁用指定的标签过滤器。

*示例：* `Set ENABLELABELFILTER my_filter,toggle`
</td></tr><tr><td>
EVALUATORDISABLE</td><td>
/O</td><td>

**on**</td><td>

禁用 [求值器](/Manual/evaluator/README.zh.md)。如果你已经在试验求值器，并且发现它导致的一些问题需要解决才能重新启用求值器，那么可能需要这样做。求值器将保持禁用状态，直到重新启用它（或重新启动 Opus）。

*示例：* `Set EVALUATORDISABLE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>
重新启用求值器。
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>
启用和禁用求值器。
</td></tr><tr><td>
EXPANDABLEFOLDERS</td><td>
/O</td><td>

**on**</td><td>

在当前的文件管理器中启用 [展开式文件夹](/Manual/basic_concepts/expandable_folders.zh.md)。在此模式下，文件夹可以直接在文件列表中展开，就像在文件夹树中一样。此命令允许覆盖 [文件夹展开](/Manual/preferences/preferences_categories/file_displays/folder_expansion.zh.md) 配置页面上的默认设置。

*示例：* `Set EXPANDABLEFOLDERS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在当前的文件管理器中禁用展开式文件夹。

*示例：* `Set EXPANDABLEFOLDERS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前的文件管理器中启用和禁用展开式文件夹。

*示例：* `Set EXPANDABLEFOLDERS=toggle`
</td></tr><tr><td>
FDBTOOLBAR</td><td>
/O</td><td>

*\<name\>*</td><td>

此命令允许更改用于 [文件列表](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 的工具栏。如果不指定名称，则选择默认文件列表工具栏。

可以通过逗号分隔来指定多个工具栏。

*示例：* `Set FDBTOOLBAR "My FDB Toolbar"`  
*示例：* `Set FDBTOOLBAR "File Display,Images"`
</td></tr><tr><td>
</td><td>
</td><td>

**!static**</td><td>

完全关闭 FDB 工具栏（还原为静态标题栏）。

*示例：* `Set FDBTOOLBAR !static`
</td></tr><tr><td>
FILTERS</td><td>
/K</td><td>

**on**</td><td>

为活动的文件管理器启用复制和删除 [递归过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。

*示例：* `Set FILTERS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动的文件管理器中禁用两个递归过滤器。

*示例：* `Set FILTERS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动的文件管理器中启用或禁用两个递归过滤器。

*示例：* `Set FILTERS=toggle`
</td></tr><tr><td>
FLATVIEW</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中启用 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 模式。

*示例：* `Set FLATVIEW=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在源文件列表中禁用平面视图模式。

*示例：* `Set FLATVIEW=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前源文件列表中启用或禁用平面视图。如果与一个模式关键字（**group**、**mixed**、**mixednofolders**）结合使用，平面视图仅在当前处于指定模式下时才会被关闭 - 否则，它将被设置为该模式（并在需要时被启用）。

*示例：* `Set FLATVIEW=toggle,grouped`
</td></tr><tr><td>
</td><td>
</td><td>

**toggleoff**</td><td>

启用或禁用平面视图。与 **toggle** 不同，如果平面视图在 *任何* 模式下当前已启用，则将关闭平面视图，即使该模式与指定的关键字不匹配。

*示例：* `Set FLATVIEW=mixednofolders,toggleoff`
</td></tr><tr><td>
</td><td>
</td><td>

**grouped**</td><td>

将平面视图设置为 *分组* 模式。

*示例：* `Set FLATVIEW=grouped`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

将平面视图设置为 *混合* 模式。

*示例：* `Set FLATVIEW=toggle,mixed`
</td></tr><tr><td>
</td><td>
</td><td>

**mixednofolders**</td><td>

将平面视图设置为 *混合（无文件夹）* 模式。

*示例：* `Set FLATVIEW=mixednofolders,on`
</td></tr><tr><td>
</td><td>
</td><td>

**keepformat**</td><td>

允许在不更改当前文件夹格式的情况下切换平面视图。（类似于在配置中禁用平面视图格式，但仅用于当前更改。）如果通常希望添加位置列，但在使用特定按钮时不希望，则此操作非常有用。如果希望在打开平面视图之前在文件列表中设置列和过滤器以减少开销（计算不需要的列）和视觉噪音（在文件列表中出现的只立即被移除的东西），则此操作也可能很有用。

例如，这将切换平面视图，隐藏所有文件，并显示完整路径列（如果显示位置和相对位置列，则会将其移除）：

    @if:Set FLATVIEW=grouped
    Set FLATVIEW=off,keepformat
    Set HIDEFILTERFILENAME
    Set FORMAT=!folder
    @if:else
    Set HIDEFILTERFILENAME=*
    Set COLUMNSREMOVE=path,pathrel
    Set COLUMNSADD=fullpath(1)
    Set FLATVIEW=grouped,keepformat
</td></tr><tr><td>
FOCUS</td><td>
/K</td><td>

**left**</td><td>

将输入焦点设置为双栏文件管理器中的左侧文件列表。

*示例：* `Set FOCUS=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

将输入焦点设置为双栏文件管理器中的右侧文件列表。

*示例：* `Set FOCUS=right`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

将输入焦点设置为当前源文件列表。
*示例:* `Set FOCUS=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

将输入焦点设置为目标文件列表。

*示例:* `Set FOCUS=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**tree**</td><td>

将输入焦点设置为文件夹树。在带双树的双栏文件窗口中，焦点将转到附加到源文件列表的树上。

*示例:* `Set FOCUS=tree`
</td></tr><tr><td>
</td><td>
</td><td>

**lefttree**</td><td>

在双栏、双树文件窗口中将输入焦点设置到左手侧文件夹树。

*示例:* `Set FOCUS=lefttree`
</td></tr><tr><td>
</td><td>
</td><td>

**righttree**</td><td>

在双栏文件窗口中将输入焦点设置到右手侧文件夹树。

*示例:* `Set FOCUS=righttree`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在左手和右手文件列表之间切换输入焦点。

*示例:* `Set FOCUS=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**pathfield**</td><td>

将焦点设置到源面包屑路径字段。

*示例:* `Set FOCUS=pathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**leftpathfield**</td><td>

在双栏文件窗口中将焦点设置到左/上路径字段。

*示例:* `Set FOCUS=leftpathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**rightpathfield**</td><td>

在双栏文件窗口中将焦点设置到右/下路径字段。

*示例:* `Set FOCUS=rightpathfield`
</td></tr><tr><td>
</td><td>
</td><td>

**filedisplay**</td><td>

使用 [@if:set](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md) 来测试哪个控件具有焦点时，你可以使用此选项指代“任何文件列表”，而不是不得不指定源/目标等。

*示例:* `@if:set FOCUS=filedisplay`
</td></tr><tr><td>
</td><td>
</td><td>

**metapane**</td><td>

将焦点赋予 [元数据窗格](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)。

*示例:* `Set FOCUS=metapane`
</td></tr><tr><td>
</td><td>
</td><td>

**viewpane**</td><td>

将焦点设置到 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)。

*示例:* `Set FOCUS=viewpane`
</td></tr><tr><td>
FOLDERTREESIZE</td><td>
/K</td><td>

*\<size\>\[,\<size\>\]*\[,**left**\|**right**\|**dest**\]</td><td>

调整活动文件窗口中文件夹树窗格的大小。大小以像素为单位的绝对宽度表示。可以指定两个单独的大小，并且使用此命令可以在它们之间切换。你还可以让命令操作除当前源文件列表所附加文件树外的文件夹树，方法是附加 **left**、**right** 或 **dest** 关键字。

*示例:* `Set FOLDERTREESIZE 200,300`
</td></tr><tr><td>
FONTSCALE</td><td>
/K</td><td>

*\<绝对比例因子\>*</td><td>

将文件列表中的字体缩放设置为指定比例因子。**100**（表示 100%）是基准级别，在配置中的 **[字体](/Manual/preferences/preferences_categories/colors_and_fonts/fonts.zh.md)** 页面上代表配置的实际点数。**200** 表示为其两倍大，**50** 表示为其一半大，依此类推。

请注意，字体缩放只适用于详细信息、强大功能和缩略图 [视图](/Manual/basic_concepts/the_lister/view_modes.zh.md)。详细信息/强大功能模式和缩略图模式有单独的缩放设置 - 默认情况下，此命令会调整当前模式的设置，但是你可以使用可选的关键字来指定受影响的模式。

*示例:* `Set FONTSCALE=125`
</td></tr><tr><td>
</td><td>
</td><td>

*\<相对比例因子\>*</td><td>

通过指定的增量调整文件列表中的字体缩放比例。使用正值来增加缩放比例，使用负值来减少缩放比例。

*示例:* `Set FONTSCALE=-10`
</td></tr><tr><td>
</td><td>
</td><td>

*\<比例因子1\>,\<比例因子2\>*</td><td>

指定两个绝对缩放比例因子来创建一个可在两者之间切换的命令。

*示例:* `Set FONTSCALE=100,150`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

缩放左侧文件列表中的字体，无论其是否是源文件。

*示例:* `Set FONTSCALE=50,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

缩放右侧文件列表中的字体。

*示例:* `Set FONTSCALE=right,-25`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

缩放目标文件列表中的字体。

*示例:* `Set FONTSCALE=dest,+50`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

缩放左右文件列表中的字体。

*示例:* `Set FONTSCALE=50,125,both`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

仅调整详细信息和强大功能模式中的字体。

*示例:* `Set FONTSCALE=150,details`
</td></tr><tr><td>
</td><td>
</td><td>

**thumbnails**</td><td>

仅调整缩略图模式中的字体。

*示例:* `Set FONTSCALE=+50,thumbnails`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

为详细信息/强大功能模式和缩略图模式同时调整字体。

*示例:* `Set FONTSCALE=+50,thumbnails`
</td></tr><tr><td>
FORMAT</td><td>
/K</td><td>

*\<格式\>*</td><td>

将命名的收藏夹文件夹格式应用于当前源文件列表。必须通过 **[文件夹/文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)** 配置页面创建过该格式。

*示例:* `Set FORMAT "Photo Viewing"`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

应用适用于源文件列表路径的文件夹类型格式。例如，如果当前路径是网络驱动器，则会应用 **网络驱动器** 格式。

*示例:* `Set FORMAT=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!factory**</td><td>

将硬编码的出厂默认文件夹格式应用于当前源文件列表。

*示例:* `Set FORMAT !factory`
</td></tr><tr><td>
</td><td>
</td><td>

**!folder**</td><td>

通过使用与初始加载文件夹时相同的规则，查找并应用文件夹格式。这通常会给你你在新窗口打开当前文件夹时所获得的格式。请参阅 **[文件夹/文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)** 配置页面，以获取 Opus 为路径选择文件夹格式时所应用的规则说明。

*示例:* `Set FORMAT !folder`
</td></tr><tr><td>
</td><td>
</td><td>

**!user**</td><td>

将 **用户默认** 文件夹格式应用于当前源文件列表。

*示例:* `Set FORMAT !user`
</td></tr><tr><td>
FORMATLIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示收藏夹和内容类型文件夹格式的生成列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。这为 **[文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md)**配置页面上收藏夹格式类别中保存的每种格式显示一个项目。从生成列表中选择格式会将它的设置应用于当前文件列表。

*示例:* `Set FORMATLIST`
</td></tr><tr><td>
</td><td>
**contenttype**</td><td>

仅显示内容类型格式（忽略收藏夹内容的格式）。

*示例：* `Set FORMATLIST=contenttype`
</td></tr><tr><td>
</td><td>
</td><td>

**favorites**</td><td>

仅显示收藏夹格式（忽略内容类型的格式）。

*示例：* `Set FORMATLIST=favorites`
</td></tr><tr><td>
</td><td>
</td><td>

**icons**</td><td>

向命令生成的列表项分配图标。创建列表的按钮也必须启用其图标才能显示图标。

*示例：* `Set FORMATLIST=icons,favorites`
</td></tr><tr><td>
</td><td>
</td><td>

**noreset**</td><td>

防止在格式列表的末尾添加通常生成的“重置”命令（例如，重置为默认设置）。

*示例：* `Set FORMATLIST=favorites,noreset`
</td></tr><tr><td>
FORMATLOCK</td><td>
/K</td><td>

**on**</td><td>

在当前文件窗口中启用[格式锁定](/Manual/basic_concepts/folder_options/locking_the_format.zh.md)。默认情况下，它适用于活动文件列表（具有焦点的那个），但你可以将其与其他参数结合使用以控制哪些文件列表受到影响。

*示例：* `Set FORMATLOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件列表中关闭格式锁定。

*示例：* `Set FORMATLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件窗口中切换格式锁定开或关。此命令可以替换默认状态栏中的挂锁图标。如果在双栏文件窗口中与 **all** 关键字结合使用，则如果两个显示器中有一个或没有启用的话，此操作将在两个文件列表中启用格式锁定。只有当两个显示器都已启用时，锁定才会关闭。

*示例：* `Set FORMATLOCK=toggle,all`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

仅将格式锁定应用于双栏文件窗口中的左侧（或顶部）文件列表。

*示例：* `Set FORMATLOCK=toggle,left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

仅将格式锁定应用于右侧（或底部）文件列表。

*示例：* `Set FORMATLOCK=toggle,right`
</td></tr><tr><td>
</td><td>
</td><td>

**source**</td><td>

仅将格式锁定应用于双栏文件窗口中的源文件列表。

*示例：* `Set FORMATLOCK=toggle,source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

仅将格式锁定应用于目标文件列表。

*示例：* `Set FORMATLOCK=toggle,dest`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

将格式锁定应用于双栏文件窗口中的两个文件列表（或否则就是一个显示）。

*示例：* `Set FORMATLOCK=off,all`
</td></tr><tr><td>
FRIENDLYDATES</td><td>
/K</td><td>

**normal**</td><td>

启用“友好的日期”，其中日期列将今天的日期显示为“今天”，昨天的日期显示为“昨天”，最近七天的日期显示为星期几名称（“星期一”等）。

*示例：* `Set FRIENDLYDATES=normal`
</td></tr><tr><td>
</td><td>
</td><td>

**today**</td><td>

启用“友好的日期”，但仅适用于“今天”。

*示例：* `Set FRIENDLYDATES=today`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

禁用“友好的日期”。所有日期都将显示为日期、月份和年份（根据日期格式设置）。

*示例：* `Set FRIENDLYDATES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggles**</td><td>

切换“友好的日期”开或关。可以与 **normal** 或 **today** 结合使用，以在启用友好的日期时指定模式；否则，将使用之前配置的模式。

*示例：* `Set FRIENDLYDATES=toggle`  
*示例：* `Set FRIENDLYDATES=toggle,normal`
</td></tr><tr><td>
FTPMODE</td><td>
/K</td><td>

**ascii**</td><td>

将当前 FTP 连接的文件传输模式设置为 ASCII。如果源文件列表当前未查看远程 FTP 站点，此命令不起作用。

*示例：* `Set FTPMODE=ascii`
</td></tr><tr><td>
</td><td>
</td><td>

**binary**</td><td>

将当前 FTP 连接的传输模式设置为二进制。

*示例：* `Set FTPMODE=binary`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

根据传输的文件类型自动选择传输模式。

*示例：* `Set FTPMODE=auto`
</td></tr><tr><td>
FULLROWSELECT</td><td>
/K</td><td>

**on**</td><td>

启用整行选择。Preferences 中的 Power（**[文件列表模式/增强模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)**）和 details（**[文件列表模式/详细信息](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)**）[视图](/Manual/basic_concepts/the_lister/view_modes.zh.md）中都有单独的整行设置，默认情况下此命令将影响源文件列表中当前视图的设置。你可以使用此参数的其他关键字来控制受影响的视图。

*示例：* `Set FULLROWSELECT=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

禁用整行选择。

*示例：* `Set FULLROWSELECT=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换整行选择开或关。

*示例：* `Set FULLROWSELECT=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**power**</td><td>

仅影响增强模式的设置，而不考虑当前的视图。

*示例：* `Set FULLROWSELECT=toggle,power`
</td></tr><tr><td>
</td><td>
</td><td>

**details**</td><td>

仅影响详细信息模式的设置。

*示例：* `Set FULLROWSELECT=on,details`
</td></tr><tr><td>
</td><td>
</td><td>

**namecol**</td><td>

当关闭整行选择时，将使用“名称列全宽”模式，而不是“仅文件名”模式。如果整行选择处于打开状态，则没有效果。

*示例：* `Set FULLROWSELECT=off,namecol`
</td></tr><tr><td>
GLOBALHIDEFILENAME</td><td>
/O</td><td>

*（无值）*</td><td>

清除 **全局隐藏过滤器** 文件名过滤器（Preferences 中 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页）。

*示例：* `Set GLOBALHIDEFILENAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

将 **全局隐藏过滤器** 文件名过滤器设置为指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。

提供的模式可以前缀 **regex:** 以指定模式是正则表达式。

如果过滤器已设置为指定模式，它将被清除，这使命令自动起作用。

*示例：* `Set GLOBALHIDEFILENAME "(desktop.ini\|\*.db)"`  
*示例：* `Set GLOBALHIDEFILENAME regex:.db\$`
</td></tr><tr><td>
GLOBALHIDEFILTER</td><td>
/K</td><td>

**on**</td><td>

启用 **启用全局通配符过滤器** 选项（Preferences 中 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页）。

*示例：* `Set GLOBALHIDEFILTER on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 **启用全局通配符过滤器** 选项。

*示例：* `Set GLOBALHIDEFILTER off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换 **启用全局通配符过滤器** 选项开或关。
*示例：* `Set GLOBALHIDEFILTER=toggle`
</td></tr><tr><td>
GLOBALHIDEFOLDERS</td><td>
/O</td><td>

*(无值)*</td><td>

清除 **全局隐藏过滤器** 文件夹过滤器（在配置的 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上）。

*示例：* `Set GLOBALHIDEFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<模式\>*</td><td>

将 **全局隐藏过滤器** 文件夹过滤器设为指定的 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。

提供的模式可以使用 **regex:** 作为前缀，以指定模式为正则表达式。

如果过滤器已设为指定模式，它将被清除，使命令自动作为切换。

*示例：* `Set GLOBALHIDEFOLDERS .svn`
</td></tr><tr><td>
GLOBALHIDEHIDDEN</td><td>
/K</td><td>

**on**</td><td>

启用全局 **隐藏隐藏文件** 选项（在配置的 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上）。

*示例：* `Set GLOBALHIDEHIDDEN on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

禁用全局 **隐藏隐藏文件** 选项。

*示例：* `Set GLOBALHIDEHIDDEN off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换全局 **隐藏隐藏文件** 选项。

*示例：* `Set GLOBALHIDEHIDDEN=toggle`
</td></tr><tr><td>
GRIDLINESH</td><td>
/K</td><td>

**on**</td><td>

在当前文件列表中启用水平网格线（仅在 power 或 details [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 中可见）。此命令将覆盖配置中的设置（在 **[文件列表模式 /增强模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)** 页或 **[文件列表模式 / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)** 页上），但更改只适用于当前源文件列表 - 全局配置设置不会被修改。

*示例：* `Set GRIDLINESH on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在当前文件列表中禁用水平网格线。

*示例：* `Set GRIDLINESH off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换当前文件列表中水平网格线。如果还给出了 **reset** 关键词，则该命令将在命令行中指定的网格线和当前配置设置之间切换。

*示例：* `Set GRIDLINESH=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

将当前文件列表中的水平网格线设置重置为在配置中定义的设置。您可以将其与 **toggle** 关键词结合使用，在配置设置和另一组自定义设置之间切换。

*示例：* `Set GRIDLINESH=reset,toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

*\<样式\>*</td><td>

将水平网格线设为使用指定的样式。结合使用此关键词和 **on**、**off** 或 **toggle** 关键词，以控制命令显示哪个样式。

支持的样式有 **solid**、**alternate**、**dot**、**dash**、**dashdot**、**dashdotdot** 和 **fill**。注意，**solid** 表示实线的不间断单像素线，而 **fill** 表示交替的行（即，粗线，填充每隔一行背景）。

*示例：* `Set GRIDLINESH=toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<颜色\>*</td><td>

设置水平网格线的颜色。*\<颜色\>* 可以用十进制格式（**rrr,ggg,bbb**）或十六进制格式（**\#rrggbb**）指定。由于 **color=** 关键词包含等号，您必须将 **GRIDLINES** 参数的整个值用引号括起来，以避免给命令解析器造成混淆。

*示例：* `Set GRIDLINESH "toggle,fill,color=#ff8000"`
</td></tr><tr><td>
</td><td>
</td><td>

**opacity=***\<opacity\>*</td><td>

设置水平网格线的透明度。*\<opacity\>* 必须是从 **1**（几乎透明）到 **100**（实心）的值。由于 **opacity=** 关键词包含等号，您必须将 **GRIDLINES** 参数的整个值用引号括起来，以避免给命令解析器造成混淆。

*示例：* `Set GRIDLINESH "toggle,solid,color=#808080,opacity=50"`
</td></tr><tr><td>
GRIDLINESV</td><td>
/K</td><td>

**on**</td><td>

在当前文件列表中启用垂直网格线（仅在 power 或 details [视图模式](/Manual/basic_concepts/the_lister/view_modes.zh.md) 中可见）。此命令将覆盖配置中的设置（在 **[文件列表模式 /增强模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)** 页或 **[文件列表模式 / Details](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)** 页上），但更改只适用于当前源文件列表 - 全局配置设置不会被修改。

*示例：* `Set GRIDLINESV on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在当前文件列表中禁用垂直网格线。

*示例：* `Set GRIDLINESV off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换当前文件列表中垂直网格线。如果还给出了 **reset** 关键词，则该命令将在命令行中指定的网格线和当前配置设置之间切换。

*示例：* `Set GRIDLINESV=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

将当前文件列表中的垂直网格线设置重置为在配置中定义的设置。您可以将其与 **toggle** 关键词结合使用，在配置设置和另一组自定义设置之间切换。

*示例：* `Set GRIDLINESV=reset,toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

*\<样式\>*</td><td>

将垂直网格线设为使用指定的样式。结合使用此关键词和 **on**、**off** 或 **toggle** 关键词，以控制命令显示哪个样式。

支持的样式有 **solid**、**alternate**、**dot**、**dash**、**dashdot** 和 **dashdotdot**。

*示例：* `Set GRIDLINESV=toggle,solid`
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<颜色\>*</td><td>

设置垂直网格线的颜色。*\<颜色\>* 可以用十进制格式（**rrr,ggg,bbb**）或十六进制格式（**\#rrggbb**）指定。由于 **color=** 关键词包含等号，您必须将 **GRIDLINES** 参数的整个值用引号括起来，以避免给命令解析器造成混淆。

*示例：* `Set GRIDLINESV "toggle,fill,color=#ff8000"`
</td></tr><tr><td>
</td><td>
</td><td>

**opacity=***\<opacity\>*</td><td>

设置垂直网格线的透明度。*\<opacity\>* 必须是从 **1**（几乎透明）到 **100**（实心）的值。由于 **opacity=** 关键词包含等号，您必须将 **GRIDLINES** 参数的整个值用引号括起来，以避免给命令解析器造成混淆。

*示例：* `Set GRIDLINESV "toggle,solid,color=#808080,opacity=50"`
</td></tr><tr><td>
GROUPBY</td><td>
/K</td><td>

*\<column\>*</td><td>

[组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 当前文件按指定列显示。该值必须是有效的其中之一[列关键字](../../metadata_keywords/keywords_for_columns.zh.md)。

除了列关键字，**GROUPBY** 认可特殊关键字同义词 **accessed**, **created**, **date, disksize, modified, path** 和 **size**。这使您能够按日期、大小或路径分组，无需了解显示的确切列（例如，该列可以是 **size**, **sizekb** 或 **sizerel** - 但在所有情况下排序都是相同的，而且 `Set GROUPBY=size` 对任何列有效）。

如果您对指定列有任何[求值器分组方案](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.zh.md) 已定义，则可以使用 **GROUPSCHEME** 参数选择一个。

**GROUPBY** 参数还认可特殊关键字 **dupes** 和 **cdstage**。这些不与列对应，并且只在某些文件夹中有效。

`Set GROUPBY=dupes` 只能在已被用作[重复文件](/Manual/additional_functionality/duplicate_file_finder.zh.md) 搜索的目标的[文件Set](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中使用（按搜索中找到的重复文件组对列表进行分组），并且 `Set GROUPBY=cdstage` 只能用于可刻录的 CD/DVD，以将列表分组为等待刻录的文件和磁盘上的文件。

*示例:* `Set GROUPBY=picsize`

在 **列表列标题[上下文菜单](/Manual/customize/the_customize_dialog/context_menus.zh.md)** 中，您可以使用 **%header%** 来引用右键单击的列。

*示例:* `Set GROUPBY=%header%,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

按指定列开启或关闭分组。请注意，列名称必须放在前面。

*示例:* `Set GROUPBY=picsize,toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前文件列表中的分组。

*示例:* `Set GROUPBY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**grouplist**</td><td>

在工具栏或菜单上使用时，命令会变成可按其分组的可用列的动态列表。添加 **GROUPSCHEME** 参数以显示为这些列定义的任何分组方案的子菜单。

*示例:* `Set GROUPBY=grouplist GROUPSCHEME`
</td></tr><tr><td>
GROUPCOLLAPSE</td><td>
/K</td><td>

**on**</td><td>

打开当前文件列表中用于分组的折叠选项。

您还可以将此与 `GROUPBY` 参数结合使用，以便在切换到分组模式时自动折叠所有组。

*示例:* `Set GROUPCOLLAPSE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭折叠选项。

*示例:* `Set GROUPCOLLAPSE off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件列表中开启或关闭折叠选项。请注意，您需要重新读取文件夹才能看到更改的结果。

*示例:* `Set GROUPCOLLAPSE=toggle`
</td></tr><tr><td>
GROUPCOMBINE</td><td>
/K</td><td>

**normal**</td><td>

将当前文件列表的文件夹格式中的 **分组 / 合并** 选项设为 **合并相似值**。这是默认分组行为。例如，按文件名分组时，您可能会为以 A-H、I-P 和 Q-Z 开头的名称创建组。

*示例:* `Set GROUPCOMBINE=normal GROUPBY=name`
</td></tr><tr><td>
</td><td>
</td><td>

**never**</td><td>

从不合并组值。如果打开此选项并且对文件列表进行分组，则会为每个不同的值创建一个组，而不是将一系列值归入单个组（例如，您将看到 A、B、C、D、E、F、G、H，而不是 A-H）。这仅对类似“用户描述”这样的文本字段真正有用。

*示例:* `Set GROUPCOMBINE=never`
</td></tr><tr><td>
</td><td>
</td><td>

**other**</td><td>

组将如 **normal** 选项一样合并，但是只有一个项目的组将进一步合并到一个名为 **其他** 的特殊组中。

*示例:* `Set GROUPCOMBINE=other`
</td></tr><tr><td>
</td><td>
</td><td>

**cycle**</td><td>

循环遍历三个分组模式。

*示例:* `Set GROUPCOMBINE=cycle`
</td></tr><tr><td>
GROUPFOLDERSATTOP</td><td>
/K</td><td>

**on**</td><td>

打开当前文件列表中的 **分组时将文件夹保留在顶部** 选项。

*示例:* `Set GROUPFOLDERSATTOP=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 **分组时将文件夹保留在顶部** 选项。

*示例:* `Set GROUPFOLDERSATTOP=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件列表中开启或关闭分组时将文件夹保留在顶部的选项。

*示例:* `Set GROUPFOLDERSATTOP=toggle`
</td></tr><tr><td>
GROUPREVERSE</td><td>
/K</td><td>

**on**</td><td>

反转当前文件列表中分组的方向。实际的组顺序会反转，而不是组中文件顺序。

*示例:* `Set GROUPREVERSE=on GROUPBY=picsize`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭反向分组。

*示例:* `Set GROUPREVERSE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件列表中开启或关闭反向分组。

*示例:* `Set GROUPREVERSE=toggle`
</td></tr><tr><td>
GROUPSCHEME</td><td>
/O</td><td>

*(无值)*</td><td>

与 **GROUPBY=grouplist** 参数一起使用时，此参数会为具有定义的[求值器分组方案](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.zh.md) 的任何列显示子菜单。

*示例:* `Set GROUPBY=grouplist GROUPSCHEME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<group\>*</td><td>

指定在使用 **GROUPBY** 参数启用分组时要使用的分组方案的名称。

*示例:* `Set GROUPBY=name GROUPSCHEME=first_letter`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当与生成项目列表的命令一起使用时（参见[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数在列表开头添加一个小标题。当列表为空时，标题将隐藏。标题仅适用于在与按钮自身相同的级别上生成多个项目的命令。

当 **HEADING** 自身使用而未指定文本值时，主按钮的标签文本将用于标题。

*示例:* `Set COLUMNSTOGGLE=columnlist HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果您希望标题文本不同于按钮的标签，则可以指定标题文本。

*示例:* `Set SORTBY=sortlist HEADING="Sort"`
</td></tr><tr><td>
HIDE</td><td>
/S</td><td>

*(无值)*</td><td>

隐藏任何 **Set** 命令工具栏按钮，在该按钮不可用时通常会被禁用，因为该功能不可用。此参数本身不执行任何操作 - 它仅与其他 **Set** 命令参数结合使用。

例如，当当前不在 FTP 文件夹中时，命令 `Set FTPMODE=ascii` 通常会在工具栏中禁用，但命令 `Set FTPMODE=ascii HIDE` 会导致该按钮从工具栏中移除，而不是仅仅禁用。
**设置**

| 命令 | 参数 | 值 | 描述 |
|---|---|---|---|
| `Set ATOMICDIRECTORYDELETIONS=toggle,grouped HIDE` | `/K` | **on** | 在当前文件列表中启用 *在文件名列中隐藏文件扩展名* 选项。 |
| | | **off** | 禁用 *隐藏文件扩展名* 选项。 |
| | | **toggle** | 在当前文件列表中启用或禁用 *隐藏文件扩展名* 选项。 |
| `Set HIDEFILTERATTR` | `/O` | *\<属性\>* | 在源文件列表中设置属性隐藏过滤器。所有指定属性都被设置的文件将从当前文件夹的显示中隐藏。 |
| | | | *\<属性\>* 值是以下一个或多个字母：**R**（只读）、**A**（压缩包）、**H**（隐藏）、**S**（系统）、**E**（加密）、**C**（压缩）、**O**（脱机）、**I**（未编入索引）、**P**（已固定）。有关详细说明，请参阅 [更改属性](/Manual/file_operations/changing_attributes.zh.md)。 |
| `Set HIDEFILTERFILENAME` | `/O` | *\<模式\>* | 将源文件列表中的文件名隐藏过滤器设置为指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。与模式匹配的文件将从当前文件夹的显示中隐藏。 |
| | | | 提供的模式前缀可以是 **regex:**，以指定模式是正则表达式。 |
| | | | 如果指定的模式已设置为过滤器，则会清除文件名过滤器，这会使得该命令自动充当切换器。您还可以指定两组属性，并且在每次运行命令时，它会在这些属性之间交替。 |
| `Set HIDEFILTERFOLDERATTR` | `/O` | *\<属性\>* | 在源文件列表中设置文件夹属性隐藏过滤器。所有指定属性都被设置的文件夹将从当前文件夹的显示中隐藏。 |
| | | | *\<属性\>* 值是以下一个或多个字母：**R**（只读）、**A**（压缩包）、**H**（隐藏）、**S**（系统）、**E**（加密）、**C**（压缩）、**O**（脱机）、**I**（未编入索引）、**P**（已固定）。有关详细说明，请参阅 [更改属性](/Manual/file_operations/changing_attributes.zh.md)。 |
| | | | 如果指定的属性已设置为过滤器，则会清除过滤器，这会使得该命令自动充当切换器。您还可以指定两组属性，并且在每次运行命令时，它会在这些属性之间交替。 |
| | | | **off** | 禁用单独的文件夹属性隐藏过滤器。当禁用文件夹属性过滤器后，常规属性过滤器将同时应用于文件和文件夹。 |
| `Set HIDEFILTERFOLDERS` | `/O` | *\<模式\>* | 清除源文件列表中的文件夹隐藏过滤器。这会修改当前文件夹的文件夹选项 - **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中的等效设置是 *过滤器 / 隐藏过滤器 / 文件夹名称*。 |
| `Set HIDESYSTEMFILES` | `/K` | **on** | 启用配置中 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面上的 **隐藏受保护的操作系统文件** 选项。此选项会导致隐藏同时具有 H（隐藏）和 S（系统）属性的所有文件和文件夹。 |
| | | | **off** | 关闭 **隐藏受保护的操作系统文件** 选项。 |
| | | | **toggle** | 启用或禁用 **隐藏受保护的操作系统文件** 选项。 |
| `Set ICONMODESORTHEADER` | `/K` | **on** | 开启在图标模式（大图标、缩略图等）中显示列头（用于排序）。这控制配置中 **[文件列表 / 选项](/Manual/preferences/preferences_categories/file_displays/options/README.zh.md)** 页面上的 *在图标模式中显示排序头*。 |
| | | | **off** | 关闭图标模式中的列头。 |
| | | | **toggle** | 启用和禁用图标模式列头。 |
| `Set ICONS` | `/K` | **on** | 启用在当前文件列表中的高级和详细信息视图模式中显示图标。这会覆盖配置中相应页面上的设置（**[文件列表模式 / 详细信息](/Manual/preferences/preferences_categories/file_display_modes/details_mode.zh.md)** 或 **[文件列表模式 / 高级模式](/Manual/preferences/preferences_categories/file_display_modes/power_mode/README.zh.md)**）。
**Example:** `Set ICONS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前文件列表的电力及细节模式中图标的显示。

**范例：**`Set ICONS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

切换电力及细节模式中图标的显示。

**范例：**`Set ICONS=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**重置**</td><td>

将图标显示重置为当前的「偏好设置」。

**范例：**`Set ICONS=reset`
</td></tr><tr><td>
IMAGEASPECTOVERLAYS</td><td>
/K</td><td>

**on**</td><td>

启用显示缩略图模式的长宽比条形图。这会修改「偏好设置」中「[档案显示模式/缩略图](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)」页面上的**叠加长宽比条形图**选项。因为这是全局设置，所有目前开启的文件窗口都会受到影响。

**范例：**`Set IMAGEASPECTOVERLAYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭显示缩略图模式的长宽比条形图。

**范例：**`Set IMAGEASPECTOVERLAYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

开启或关闭显示缩略图模式的长宽比条形图。

**范例：**`Set IMAGEASPECTOVERLAYS=toggle`
</td></tr><tr><td>
INVERT</td><td>
/S</td><td>

*（无值）*</td><td>

反转当他们控制的**设定**选项目前开启时，出现突出显示（或勾选）工具列按钮。

例如，当文件夹树状图显示时，如`Set TREE=toggle`之类的指令将会在工具栏上突出显示。将该指令更改为`Set TREE=toggle INVERT`会导致当树状图未显示时，工具列按钮突出显示。

**范例：**`Set HIDESYSTEMFILES=toggle INVERT`
</td></tr><tr><td>
JOBSBAR</td><td>
/K</td><td>

**on**</td><td>

在当前文件窗口中显示[工作栏](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.zh.md)。

**范例：**`Set JOBSBAR=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在当前文件窗口中隐藏[工作栏](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.zh.md)。

**范例：**`Set JOBSBAR=off`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

切换开启或关闭[工作栏](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.zh.md)。

**范例：**`Set JOBSBAR=toggle`
</td></tr><tr><td>
KEEPFOLDERSALPHA</td><td>
/K</td><td>

**on**</td><td>

在原始档案显示中开启**保持文件夹按字母顺序排列**选项。这会修改当前文件夹的**[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

**范例：**`Set KEEPFOLDERSALPHA=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭**保持文件夹按字母顺序排列**选项。

**范例：**`Set KEEPFOLDERSALPHA off`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

切换**保持文件夹按字母顺序排列**选项的状态。

**范例：**`Set KEEPFOLDERSALPHA=toggle`
</td></tr><tr><td>
LAYOUT</td><td>
/K</td><td>

**记住**</td><td>

记住活动文件窗口目前的版型和外观。

**范例：**`Set LAYOUT=remember`
</td></tr><tr><td>
</td><td>
</td><td>

**还原**</td><td>

还原活动文件窗口先前记住的版型和外观。例如，如果您执行`Set LAYOUT=remember`指令，然后对文件窗口做出诸如关闭树状结构、开启查看器窗格或选择新的[样式](/Manual/basic_concepts/the_lister/styles.zh.md)等更动，`Set LAYOUT=restore`指令会将文件窗口还原为原始状态。

**范例：**`Set LAYOUT=restore`
</td></tr><tr><td>
LISTERCMD</td><td>
/K</td><td>

**最小化**</td><td>

最小化目前活跃的文件窗口窗口。

**范例：**`Set LISTERCMD=minimize`
</td></tr><tr><td>
</td><td>
</td><td>

**最大化**</td><td>

最大化目前活跃的文件窗口窗口。

**范例：**`Set LISTERCMD=maximize`
</td></tr><tr><td>
</td><td>
</td><td>

**还原**</td><td>

还原窗口最初的大小与位置（它被最小化或最大化之前）。

**范例：**`Set LISTERCMD=restore`
</td></tr><tr><td>
</td><td>
</td><td>

**切换最大化**</td><td>

如果当前的文件窗口窗口没有最大化，它将会被最大化，否则它将会被还原。您可以利用此指令新增一个切换文件窗口进出「全屏幕」模式的热键。

**范例：**`Set LISTERCMD=togglemaximize`
</td></tr><tr><td>
</td><td>
</td><td>

**全部显示**</td><td>

让所有当前开启的文件窗口显示。最小化窗口将被还原，所有的文件窗口窗口将挪至最前。

**范例：**`Set LISTERCMD=showall`
</td></tr><tr><td>
</td><td>
</td><td>

**全部最小化**</td><td>

最小化所有当前开启的文件窗口。

**范例：**`Set LISTERCMD=minimizeall`
</td></tr><tr><td>
</td><td>
</td><td>

**平铺横向**</td><td>

水平于屏幕平铺所有当前开启的文件窗口。

**范例：**`Set LISTERCMD=tileh`
</td></tr><tr><td>
</td><td>
</td><td>

**平铺垂直**</td><td>

垂直于屏幕平铺所有文件窗口。

**范例：**`Set LISTERCMD=tilev`
</td></tr><tr><td>
</td><td>
</td><td>

**层叠**</td><td>

层叠所有文件窗口窗口。所有窗口大小相同，并错列对角线地分布于屏幕上。

**范例：**`Set LISTERCMD=cascade`
</td></tr><tr><td>
</td><td>
</td><td>

**取消平铺层叠**</td><td>

取消前一个平铺或层叠操作。尽可能地将窗口恢复到它们前一个的大小及位置。

**范例：**`Set LISTERCMD=undotilecascade`
</td></tr><tr><td>
</td><td>
</td><td>

**切换全部最小化**</td><td>

最小化所有目前开启的文件窗口窗口。如果所有窗口都已经最小化，它们都将会被还原。

**范例：**`Set LISTERCMD=toggleminimizeall`
</td></tr><tr><td>
</td><td>
</td><td>

**置于最前**</td><td>

将文件窗口窗口置于最前。当从[脚本](/Manual/scripting/README.zh.md)执行此指令时，最为有用。

**范例：**`Set LISTERCMD=tofront`
</td></tr><tr><td>
LISTERPOS</td><td>
/K</td><td>

*\<x\>,\<y\>*</td><td>

将活动文件窗口的位置，设定为指定的 x 及 y 坐标。您亦可指定一个 delta 来修改当前位置。

**范例：**`Set LISTERPOS=500,200`
**范例：**`Set LISTERPOS=+100,+50`
</td></tr><tr><td>
LISTERSIZE</td><td>
/K</td><td>

*\<w\>,\<h\>*</td><td>

将目前活跃的文件窗口的大小，设定为指定的宽度及高度。您亦可指定一个 delta 来修改当前大小。

**范例：**`Set LISTERSIZE=1024,768`
**范例：**`Set LISTERSIZE=+50,+50`
</td></tr><tr><td>
</td><td>
</td><td>

**自动**</td><td>

自动（尽可能）水平调整文件窗口大小，以完全符合目前显示的栏（仅限于「详细」或「电源」模式）。

**范例：**`Set LISTERSIZE=auto`
</td></tr><tr><td>
LISTERTITLE</td><td>
/O</td><td>

*（无值）*</td><td>

将目前文件窗口的标题重置回预设值。

**范例：**`Set LISTERTITLE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<自订标题\>*</td><td>

设定目前活跃文件窗口的自订标题。您可以在标题字串中使用一些特殊的「标记」，以插入各种资讯：
</code>
|        |                                                                       |
|--------|-----------------------------------------------------------------------|
| **%P** | 当前 (源) 文件夹的完整路径                                        |
| **%N** | 当前 (源) 文件夹的名称                                         |
| **%R** | 当前 (源) 文件夹的驱动器根目录                                  |
| **%D** | 目标文件夹的完整路径                                         |
| **%M** | 目标文件夹的名称                                                |
| **%G** | 如果文件夹是联结或符号链接，目标                                 |
| **%1** | 左侧文件列表的完整路径                                          |
| **%2** | 右侧文件列表的完整路径                                         |
| **%3** | 左侧文件列表的文件夹名称                                        |
| **%4** | 右侧文件列表的文件夹名称                                       |
| **%L** |文件窗口所来自布局的名称 (如果有)                               |
| **%S** |文件窗口中选定的当前样式的名称 (如果有)                         |
| **%T** | 完整的原始标题 (有助于仅添加前缀或后缀)                     |
| **%!** | 隐藏部分                                                        |

*示例：* `Set LISTERTITLE "Directory Opus - %N"`

此命令通常作为切换方式，当指定标题已设置时，执行该命令会清除标题。你可以通过标题前加“notoggle:”来防止这种情况。这对于可能提出冗余标题设置请求并需检查其当前值以避免在其他情况下重置标题的事件驱动脚本而言非常有用。

*示例：* `Set LISTERTITLE "notoggle:Directory Opus - %N"`

**%!** 代码让你可以隐藏其中所有其他令牌都为空的字符串中的部分。

*示例：* `Set LISTERTITLE "%!%T - %!Directory Opus"`

这意味着，如果 **%T** 令牌扩展为一个空字符串，结果将只是“Directory Opus”，而不是“ - Directory Opus”。
</td></tr><tr><td>
MANUALSORT</td><td>
/K</td><td>

**on**</td><td>

打开当前文件列表中的[手动排序](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.zh.md)。将使用默认手动排序顺序，除非已配置其他手动排序名称以及你使用 *\<name>* 参数指定名称。

*示例：* `Set MANUALSORT=on,MySortOrder`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前源文件列表中的手动排序。

*示例：* `Set MANUALSORT=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件列表中开启或关闭手动排序模式。

*示例：* `Set MANUALSORT=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

*\<name>*</td><td>

指定要使用的排序顺序的其他名称，该名称必须首先在配置中的 **[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上配置 **manual_sort_names** 选项。

*示例：* `Set MANUALSORT=MySortOrder,toggle`
</td></tr><tr><td>
MANUALSORTRESET</td><td>
/O</td><td>

*(无值)*</td><td>

重置源文件列表中文件夹的当前手动排序顺序。将使用当前（非手动）排序方法对文件列表重新排序，并将丢弃你的旧手动排序顺序。

*示例：* `Set MANUALSORTRESET`
</td></tr><tr><td>
</td><td>
</td><td>

*\<name>*</td><td>

重置当前文件夹的指定手动排序顺序。该名称必须首先在配置中的 **[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上配置 **manual_sort_names** 选项。

*示例：* `Set MANUALSORTRESET=MySortOrder`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

重置当前文件夹的默认手动排序顺序。

*示例：* `Set MANUALSORTRESET=!default`
</td></tr><tr><td>
</td><td>
</td><td>

**!all**</td><td>

重置当前文件夹的所有手动排序顺序（默认和已命名）。

*示例：* `Set MANUALSORTRESET=!all`
</td></tr><tr><td>
MANUALSORTSAVE</td><td>
/S</td><td>

*(无值)*</td><td>

保存当前文件夹中的当前手动排序顺序。仅当未启用手动排序顺序的自动保存时，才需要使用此命令。

*示例：* `Set MANUALSORTSAVE`
</td></tr><tr><td>
METAPANE</td><td>
/K</td><td>

**on**</td><td>

在当前激活的文件窗口中打开[元数据面板](/Manual/basic_concepts/the_lister/metadata_pane.zh.md)。

*示例：* `Set METAPANE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件窗口中关闭元数据面板。

*示例：* `Set METAPANE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

开启或关闭元数据面板。

*示例：* `Set METAPANE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

当元数据面板打开时，强制它采用水平布局。

*示例：* `Set METAPANE=toggle,horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

指定元数据面板的垂直布局。

*示例：* `Set METAPANE=on,vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

在垂直和水平之间切换元数据面板的布局。

*示例：* `Set METAPANE=togglelayout`
</td></tr><tr><td>
METAPANESIZE</td><td>
/K</td><td>

*\<size>\[,\<size>\]*</td><td>

调整活动文件窗口中元数据面板的尺寸。尺寸表示为文件窗口总尺寸的百分比，并根据元数据面板的当前布局应用于适当的维度（例如，当面板为水平方向时，会影响其高度）。

还可以指定两个不同的尺寸，此命令将在它们之间切换。

*示例：* `Set METAPANESIZE 25,50`
</td></tr><tr><td>
MINIMIZEPROGRESS</td><td>
/K</td><td>

**on**</td><td>

打开配置中 [进度指示器](/Manual/preferences/preferences_categories/file_operations/progress_indicators/README.zh.md) 页面的 *自动最大化进度指示器* 选项。

*示例：* `Set MINIMIZEPROGRESS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 *自动最大化进度指示器* 选项。

*示例：* `Set MINIMIZEPROGRESS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

开启或关闭 *自动最大化进度指示器*。

*示例：* `Set MINIMIZEPROGRESS=toggle`
</td></tr><tr><td>
NAVLOCK</td><td>
/K</td><td>

**on**</td><td>

在当前文件窗口中打开[导航锁定](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.zh.md)。只有当文件窗口处于 [双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式时，此命令才可用。

*示例：* `Set NAVLOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件窗口中关闭导航锁定。

*示例：* `Set NAVLOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>
切换活动文件窗口的导航锁。

*示例：* `Set NAVLOCK=toggle`
</td></tr><tr><td>
NOOP</td><td>
/S</td><td>

*(无值)*</td><td>

保证没有任何操作。如果指定，其他参数将被忽略。可用于创建一个不执行任何操作的热键，以便按下该键不会触发即时查找或任何其他操作。

*示例：* `Set NOOP`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(无值)*</td><td>

使用 **NOSCRIPT** 参数可阻止与 Set 命令响应的 [脚本事件](/Manual/scripting/script_add-ins/README.zh.md) 的触发。目前，此功能仅适用于 `Set LISTERCMD=ToFront` 命令，以防止触发 **[OnActivate文件窗口](../../scripting_reference/scripting_events/onactivatelister.zh.md)** 事件。

*示例：* `Set LISTERCMD=ToFront NOSCRIPT`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

*\<预设名\>*</td><td>

与 **UTILITY** 参数结合使用时，这允许你打开查找/重复文件/同步面板并自动加载指定的预设。

*示例：* `Set UTILITY=Find,Toggle PRESET=WorkDocuments`
</td></tr><tr><td>
PROGRESSCMD</td><td>
/K</td><td>
最小化</td><td>

向所有当前进度对话框发送“最小化”命令。所有当前可见的进度都会被最小化。

*示例：* `Set PROGRESSCMD=minimize`
</td></tr><tr><td>
</td><td>
</td><td>
还原</td><td>
向所有进度对话框发送“还原”命令。所有当前最小化的进度都将恢复为可见。
</td></tr><tr><td>
</td><td>
</td><td>
显示</td><td>
将所有非最小化的进度对话框置于前面。
</td></tr><tr><td>
</td><td>
</td><td>
暂停</td><td>
向所有进度对话框发送“暂停”命令。所有支持暂停的正在运行的操作都将暂停。
</td></tr><tr><td>
</td><td>
</td><td>
恢复</td><td>
向所有进度对话框发送“恢复”命令。所有暂停的操作都将恢复。
</td></tr><tr><td>
</td><td>
</td><td>
中止</td><td>

向所有进度对话框发送“中止”命令。所有正在运行 **和** 正在排队的操作都将被中止。
</td></tr><tr><td>
QUICKFILTER</td><td>
/O</td><td>

*(无值)*</td><td>

显示 [过滤工具栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md) 并在其上让键盘获得焦点。与在默认键盘配置下按 \* 键类似。

*示例：* `Set QUICKFILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<模式\>*</td><td>

将当前源文件列表中的快速过滤器设置为指定的 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。这是由 [过滤工具栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md) 编辑的相同过滤器。不匹配该模式的文件将从显示中隐藏。

通常，如果过滤器已设置为指定模式，则将清除该模式，使命令自动作为切换命令工作。

*示例：* `Set QUICKFILTER=\*.jpg`

你可以通过在模式前加上“notoggle:”的前缀来防止自动切换。

*示例：* `Set QUICKFILTER="notoggle:Hello World.\*"`
</td></tr><tr><td>
</td><td>
</td><td>

**!clear**</td><td>

清除当前文件列表中的快速过滤器模式。请注意，这不会清除 **QUICKFILTERFLAGS** 值，因此，即使过滤器模式被清除，文件仍有可能被过滤掉。要完全清除快速过滤器，请使用 **QUICKFILTERCLEAR** 参数。

*示例：* `Set QUICKFILTER=!clear`
</td></tr><tr><td>
</td><td>
</td><td>

**!prev**</td><td>

恢复当前文件列表中的前一个快速过滤器。默认情况下，当更改文件夹时，快速过滤器会被清除（尽管这可以通过配置中 **[文件列表/过滤工具栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md)** 页面上的 **更改文件夹时自动清除快速过滤器** 选项来更改）。例如，你可以在进入子目录然后返回父目录后，分配一个热键来恢复前一个过滤器。

*示例：* `Set QUICKFILTER=!prev`
</td></tr><tr><td>
QUICKFILTERCLEAR</td><td>
/S</td><td>

*(无值)*</td><td>

清除当前源文件列表中的快速过滤器。过滤器模式和标志都将被清除。这不会影响由文件夹选项或配置中的全局过滤器引起的过滤。

*示例：* `Set QUICKFILTERCLEAR`
</td></tr><tr><td>
QUICKFILTERFLAGS</td><td>
/O</td><td>

*(无值)*</td><td>

重置并清除当前源文件列表中的快速过滤器标志。标志如下所示。清除标志不会清除过滤器模式，因此，即使标志被清除，文件仍有可能被过滤掉。

*示例：* `Set QUICKFILTERFLAGS`

另外，可以使用 **QUICKFILTERCLEAR** 参数完全清除快速过滤器，包括模式和标志。
</td></tr><tr><td>
</td><td>
</td><td>

**set**</td><td>

与其他标志结合使用时，确保这些标志始终保持开启。如果没有 **set** 或 **clear**，其他指定的标签将被 *切换*，即关闭时打开，打开时关闭。

*示例：* `Set QUICKFILTERFLAGS=set,showfiles`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

与其他标志结合使用时，确保这些标志始终保持关闭。如果没有 **set** 或 **clear**，其他指定的标签将被 *切换*，即关闭时打开，打开时关闭。

*示例：* `Set QUICKFILTERFLAGS=clear,showfiles`
</td></tr><tr><td>
</td><td>
</td><td>

**showfiles**</td><td>

显示所有文件，即使它们被过滤器模式隐藏。这不会覆盖文件夹格式或全局过滤器。

*示例：* `Set QUICKFILTERFLAGS=showfiles`

启用 **showfiles** 会自动关闭 **hidefiles**。
</td></tr><tr><td>
</td><td>
</td><td>

**showdirs**</td><td>

显示所有文件夹，即使它们被过滤器模式隐藏。

*示例：* `Set QUICKFILTERFLAGS=showdirs QUICKFILTER="a\*"`

启用 **showdirs** 会自动关闭 **hidedirs**。
</td></tr><tr><td>
</td><td>
</td><td>

**hidefiles**</td><td>

隐藏所有文件，即使它们匹配过滤器模式。

*示例：* `Set QUICKFILTERFLAGS=hidefiles`

启用 **hidefiles** 会自动关闭 **showfiles**，还会关闭 **hidedirs**，除非同时指定了 **set**。
</td></tr><tr><td>
</td><td>
</td><td>

**hidedirs**</td><td>

隐藏所有文件夹，即使它们匹配过滤器模式。

*示例：* `Set QUICKFILTERFLAGS=hidedirs`

启用 **hidedirs** 会自动关闭 **showdirs**，还会关闭 **hidefiles**，除非同时指定了 **set**。
</td></tr><tr><td>
</td><td>
</td><td>

**disable**</td><td>

暂时禁用快速过滤器，保留过滤器模式不变。

*示例：* `Set QUICKFILTERFLAGS=disable`
</td></tr><tr><td>
</td><td>
</td><td>

**flatviewon**</td><td>

当处于平面视图中时启用文件夹的过滤，覆盖全局配置设置。

*示例：* `Set QUICKFILTERFLAGS=flatviewon`
</td></tr><tr><td>
</td><td>
</td><td>

**flatviewoff**</td><td>

当处于平面视图中时禁用文件夹的过滤，覆盖全局配置设置。
**regexpon**

开启正则表达式（取代通配符），覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=regexpon`
</td></tr><tr><td>
</td><td>
</td><td>

**regexpoff**

关闭正则表达式（即强制使用通配符），覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=regexpoff`
</td></tr><tr><td>
</td><td>
</td><td>

**ignorediacriticson**

开启“忽略变音符号”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=ignorediacriticson`
</td></tr><tr><td>
</td><td>
</td><td>

**ignorediacriticsoff**

关闭“忽略变音符号”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=ignorediacriticsoff`
</td></tr><tr><td>
</td><td>
</td><td>

**anywordon**

开启“匹配任意词语”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=anywordon`
</td></tr><tr><td>
</td><td>
</td><td>

**anywordoff**

关闭“匹配任意词语”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=anywordoff`
</td></tr><tr><td>
</td><td>
</td><td>

**partialon**

开启“部分匹配”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=partialon`
</td></tr><tr><td>
</td><td>
</td><td>

**partialoff**

关闭“部分匹配”选项，覆盖全局配置设置。

*示例:* `Set QUICKFILTERFLAGS=partialoff`
</td></tr><tr><td>
READONLY</td><td>
/K</td><td>

**on**

使当前文件列表为只读。目前仅支持 Zip 压缩包文件。当文件列表被标记为只读时，将无法修改当前 Zip 压缩包文件的内容。在没有查看 Zip 压缩包文件时，此命令无效。

*示例:* `Set READONLY=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**

清除当前文件列表的只读标志。配置的**[Zip 及其他压缩包文件/Zip 文件](/Manual/preferences/preferences_categories/zip_and_other_archives/zip_file_options.zh.md)**页面上的**默认情况下以只读方式打开 Zip 文件**选项可以使 Zip 压缩包文件默认情况下为只读，然后你可以使用此命令来使其可写。

*示例:* `Set READONLY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**

在当前文件列表中切换只读标志的开或关状态。

*示例:* `Set READONLY=TOGGLE`
</td></tr><tr><td>
RECYCLEBINEMPTY</td><td>
/S</td><td>

*（无值）*</td><td>

作为一个命令，它没有任何效果 - 它仅可与**@ifset**和**@icon**[命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md)一起使用。它让你测试回收站当前是否为空。

//<示例://>

    @ifset:RECYCLEBINEMPTY
    @confirm 回收站
     为空！
    @ifset:else
    删除EMPTYRECYCLE
</td></tr><tr><td>
RELATIVEDATEGRAPHS</td><td>
/K</td><td>

**on**

开启配置中的**[文件列表列/选项](/Manual/preferences/preferences_categories/file_display_columns/options.zh.md)**页面的**显示修改和创建日期和时间列后的图表**选项。由于这是一项全局设置，因此所有当前打开的文件窗口都会受到影响。

*示例:* `Set RELATIVEDATEGRAPHS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**

关闭**显示日期列之后的图表**选项。

*示例:* `Set RELATIVEDATEGRAPHS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**

切换**显示日期列之后的图表**选项的开或关状态。

*示例:* `Set RELATIVEDATEGRAPHS=toggle`
</td></tr><tr><td>
RELATIVESIZEGRAPHS</td><td>
/K</td><td>

**on**

开启配置中的**[文件列表列/选项](/Manual/preferences/preferences_categories/file_display_columns/options.zh.md)**页面的**显示大小列后的图表**选项。由于这是一项全局设置，因此所有当前打开的文件窗口都会受到影响。

*示例:* `Set RELATIVESIZEGRAPHS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**

关闭**显示大小列之后的图表**选项。

*示例:* `Set RELATIVESIZEGRAPHS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**

切换**显示大小列之后的图表**选项的开或关状态。

*示例:* `Set RELATIVESIZEGRAPHS=toggle`
</td></tr><tr><td>
RELDIMENSIONOVERLAYS</td><td>
/K</td><td>

**on**

打开缩略图模式相对尺寸栏的显示。这修改了配置中的**[文件列表模式/缩略图](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)**页面的**覆盖相对尺寸栏**选项。由于这是一项全局设置，因此所有当前打开的文件窗口都会受到影响。

*示例:* `Set RELDIMENSIONOVERLAYS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**

关闭缩略图模式相对尺寸栏的显示。

*示例:* `Set RELDIMENSIONOVERLAYS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**

切换缩略图模式相对尺寸栏的显示的开或关状态。

*示例:* `Set RELDIMENSIONOVERLAYS=toggle`
</td></tr><tr><td>
SAVEFORMAT</td><td>
/O</td><td>

*（无值）*</td><td>

显示*保存文件夹格式*对话框，让你可以在源文件列表中保存[文件夹格式](/Manual/basic_concepts/folder_options/README.zh.md)。

*示例:* `Set SAVEFORMAT`
</td></tr><tr><td>
</td><td>
</td><td>

**folder**

保存当前文件夹的文件夹格式（不显示*保存文件夹格式*对话框）。你可以将此与**replace**和**subfolders**参数或**clear**参数结合使用。

*示例:* `Set SAVEFORMAT=folder`
</td></tr><tr><td>
</td><td>
</td><td>

**all**

保存所有文件夹的当前格式（即，这使其成为新的**用户默认**格式）。你可以将此与**clear**、**replace**和**quiet**参数结合使用。

*示例:* `Set SAVEFORMAT=all`
</td></tr><tr><td>
</td><td>
</td><td>

**favorite**

将当前格式保存为**收藏夹格式**。你可以使用**FORMAT**参数指定格式名称。

*示例:* `Set SAVEFORMAT=favorite FORMAT "我的最爱格式"`
</td></tr><tr><td>
</td><td>
</td><td>

**subfolders**

与**folder**参数一起使用，保存当前文件夹和所有子文件夹的文件夹格式。

*示例:* `Set SAVEFORMAT=folder,subfolders`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**

与**folder**或**all**参数一起使用，将布局和样式中任何现有的文件夹格式替换为新格式。

*示例:* `Set SAVEFORMAT=all,replace`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**

与**folder**参数一起使用，删除当前文件夹的已保存格式（如果有）。

*示例:* `Set SAVEFORMAT=folder,clear`

与**all**参数一起使用，清除任何现有的已保存文件夹格式（这样将使用新的**用户默认**格式）。
*示例:* `Set SAVEFORMAT=all,clear`

清除格式后，您可以通过 `Set FORMAT=!folder` 或类似方式告诉文件夹标签重新求值其当前路径的格式。
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

与 **all** 参数一起使用，可以阻止在替换所有现有文件夹格式前出现警告对话框。

*示例:* `Set SAVEFORMAT=all,replace,quiet`
</td></tr><tr><td>
SHOWEVERYTHING</td><td>
/K</td><td>

**on**</td><td>

开启源文件列表中的 *[显示所有](/Manual/basic_concepts/searching_and_filtering/show_everything.zh.md)* 模式。这将覆盖所有活动过滤器，并确保所有文件和文件夹均可见。

*示例:* `Set SHOWEVERYTHING=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭源文件列表中的 *显示所有* 模式。

*示例:* `Set SHOWEVERYTHING=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

开启或关闭显示所有模式。

示例: `Set SHOWEVERYTHING=toggle`
</td></tr><tr><td>
SHOWFILTERATTR</td><td>
/O</td><td>

*(无值)* </td><td>

清除源文件列表中的属性显示过滤器；这将修改当前文件夹的文件夹选项 - **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中的等效设置是 *过滤器 / 显示过滤器 / 属性*。

*示例:* `Set SHOWFILTERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

设置源文件列表中的属性显示过滤器。只会显示已设置指定属性的文件，所有其他属性的文件将被隐藏。

*\<attributes\>* 值为以下一个或多个字母：**R**（只读）、**A**（压缩包）、**H**（隐藏）、**S**（系统）、**E**（加密）、**C**（压缩）、**O**（脱机）、**I**（非索引）、**P**（固定）。有关详细说明，请参阅[调整属性](/Manual/file_operations/changing_attributes.zh.md)。

*示例:* `Set SHOWFILTERATTR e`

如果已经将指定属性设置为过滤器，则会清除过滤器，使得命令立即自动充当开关。您还可以指定两组属性，并且该命令将在每次运行时在这些属性之间交替。

*示例:* `Set SHOWFILTERATTR e,ra`
</td></tr><tr><td>
SHOWFILTERFILENAME</td><td>
/O</td><td>

*(无值)* </td><td>

清除源文件列表中的文件名显示过滤器；这将修改当前文件夹的文件夹选项 - **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中的等效设置是 *过滤器 / 显示过滤器 / 文件名*。

示例: `Set SHOWFILTERFILENAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

将源文件列表中的文件名显示过滤器设置为指定的 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。只会显示与该模式匹配的文件，源文件列表中将隐藏所有其他文件。

提供的模式可使用 **regex:** 作为前缀，指定该模式为正则表达式。

如果已经将指定模式设置为过滤器，则会清除过滤器，使得命令立即自动充当开关。

*示例:* `Set SHOWFILTERFILENAME \*.(doc\|xls)`
</td></tr><tr><td>
SHOWFILTERFOLDERATTR</td><td>
/O</td><td>

*(无值)*</td><td>

清除源文件列表中的文件夹属性显示过滤器；这将修改当前文件夹的文件夹选项 - **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中的等效设置是 *过滤器 / 显示过滤器 / 文件夹属性*。

示例: `Set SHOWFILTERFOLDERATTR`
</td></tr><tr><td>
</td><td>
</td><td>

*\<attributes\>*</td><td>

设置源文件列表中的文件夹属性显示过滤器。只会显示已设置指定属性的文件夹，所有其他属性的文件夹将被隐藏。

*\<attributes\>* 值为以下一个或多个字母：**R**（只读）、**A**（压缩包）、**H**（隐藏）、**S**（系统）、**E**（加密）、**C**（压缩）、**O**（脱机）、**I**（非索引）、**P**（固定）。有关详细说明，请参阅[调整属性](/Manual/file_operations/changing_attributes.zh.md)。

*示例:* `Set SHOWFILTERFOLDERATTR o`

如果已经将指定属性设置为过滤器，则会清除过滤器，使得命令立即自动充当开关。您还可以指定两组属性，并且该命令将在每次运行时在这些属性之间交替。

*示例:* `Set SHOWFILTERFOLDERATTR o,off`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

禁用单独的文件夹属性显示过滤器。当禁用文件夹属性过滤器时，常规属性过滤器将应用于文件和文件夹。

*示例:* `Set SHOWFILTERFOLDERATTR off`
</td></tr><tr><td>
SHOWFILTERFOLDERS</td><td>
/O</td><td>

*(无值)*</td><td>

清除源文件列表中的文件夹显示过滤器；这将修改当前文件夹的文件夹选项 - **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)** 对话框中的等效设置是 *过滤器 / 显示过滤器 / 文件夹名称*。

示例: `Set SHOWFILTERFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

将源文件列表中的文件夹显示过滤器设置为指定的 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。只会显示名称与该模式匹配的文件夹，源文件列表中将隐藏所有其他文件夹。

提供的模式可使用 **regex:** 作为前缀，指定该模式为正则表达式。

如果已经将指定模式设置为过滤器，则会清除过滤器，使得命令立即自动充当开关。

*示例:* `Set SHOWFILTERFOLDERS "\* Reports \*"`
</td></tr><tr><td>
SHOWMILLIS</td><td>
/K</td><td>

**on**</td><td>

打开文件时间列中毫秒的显示功能。该操作控制 [文件列表列 / 选项](/Manual/preferences/preferences_categories/file_display_columns/options.zh.md) 配置页面中的 **显示毫秒** 选项。请注意，秒也必须显示，此命令才具有任何效果。

*示例:* `Set SHOWMILLIS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭文件时间列中毫秒的显示功能。

*示例:* `Set SHOWMILLIS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

开启或关闭毫秒的显示功能。

*示例:* `Set SHOWMILLIS=toggle`
</td></tr><tr><td>
SHOWSECONDS</td><td>
/K</td><td>

**on**</td><td>

打开文件时间列中秒的显示功能。该操作控制 [文件列表列 / 选项](/Manual/preferences/preferences_categories/file_display_columns/options.zh.md) 配置页面中的 **显示秒** 选项。

*示例:* `Set SHOWSECONDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭文件时间列中秒的显示功能。

*示例:* `Set SHOWSECONDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

开启或关闭秒的显示功能。

*示例:* `Set SHOWSECONDS=toggle`
</td></tr><tr><td>
SIDE</td><td>
/K</td><td>

**左**</td><td>

当作为条件进行测试时，如果命令位于连接到文件列表左侧（或顶部）的 [地址栏工具栏](/Manual/basic_concepts/the_lister/navigation/file_display_border.zh.md) 上，则返回 true。

*示例:* `@<图标:copysourcedest_right,Set> SIDE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**右**</td><td>

当连接到右侧（或底部）文件列表时为真。

*示例:* `@<图标:copysourcedest_left,Set> SIDE=right`
</td></tr><tr><td>
SORTBY</td><td>
/K</td><td>

*\<列\>, ...*</td><td>

按指定列 [对](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 当前文件列表进行排序。该值必须是有效 [列关键字](../../metadata_keywords/keywords_for_columns.zh.md) 之一，并且该列也必须显示在文件列表中。

除了列关键字之外，**SORTBY** 还识别特殊的关键字同义词 **accessed**、**created**、**date, disksize, modified, path** 和 **size**。这使你可以按日期、大小或路径进行排序，而无需知道显示的确切列（例如，该列可以是 **size**、**sizekb** 或 **sizerel** - 但所有情况下排序相同，而 `Set SORTBY=size` 适用于任何列）。

可以通过指定多个用逗号分隔的关键字来按多个列对列表进行排序。你还可以指定特定列的排序顺序应通过在其关键字之前加上连字符来反转。

`Set SORTBY` 命令还可用于将指定列自动添加到文件列表中（因为列需要显示在列表中才能按其排序）。加上 **+** 号前缀以启用列。如果列尚未在列表中，它将被添加到现有列的结尾。如果该列尚不存在，你还可以在其中指定应添加列的位置 - 有关此内容的详细信息，请参阅 `Set COLUMNSADD` 命令的说明。

*示例:* `Set SORTBY=picsize,-modified`  
*示例:* `Set SORTBY=+datetaken`
</td></tr><tr><td>
</td><td>
</td><td>

**sortlist**</td><td>

当在工具栏或菜单上使用时，该命令将变为可排序可用列的动态列表。

*示例:* `Set SORTBY=sortlist`
</td></tr><tr><td>
SORTNAMEEXTSEPARATELY</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中打开 **按名称和扩展名分开排序** 选项。这将修改当前文件夹的 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTNAMEEXTSEPARATELY=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 **按名称和扩展名分开排序** 选项。

*示例:* `Set SORTNAMEEXTSEPARATELY=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭当前文件列表中的 **按名称和扩展名分开排序** 选项。

*示例:* `Set SORTNAMEEXTSEPARATELY=toggle`
</td></tr><tr><td>
SORTNEWFILES</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中打开 **按新创建和复制的文件排序** 选项。这将修改当前文件夹的 **[文件夹格式](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTNEWFILES=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭源文件列表中的 **按新创建和复制的文件排序** 选项。

*示例:* `Set SORTNEWFILES=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭源文件列表中的 **按新创建和复制的文件排序** 选项。

*示例:* `Set SORTNEWFILES=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**reset**</td><td>

将源文件列表的 **按新创建和复制的文件排序** 选项重置为 [排序](/Manual/preferences/preferences_categories/filtering_and_sorting/sorting.zh.md) 配置页面中的默认设置。

*示例:* `Set SORTNEWFILES=reset`
</td></tr><tr><td>
SORTNUMERIC</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中打开 **文件名排序的数字顺序** 选项。这将修改当前文件夹的 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTNUMERIC=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 **文件名排序的数字顺序** 选项。

*示例:* `Set SORTNUMERIC=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭当前文件列表中的 **按文件名排序的数字顺序** 选项。

*示例:* `Set SORTNUMERIC=toggle`
</td></tr><tr><td>
SORTORDER</td><td>
/K</td><td>

**folders**</td><td>

更改源文件列表中的排序顺序，以便文件夹列在文件之前。这将修改当前文件夹的 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTORDER=folders`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

在当前文件列表中列出文件之前的文件。

*示例:* `Set SORTORDER=files`
</td></tr><tr><td>
</td><td>
</td><td>

**mixed**</td><td>

在当前文件列表中一起对文件和文件夹进行排序。

*示例:* `Set SORTORDER=mixed`
</td></tr><tr><td>
</td><td>
</td><td>

**cycle**</td><td>

循环浏览当前文件列表中的三个不同的排序选项。

*示例:* `Set SORTORDER=cycle`
</td></tr><tr><td>
SORTREVERSE</td><td>
/K</td><td>

**on**</td><td>

反转当前文件列表中的排序顺序。如果仅按一列对列表进行排序，则该列排序的方向将被反转。如果选择了多列进行排序，则其方向不会改变，但总结果会在排序最后一步中被逆转。

这将修改当前文件夹的 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTREVERSE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭当前文件夹的反向排序标志，将排序顺序恢复为正常。

*示例:* `Set SORTREVERSE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭当前文件夹的反向排序。

*示例:* `Set SORTREVERSE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**togglesmart**</td><td>

打开或关闭当前文件夹的反向排序。如果在同一命令行上与 **SORTBY** 参数一起使用，则此参数的操作与 **toggle** 略有不同。如果为 **SORTBY** 指定的列已经排序，则排序顺序将被反转，但如果指定的列尚未排序，则排序顺序将不会被反转。

为了说明这一点，想象一下列表当前按名称正序排列，并且多次运行 `Set SORTBY=size SORTREVERSE=toggle` 命令。每次迭代后的排序顺序为：

1. 按名称正序排列
2. 按大小倒序排列
3. 按大小正序排列

将此与命令 `Set SORTBY=size SORTREVERSE=togglesmart` 进行对比：

1. 按名称正序排列
2. 按大小正序排列
3. 按大小倒序排列

*示例:* `Set SORTBY=desc SORTREVERSE=togglesmart`
</td></tr>
SORTWORDS</td><td>
/K</td><td>

**on**</td><td>

在源文件列表中打开 \*\*Word 排序 \*\*选项。这将修改当前文件夹的 **[文件夹选项](/Manual/basic_concepts/folder_options/README.zh.md)**。

*示例:* `Set SORTWORDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在源文件列表中关闭 **Word 排序** 选项。

*示例:* `Set SORTWORDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在当前文件夹中切换 **Word 排序** 选项。

*示例:* `Set SORTWORDS=toggle`
</td></tr><tr><td>
SOUNDS</td><td>
/K</td><td>

**on**</td><td>

在配置中的 **[其他 / 声音](/Manual/preferences/preferences_categories/miscellaneous/sounds.zh.md)** 页面上打开 **启用声音事件** 选项。

*示例:* `Set SOUNDS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭 **启用声音事件** 选项。

*示例:* `Set SOUNDS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

启用或禁用 **启用声音事件** 选项。

*示例:* `Set SOUNDS=toggle`
</td></tr><tr><td>
SOURCE</td><td>
/K</td><td>

**left**</td><td>

设置双栏文件窗口中的左侧（或顶部）文件列表为源。

*示例:* `Set SOURCE=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

设置右侧（或底部）文件列表为源。

*示例:* `Set SOURCE=right`
</td></tr><tr><td>
</td><td>
</td><td>

**focus**</td><td>

设置当前具有输入焦点的文件列表为源。

*示例:* `Set SOURCE=focus`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

切换左侧和右侧文件列表的状态（源/目标）。

*示例:* `Set SOURCE=toggle`
</td></tr><tr><td>
SPACING</td><td>
/K</td><td>

*\<item\>**:**\<value\>*</td><td>

修改各个用户界面元素（可以被 [用户界面间距方案](/Manual/preferences/preferences_categories/user_interface/spacing.zh.md) 更改的元素）的间距。

你可以指定一个或多个用逗号分隔的项，并为每个项提供新的绝对值或正负增量。

项关键字是：  
**detailslinespacing**, **detailslinepadding**, **powerlinespacing**, **powerlinepadding**, **pathiconleft**, **pathiconright**, **pathlabelleft**, **pathlabelright**, **thumbnailspacingh**, **thumbnailspacingv**, **tilespacingh**, **tilespacingv**, **treepadding**, **toolbarspacingh**, **toolbarspacingv**, **dragdistance**, **dblclkdistance**.

*示例:* `Set SPACING detailslinespacing:+16,powerlinespacing:+16`  
*示例:* `Set SPACING tilespacingv:20,tilespacingh:32`
</td></tr><tr><td>
SPACINGSCHEME</td><td>
/O</td><td>

*(no value)*</td><td>

生成已配置的 [用户界面间距方案](/Manual/preferences/preferences_categories/user_interface/spacing.zh.md) 列表。从列表中选择一个项目将会切换到该方案。

*示例:* `Set SPACINGSCHEME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<scheme name\>*</td><td>

切换到指定的 UI 间距方案。

*示例:* `Set SPACINGSCHEME=CouchFriendly`
</td></tr><tr><td>
</td><td>
</td><td>

**!default**</td><td>

重置为默认 UI 间距值。

*示例:* `Set SPACINGSCHEME=!default`
</td></tr><tr><td>
STATE</td><td>
/K</td><td>

**source**</td><td>

设置当前处于活动状态的文件窗口为源。当一个文件窗口成为源时，先前的源（如果有）将成为目标，而先前的目标（如果有）将被关闭。在一个双栏文件窗口中，此命令无效，因为当前处于活动状态的文件列表在定义上已经是源。

*示例:* `Set STATE=source`
</td></tr><tr><td>
</td><td>
</td><td>

**dest**</td><td>

设置当前处于活动状态的文件窗口为目标。在一个双栏文件窗口中，这相当于 `Set SOURCE=toggle` - 源将变为目标，反之亦然。

*示例:* `Set STATE=dest`
</td></tr><tr><td>
</td><td>
</td><td>

**lockoff**</td><td>

锁定活动文件窗口为关闭状态。当一个文件窗口被锁定为关闭状态时，单击它不会使其成为源或目标 - 只有另一个 `Set STATE` 命令才能解锁它。此命令在一个双栏文件窗口中无效。

*示例:* `Set STATE=lockoff`
</td></tr><tr><td>
STATUSBAR</td><td>
/K</td><td>

**on**</td><td>

在活动文件窗口中打开 [状态栏](/Manual/basic_concepts/the_lister/status_bar.zh.md)。

*示例:* `Set STATUSBAR=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件窗口中关闭状态栏。

*示例:* `Set STATUSBAR=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动文件窗口中打开或关闭状态栏。

*示例:* `Set STATUSBAR=toggle`
</td></tr><tr><td>
STATUSBARSTYLE</td><td>
/K</td><td>

**single**</td><td>

将状态栏样式设置为一个单一的状态栏，即使是在双栏文件窗口中。

*示例:* `Set STATUSBARSTYLE=single`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

一个单一的状态栏，在双栏模式下有单独的定义。

*示例:* `Set STATUSBARSTYLE=dual`
</td></tr><tr><td>
</td><td>
</td><td>

**independent**</td><td>

左侧/右侧文件列表的独立状态栏，左侧和右侧的定义是独立的。

*示例:* `Set STATUSBARSTYLE=independent`
</td></tr><tr><td>
</td><td>
</td><td>

**independentsame**</td><td>

左侧/右侧文件列表的独立状态栏，两侧的定义相同。

*示例:* `Set STATUSBARSTYLE=independentsame`
</td></tr><tr><td>
</td><td>
</td><td>

**bottom**</td><td>

将状态栏放在文件窗口的底部，而不是文件列表的底部。

*示例:* `Set STATUSBARSTYLE=dual,bottom`
</td></tr><tr><td>
</td><td>
</td><td>

**nobottom**</td><td>

将状态栏放在文件列表的底部，而不是文件窗口的底部。

*示例:* `Set STATUSBARSTYLE=independentsame,nobottom`
</td></tr><tr><td>
</td><td>
</td><td>

**glass**</td><td>

当状态栏位于文件窗口底部时启用玻璃效果。

*示例:* `Set STATUSBARSTYLE=bottom,glass`
</td></tr><tr><td>
</td><td>
</td><td>

**noglass**</td><td>

当状态栏位于文件窗口底部时禁用玻璃效果。

*示例:* `Set STATUSBARSTYLE=bottom,single,noglass`
</td></tr><tr><td>
TABPOSITION</td><td>
/K</td><td>

**above**</td><td>

设置当前文件窗口中的文件夹标签页在文件列表上方显示。这将覆盖 **[文件夹标签页栏](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.zh.md)** 页面在配置中配置的默认文件夹标签页位置。

*示例:* `Set TABPOSITION=above`
</td></tr><tr><td>
</td><td>
</td><td>

**below**</td><td>

当前文件窗口中的文件夹标签页将在文件列表下方显示。

*示例:* `Set TABPOSITION=below`
</td></tr><tr><td>
</td><td>
</td><td>

\*\*left \*\*</td><td>

文件夹标签页将显示在文件列表的左侧。

*示例:* `Set TABPOSITION=left`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

文件夹标签页将显示在文件列表的右侧。

*示例:* `Set TABPOSITION=right`
**together**

在双栏方式的文件窗口中，每个文件列表方式的文件夹标签页都将一起显示（例如，当设置为上方或下方时，水平双栏方式的文件窗口将会在两个文件列表方式之间一起显示两个文件夹标签页栏）。这将覆盖在配置的**[文件夹标签页栏](/Manual/preferences/preferences_categories/folder_tabs/folder_tab_bar.zh.md)**页面上配置的默认设置。

你可以独立使用此关键词或与上述位置参数之一结合使用，以同时更改两个设置。

*示例:* `Set TABPOSITION=above,together`

**apart**

在双栏方式的文件窗口中，文件夹标签页会彼此分开（例如，当设置为上方或下方时，水平双栏方式的文件窗口会在最上面的文件列表方式的上方以及最下面的文件列表方式的下方显示标签页）。

*示例:* `Set TABPOSITION=apart`

**normal**

在双栏方式的文件窗口中，文件夹标签页的位置将按配置的方式显示（例如，当设置为上方时，两个标签页栏都将显示在各自显示方式的上方）。

*示例:* `Set TABPOSITION=above,normal`

**reset**

将此文件窗口中的文件夹标签页位置重置为在配置中配置的默认值。

*示例:* `Set TABPOSITION=reset`

**save**

使此命令所做的更改永久生效（并将其应用到任何其他已打开的文件窗口）。

*示例:* `Set TABPOSITION=above,normal,save`

**TABWIDTH**

*\<size\>*

设置文件夹标签页栏的宽度（如果显示在文件列表方式的左侧或右侧）。（如果文件夹标签页栏位于文件列表方式的上方或下方，则所有 `Set TABWIDTH` 变体均对其无效。）

*示例:* `Set TABWIDTH=250`

你指定的宽度通常会按 DPI 进行缩放，但如果你希望使用绝对像素宽度且不缩放，则可以指定一个负数：

*示例:* `Set TABWIDTH=-300`

**auto**

自动调整文件夹标签页栏的大小以适应当前标签页的**标记**。（类似于双击标签页栏的分隔符。）

*示例:* `Set TABWIDTH=auto`

当 **auto** 和 **both** 结合使用时，两个标签页栏将自动调整大小以适应相同宽度，该宽度足以容纳两个标签页栏。

*示例:* `Set TABWIDTH=auto,both`

（如果你希望独立调整两侧的大小，请运行 `Set TABWIDTH=auto,left`，然后再运行 `Set TABWIDTH=auto,right`。）

**source**

指定你希望调整双栏方式窗口中*源*文件列表方式的标签页栏的大小。（这通常是隐式的，无需指定，但可以覆盖文件列表方式工具栏上的按钮所影响的文件列表方式。）

*示例:* `Set TABWIDTH=auto,source`

**dest**

指定你希望调整双栏方式窗口中*目标*文件列表方式的标签页栏的大小。

*示例:* `Set TABWIDTH=auto,dest`

**left**

指定你希望调整*左侧*（或*上方*）文件列表方式的标签页栏的大小。

*示例:* `Set TABWIDTH=auto,left`

**right**

指定你希望调整*右侧*（或*下方*）文件列表方式的标签页栏的大小。

*示例:* `Set TABWIDTH=auto,right`

**both**

指定你希望同时调整*左侧*和*右侧*（或*上方*和*下方*）文件列表方式的标签页栏的大小。

*示例:* `Set TABWIDTH=300,both`

将 **both** 和 **auto** 结合使用时，将将两侧的大小调整为任何一侧所需的最大值。有关详细信息，请参阅上面的 **auto**。

**thinnest**

在双栏方式窗口中，使两个标签页栏的宽度与最窄的标签页栏相同。

*示例:* `Set TABWIDTH=thinnest`

**widest**

在双栏方式窗口中，使两个标签页栏的宽度与最宽的标签页栏相同。

*示例:* `Set TABWIDTH=widest`

**THUMBNAILLABELS**

**on**

开启缩略图**标记**显示。这是一个全局设置 - 它修改配置的**[文件列表模式/缩略图](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)**页面上**显示**标记**选项的状态。

*示例:* `Set THUMBNAILLABELS=on`

**off**

关闭缩略图**标记**。

*示例:* `Set THUMBNAILLABELS=off`

**toggle**

切换缩略图**标记**开或关。

*示例:* `Set THUMBNAILLABELS=toggle`

**THUMBNAILRATINGS**

**on**

启用或禁用缩略图评分星级的覆盖。这是一个全局设置 - 它修改配置的**[文件列表模式/缩略图](/Manual/preferences/preferences_categories/file_display_modes/thumbnails_mode/README.zh.md)**页面上**覆盖评级**选项的状态。

*示例:* `Set THUMBNAILRATINGS=on`

**off**

关闭评级覆盖。

*示例:* `Set THUMBNAILRATINGS=off`

**toggle**

切换评级覆盖开或关。

*示例:* `Set THUMBNAILRATINGS=toggle`

**THUMBSTRETCH**

**reset**

禁用当前文件夹格式正在应用的缩略图拉伸模式的任何覆盖。然后会使用为当前文件列表模式在配置中定义的拉伸模式。

*示例:* `Set THUMBSTRETCH=reset`

*\<mode\>*

通过当前文件夹格式应用缩略图拉伸模式的覆盖。

有效模式：**FitReduce**、**FitSmooth**、**FitPixelated**、**FillCropSmooth** 和 **FillCropPixelated**。

在覆盖生效时，所有可以显示缩略图的文件列表模式都会受到影响，仅限于当前文件夹标签页。（文件夹缩略图中的子图像不会受到影响。）

*示例:* `Set THUMBSTRETCH=FitPixelated`

**TREE**

**on**

在活动的文件窗口中开启文件夹树。在双栏方式的文件窗口中，**[文件夹树/选项](/Manual/preferences/preferences_categories/folder_tree/options.zh.md)**页面上**双栏模式下打开第二个文件夹树**选项控制是否自动打开第二个文件夹树 - 如果该选项已关闭，你可以使用 **dual** 关键词强制打开第二个文件夹树。

*示例:* `Set TREE=on`

**off**

在活动的文件窗口中关闭文件夹树。

*示例:* `Set TREE=off`

**toggle**

在活动的文件窗口中切换文件夹树开或关。

*示例:* `Set TREE=toggle`

**left**

控制双栏方式文件窗口中的左侧（或上方）文件夹树。
**TREE**
| 选项 | 键 | 值 | 描述 |
|---|---|---|---|
| TREE | /K | **left,toggle** | 控制双栏文件窗口中的右侧（或底部）文件夹树。 |
| TREE | /K | **right** | 控制双栏文件窗口中的两个树。 |
| TREE | /K | **dual** | 控制双栏文件窗口中的两个树。 |
| TREE | /K | **source** | 控制“属于”源文件列表的文件夹树。 |
| TREE | /K | **dest** | 控制属于目标文件列表的文件夹树。 |
**TREELOCK**
| 选项 | 键 | 值 | 描述 |
|---|---|---|---|
| TREELOCK | /K | **on** | 为活动文件窗口（或存在两棵树时，为源文件列表）启用文件夹树锁定。这等同于单击文件夹树标题中的挂锁图标，即使在配置中关闭了树标题，也可以使用。当文件夹树被锁定时，它将不再自动更改选择以遵循当前源路径。 |
| TREELOCK | /K | **off** | 为活动文件窗口关闭文件夹树锁定。 |
| TREELOCK | /K | **toggle** | 切换文件夹树锁定功能的开启和关闭状态。 |
**TREESHOWPATHTOSEL**
| 选项 | 键 | 值 | 描述 |
|---|---|---|---|
| TREESHOWPATHTOSEL | /K | **on** | 启用文件夹树的**突出显示到选定文件夹的路径**选项。这是一个全局设置，因此会影响所有文件窗口。启用后，**[文件夹树 / 外观](/Manual/preferences/preferences_categories/folder_tree/appearance.zh.md)**配置页面上的其他选项将生效。 |
| TREESHOWPATHTOSEL | /K | **off** | 关闭树路径突出显示。 |
| TREESHOWPATHTOSEL | /K | **toggle** | 切换树路径突出显示功能的开启和关闭状态。 |
**UTILITY**
| 选项 | 键 | 值 | 描述 |
|---|---|---|---|
| UTILITY | /K | **find** | 在[查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)模式下显示[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。面板将以简单或高级状态打开，具体取决于上次关闭面板时使用哪种状态。 |
| UTILITY | /K | **findsimple** | 在[查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)（简单）模式下显示[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。 |
| UTILITY | /K | **findadvanced** | 在[查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md)（高级）模式下显示[实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)。 |
| UTILITY | /K | **sync** | 在[同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)模式下显示实用程序面板。 |
| UTILITY | /K | **dupe** | 在[重复文件查找器](/Manual/additional_functionality/duplicate_file_finder.zh.md)模式下显示实用程序面板。 |
| UTILITY | /K | **undo** | 显示实用程序面板，其中显示撤销列表（可以撤销的文件操作）。 |
| UTILITY | /K | **filelog** | 显示实用程序面板，其中显示[文件操作日志](/Manual/file_operations/tracking_and_undoing_file_operations.zh.md)。 |
| UTILITY | /K | **ftplog** | 显示实用程序面板，其中显示[FTP 日志](/Manual/ftp/ftp_log.zh.md)。 |
| UTILITY | /K | **scriptlog** | 显示实用程序面板，其中显示“脚本日志”页面。 |
| UTILITY | /K | **email** | 显示实用程序面板，其中显示传出电子邮件日志。 |
| UTILITY | /K | **on** | 在活动文件窗口中启用实用程序面板。 |
| UTILITY | /K | **off** | 关闭实用程序面板。 |
| UTILITY | /K | **toggle** | 在活动文件窗口中切换实用程序面板的开启和关闭状态。 |
| UTILITY | /K | **focus** | 如果实用程序面板处于打开状态，则为其赋予焦点。如果与**toggle**一起使用，则只有当实用程序面板具有焦点时，它才会切换为关闭状态。 |
| UTILITY | /K | **expand** | 如果实用程序面板处于收缩状态，则此参数与**toggle**结合使用会导致面板展开而不是关闭。 |
| UTILITY | /K | **noexpand** | 当与**toggle**（或其他使面板启用的关键字）一起使用时，**noexpand**可以防止实用程序面板展开，如果它之前保存在收缩状态中。也就是说，它将被启用但仍保持收缩状态。 |
**VIEW**
| 选项 | 键 | 值 | 描述 |
|---|---|---|---|
| VIEW | /K | *\<mode\>\[,\<mode\>\]* | 更改当前文件列表中的[视图](/Manual/basic_concepts/the_lister/view_modes.zh.md)。有效的模式关键字包括**largeicons**、**smallicons**、**list**、**detail**、**power**、**thumbnails**和**tile**。 |
| VIEW | /K | **cycle** | 循环浏览视图。如果单独使用，它将循环浏览所有可用的视图；否则，与适当的视图关键字结合使用，以创建在特定模式之间循环的命令。 |
</td></tr><tr><td>
VIEWERTOOLBAR</td><td>
/O</td><td>

*\<名称\>*</td><td>

此命令允许你改变用于 [Viewer 工具栏](/Manual/additional_functionality/viewing_images/viewer_keys_and_toolbar.zh.md) 的工具栏。如果你未指定名称，则会选择默认的 Viewer 工具栏。

*实例：* `Set VIEWERTOOLBAR "我的查看器工具栏"`
</td></tr><tr><td>
VIEWPANE</td><td>
/K</td><td>

**on**</td><td>

在当前活动的文件窗口中打开 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md)。

*实例：* `Set VIEWPANE=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在活动文件窗口中关闭查看器窗格。

*实例：* `Set VIEWPANE=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在活动文件窗口中打开或关闭查看器窗格。

*实例：* `Set VIEWPANE=toggle`
</td></tr><tr><td>
</td><td>
</td><td>

**horiz**</td><td>

当查看器窗格打开时，强制其采用水平布局。

*实例：* `Set VIEWPANE=toggle,horiz`
</td></tr><tr><td>
</td><td>
</td><td>

**vert**</td><td>

指定查看器窗格的垂直布局。

*实例：* `Set VIEWPANE=on,vert`
</td></tr><tr><td>
</td><td>
</td><td>

**togglelayout**</td><td>

在垂直和水平之间切换查看器窗格的布局。

*实例：* `Set VIEWPANE=togglelayout`
</td></tr><tr><td>
VIEWPANELOCK</td><td>
/K</td><td>

**on**</td><td>

在当前的文件窗口中打开 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 锁定。当查看器窗格锁定打开时，即便在文件窗口中改变了文件选择，它仍将继续显示当前图像。

*实例：* `Set VIEWPANELOCK=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

关闭查看器窗格锁定。

*实例：* `Set VIEWPANELOCK=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

打开或关闭查看器窗格锁定。

*实例：* `Set VIEWPANELOCK=toggle`
</td></tr><tr><td>
VIEWPANESHELLICONS</td><td>
/K</td><td>

**on**</td><td>

在 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 中启用 shell 图标。参见 **[配置/查看器/查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)/显示 shell 图标**。

*实例：* `Set VIEWPANESHELLICONS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在查看器窗格中禁用 shell 图标。

*实例：* `Set VIEWPANESHELLICONS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在查看器窗格中打开或关闭 shell 图标。

*实例：* `Set VIEWPANESHELLICONS=toggle`
</td></tr><tr><td>
VIEWPANESHELLTHUMBS</td><td>
/K</td><td>

**on**</td><td>

在 [查看器窗格](/Manual/basic_concepts/the_lister/viewer_pane.zh.md) 中启用 shell 缩略图。参见 **[配置/查看器/查看器窗格](/Manual/preferences/preferences_categories/viewer/viewer_pane.zh.md)/显示 shell 缩略图**。

*实例：* `Set VIEWPANESHELLTHUMBS=on`
</td></tr><tr><td>
</td><td>
</td><td>

**off**</td><td>

在查看器窗格中禁用 shell 缩略图。

*实例：* `Set VIEWPANESHELLTHUMBS=off`
</td></tr><tr><td>
</td><td>
</td><td>

**toggle**</td><td>

在查看器窗格中打开或关闭 shell 缩略图。

*实例：* `Set VIEWPANESHELLTHUMBS=toggle`
</td></tr><tr><td>
VIEWPANESIZE</td><td>
/K</td><td>

*\<大小\>\[,\<大小\>\]*</td><td>

调整活动文件窗口中查看器窗格的大小。大小以文件窗口的总大小百分比给出，并根据查看器窗格当前的布局进行相应维度应用（例如，当窗格为水平时，这会影响其高度）。

还可以指定两个单独的大小，并且此命令将在它们之间切换。

*实例：* `Set VIEWPANESIZE 25,50`
</td></tr></tbody>
</table>