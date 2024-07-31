# TabGroupTabEntry

**TabGroupTabEntry** 对象表示单个 [文件夹标签页](/Manual/basic_concepts/the_lister/tabs/README.zh.md)。可以通过 **[TabGroupTabList](tabgrouptablist.zh.md)** 对象枚举标签页组中的文件夹标签页。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>

**描述**
</th></tr></thead><tbody><tr><td>
color</td><td>

*string*</td><td>
返回分配给此标签页的颜色（如果有）。
</td></tr><tr><td>
format</td><td>

object:**[Format](format.zh.md)**</td><td>
返回此标签页的文件夹格式。
</td></tr><tr><td>
linkid</td><td>

*int*</td><td>

返回此标签页的链接 ID（如果它链接到另一个标签页）。两个标签页将具有相同的链接 ID，但在其它情况下，该值毫无意义。使用 **[TabGroup](tabgroup.zh.md).Link** 和 **Unlink** 方法更改标签页链接。
</td></tr><tr><td>
linktype</td><td>

*string*</td><td>

如果此标签页链接为从属标签页，则返回字符串 **"slave"**。
</td></tr><tr><td>
locked</td><td>

*string*</td><td>

返回此标签页的锁定类型。有效值为 **"on"**、**"off"**、**"changes"** 和 **"reuse"**。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回此标签页的名称（如果分配了名称）。没有分配特定名称的标签页通常会显示路径的最后一个部分作为其名称。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>
返回此标签页打开时将加载的路径。
</td></tr></tbody>
</table>

  

<table>
<thead><tr><th>

**方法名称**</th><th>

**参数**</th><th>

**返回类型**</th><th>

**描述**
</th></tr></thead><tbody><tr><td>
Duplicate</td><td>

*无*</td><td>

*object:***TabGroupTabEntry**</td><td>
返回此标签页条目的副本。
</td></tr></tbody>
</table>

 