# TabGroup

**TabGroup** 对象表示一个 [文件夹标签页组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md) 或一个可以组织其它标签页组的文件夹。可以从 **[TabGroups](tabgroups.zh.md)** 对象访问或枚举各个 **TabGroup** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
closeexisting</td><td>

*bool*</td><td>

**True** 如果此组已启用 **打开此组时关闭现有文件夹标签页** 选项。仅在 **folder** 属性为 **False** 时存在。
</td></tr><tr><td>
desc</td><td>

*string*</td><td>

此标签页组的描述（如果有）。仅在 **folder** 属性为 **False** 时存在。
</td></tr><tr><td>
dual</td><td>

*bool*</td><td>

**True** 如果此组已启用 **在双栏文件窗口上的特定侧定义标签页** 选项。仅在 **folder** 属性为 **False** 时存在。
</td></tr><tr><td>
folder</td><td>

*bool*</td><td>

**True** 如果此对象表示标签页组列表中的文件夹，**False** 如果它是实际的标签页组。
</td></tr><tr><td>
hidden</td><td>

*bool*</td><td>

**True** 如果此标签页组或文件夹应从列出标签页组的菜单中隐藏。该组在配置中始终可见。
</td></tr><tr><td>
lefttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回一个 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象，表示此组中在双栏文件窗口的左侧/顶部打开的标签页。仅在 **folder** 属性为 **False** 且 **dual** 属性为 **True** 时存在。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
此组或文件夹的名称。
</td></tr><tr><td>
righttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回一个 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象，表示此组中在双栏文件窗口的右侧/底部打开的标签页。仅在 **folder** 属性为 **False** 且 **dual** 属性为 **True** 时存在。
</td></tr><tr><td>
tabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.zh.md)**</td><td>

返回一个 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象，表示此组中的标签页。仅在 **folder** 和 **dual** 属性均为 **False** 时存在。
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

将新的子文件夹添加到此标签页组文件夹。仅在 **folder** 属性为 **True** 时可用。您可以提供一个 **TabGroup** 对象（其自身的 folder 属性设置为 **True**）或新文件夹的名称。如果操作成功，则返回一个 **TabGroup** 对象，该对象表示新文件夹。如果操作失败，则返回 **False**。
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***TabGroup**\> 或 \<string:name\></td><td>

*object:**TabGroup***</td><td>

将新的标签页组添加到此标签页组文件夹。仅在 **folder** 属性为 **True** 时可用。您可以提供一个 **TabGroup** 对象或新组的名称。如果操作成功，则返回一个 **TabGroup** 对象，该对象表示新的标签页组。如果操作失败，则返回 **False**。
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***TabGroup**\></td><td>

*none*</td><td>
删除子项（文件夹或标签页组）。
</td></tr><tr><td>
Duplicate</td><td>

*none*</td><td>

*object:**TabGroup***</td><td>
返回此标签页组或文件夹的副本。返回时，副本尚未添加到标签页列表中。
</td></tr><tr><td>
Link</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>  
*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>  
\<string:type\></td><td>

*none*</td><td>

在具有特定左侧和右侧标签页的标签页组中，此方法将左侧标签页和右侧标签页链接在一起。仅在 **dual** 属性设置为 **True** 时可用。您可以提供 **[TabGroupTabEntry](tabgrouptabentry.zh.md)** 对象或要链接的标签页的索引号。

可选的 *type* 参数可以设置为 **"slave"**，以指定标签页应相互从属。
</td></tr><tr><td>
Unlink</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.zh.md)**\>* *</td><td>

*none*</td><td>

取消链接指定标签页与其伙伴的链接。仅在 **dual** 属性设置为 **True** 时可用。
</td></tr></tbody>
</table>