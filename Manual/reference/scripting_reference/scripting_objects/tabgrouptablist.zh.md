# TabGroupTabList

**TabGroupTabList** 对象表示一个文件夹列表，这些文件夹将在父 [标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 打开时作为 [文件列表标签](/Manual/basic_concepts/the_lister/tabs/README.zh.md) 打开。您可以从 **[TabGroup](tabgroup.zh.md)** 对象的 **tabs**、**lefttabs** 和 **righttabs** 属性获取此对象。

**TabGroupsTabList** 对象是一个 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象的集合；您可以枚举它以发现每个文件夹标签。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
active</td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

返回一个 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象，表示此标签列表中的活动（默认）文件夹标签。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddTab</td><td>

*\<对象:***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*  
   
或

\<字符串:路径\>  
\<字符串:名称\></td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

将文件夹标签条目添加到此列表。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象，或新文件夹标签的 *路径* 和可选 *名称*。
</td></tr><tr><td>
DeleteTab</td><td>

*\<对象:***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*

或

\<整数:索引\></td><td>

*无*</td><td>

从此列表中删除文件夹标签条目。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象，或要删除的标签条目的索引。如果您将索引指定为 **-1**，则所有标签条目将被删除。
</td></tr><tr><td>
InsertTabAt</td><td>

*\<对象:***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*  
*\\* 或

\<字符串:路径\>  
\<字符串:名称\>

\<整数:索引\></td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

将文件夹标签条目插入到此列表中。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象，或新文件夹标签的 *路径* 和可选 *名称*。最后一个参数必须是指示所需插入位置的索引。
</td></tr><tr><td>
MoveTabTo</td><td>

*\<对象:***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>  
\<对象:***TabGroupTabList***\>*  
\<整数:索引\></td><td>

*无*</td><td>

将指定的标签条目移动到新位置，并可以选择移动到新的标签列表。如果第二个参数是 **TabGroupTabList** 对象，则标签条目将被移动到该列表。最后一个参数必须是指示所需插入位置的索引。
</td></tr></tbody>
</table>