**TabGroupTabEntry** 对象表示单个 [文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)。标签页组中的文件夹标签页可以通过 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象进行枚举。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>

**说明**
</th></tr></thead><tbody><tr><td>
颜色</td><td>

*字符串*</td><td>
如果已分配该标签页，则返回颜色。
</td></tr><tr><td>
格式</td><td>

object:**[Format](format.zh.md)**</td><td>
返回此标签页的文件夹格式。
</td></tr><tr><td>
linkid</td><td>

*int*</td><td>

如果此标签页链接到另一个标签页，则返回该标签页的链接 ID。两个标签页将具有相同的链接 ID，但除此之外该值没有意义。使用 **[TabGroup](tabgroup.zh.md).Link** 和 **Unlink** 方法更改标签页链接。
</td></tr><tr><td>
linktype</td><td>

*字符串*</td><td>

如果此标签页作为从属标签页链接，则返回字符串 **“slave”**。
</td></tr><tr><td>
锁定</td><td>

*字符串*</td><td>

返回此标签页的锁定类型。有效值包括 **“on”**、**“off”**、**“changes”** 和 **“reuse”**。
</td></tr><tr><td>
名称</td><td>

*字符串*</td><td>
如果已分配名称，则返回此标签页的名称。未分配特定名称的标签页通常将路径的最后一个组件显示为其名称。
</td></tr><tr><td>
路径</td><td>

*object:***[Path](path.zh.md)**</td><td>
返回此标签页在打开时将加载的路径。
</td></tr></tbody>
</table>

 

<table>
<thead><tr><th>

**方法名称**</th><th>

**参数**</th><th>

**返回类型**</th><th>

**说明**
</th></tr></thead><tbody><tr><td>
Duplicate</td><td>

*无*</td><td>

*object:***TabGroupTabEntry**</td><td>
返回此标签页条目的副本。
</td></tr></tbody>
</table>

 