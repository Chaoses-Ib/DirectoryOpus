**TabGroupTabList** 对象表示当父级 [标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 打开时作为 [文件列表标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md) 打开的文件夹列表。您可以从 **[TabGroup](tabgroup.zh.md)** 对象的 **tabs**、**lefttabs** 和 **righttabs** 属性中获取此对象。

**TabGroupsTabList** 对象是 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象的集合；您可以对它进行枚举，以发现每个文件夹标签。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
active</td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

返回一个 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象，表示此标签页列表中活动的（默认）文件夹标签页。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
AddTab</td><td>

*\<对象：***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*  
   
or

\<字符串：路径\>  
\<字符串：名称\></td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

将文件夹标签页条目添加到此列表。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象或新文件夹标签页的 *路径* 和可选 *名称*。
</td></tr><tr><td>
DeleteTab</td><td>

*\<对象：***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*

or

\<整数：索引\></td><td>

*无*</td><td>

从该列表中删除文件夹标签页条目。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象或要删除的标签页条目的索引。如果您将索引指定为 **-1**，则所有标签页条目都将被删除。
</td></tr><tr><td>
InsertTabAt</td><td>

*\<对象：***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>*  
*\\* or

\<字符串：路径\>  
\<字符串：名称\>

\<整数：索引\></td><td>

对象：**[TabGroupTabEntry](tabgrouptabentry.zh.md)**</td><td>

将文件夹标签页条目插入此列表。您可以提供一个  
**[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象或新文件夹标签页的 *路径* 和可选 *名称*。最后一个参数必须是表示所需插入位置的索引。
</td></tr><tr><td>
MoveTabTo</td><td>

*\<对象：***[TabGroupTabEntry](tabgrouptabentry.zh.md)***\>  
\<对象：***TabGroupTabList***\>*  
\<整数：索引\></td><td>

*无*</td><td>

将指定的标签页条目移动到新位置（还可以选择移动到新标签页列表）。如果第二个参数是 **TabGroupTabList** 对象，那么标签页条目将移动到该列表。最后一个参数必须是表示所需插入位置的索引。
</td></tr></tbody>
</table>