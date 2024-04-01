# TabGroup

**TabGroup** 对象表示[文件夹标签页组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)或可将其它标签页组组织其中的文件夹。可以从 **[TabGroups](tabgroups.zh.md)** 对象访问或枚举单独的 **TabGroup** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
closeexisting</td><td>

*bool*</td><td>

如果 **关闭现有的文件夹标签页时打开此组** 选项针对此组开启，则为 **True**。仅在 **folder** 属性为 **False** 时显示。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>

此标签页组的描述（如果有）。仅在 **folder** 属性为 **False** 时显示。
</td></tr><tr><td>
dual</td><td>

*bool*</td><td>

如果 **在双栏器文件窗口上的特定侧定义标签页** 选项针对此组开启，则为 **True**。仅在 **folder** 属性为 **False** 时显示。
</td></tr><tr><td>
folder</td><td>

*bool*</td><td>

如果此对象表示标签页组列表中的文件夹，则为 **True**；如果它是一个实际标签页组，则为 **False**。
</td></tr><tr><td>
hidden</td><td>

*bool*</td><td>

如果此标签页组或文件夹应当在列出标签页组的菜单中隐藏，则为 **True**。此组将始终在配置中可见。
</td></tr><tr><td>
lefttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回表示此组中在双栏器文件窗口的左侧/顶部打开的标签页的 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象。仅在 **folder** 属性为 **False** 且 **dual** 属性为 **True** 时显示。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
此组或文件夹的名称。
</td></tr><tr><td>
righttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回表示此组中在双栏器文件窗口的右侧/底部打开的标签页的 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象。仅在 **folder** 属性为 **False** 且 **dual** 属性为 **True** 时显示。
</td></tr><tr><td>
tabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回表示此组中标签页的 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象。仅在 **folder** 和 **dual** 属性均为 **False** 时显示。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddChildFolder</td><td>

*\<object:***TabGroup**\> 或 \<string:name\></td><td>

*object:**TabGroup***</td><td>

向此标签页组文件夹添加新的子文件夹。仅在 **folder** 属性为 **True** 时可用。您可以提供 **TabGroup** 对象（其本身的 folder属性设置为 **True**）或新文件夹的名称。如果操作成功，则会返回表示新文件夹的 **TabGroup** 对象。如果操作失败，则返回 **False**。
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***TabGroup**\> 或 \<string:name\></td><td>

*object:**TabGroup***</td><td>

向此标签页组文件夹添加新的标签页组。仅在 **folder** 属性为 **True** 时可用。您可以提供 **TabGroup** 对象或新组的名称。如果操作成功，则会返回表示新的标签页组的 **TabGroup** 对象。如果操作失败，则返回 **False**。
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***TabGroup**\></td><td>

*none*</td><td>
删除子项（文件夹或标签页组）。
</td></tr><tr><td>
Duplicate</td><td>

*none*</td><td>

*object:**TabGroup***</td><td>
返回此标签页组或文件夹的副本。副本返回时尚未添加到标签页列表中。
</td></tr><tr><td>
Link</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>  
*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>  
\<string:type\></td><td>

*none*</td><td>

在一个指定了特定左右标签页的标签页组中，此方法链接来自左侧的标签页和来自右侧的标签页。仅在 **dual** 属性设置为 **True** 时可用。您可以提供 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象或要链接的标签页的索引号。

可选 *type* 参数可设置为 **"slave"** 以指定标签页之间应当为从属关系。
</td></tr><tr><td>
Unlink</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>* *</td><td>

*none*</td><td>

将指定标签页从其配对标签页取消链接。仅在 **dual** 属性设置为 **True** 时可用。
</td></tr></tbody>
</table>