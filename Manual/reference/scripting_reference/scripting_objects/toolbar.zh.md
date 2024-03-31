# 工具栏

**Toolbar** 对象表示一个工具栏。**Toolbar** 对象既可以表示工具栏的具体实例（在一个特定的文件窗口中打开），也可以表示工具栏本身，它在磁盘上，但当前根本不需要打开。

- 从 **[Toolbars](toolbars.zh.md)** 对象（反过来从 **[DOpus](dopus.zh.md).Toolbars** 方法中获得）检索时，该对象表示磁盘上的工具栏。你可以从其属性中找到它当前正在使用的位置。
- 从 **[文件窗口](lister.zh.md).toolbars** 属性中检索时，表示该特定文件窗口中工具栏的实例。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回工具栏的名称。
</td></tr><tr><td>
deftoolbar</td><td>

*bool*</td><td>

如果这是默认（出厂提供的）工具栏，则返回 **True**；如果这是用户创建的，则返回 **False**。

（旧脚本可能使用“default”而不是“deftoolbar”；这已被弃用，因为它在 JScript 中不起作用，其中“default”是保留关键字。）
</td></tr><tr><td>
listers</td><td>

*集合:***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象集合，用于表示该工具栏当前在其中打开的所有文件窗口。
</td></tr><tr><td>
docks</td><td>

*集合:***[Dock](dock.zh.md)**</td><td>

返回一个 **[Dock](dock.zh.md)** 对象集合，用于表示该工具栏的任何当前浮动实例。
</td></tr><tr><td>
group</td><td>

*string*</td><td>

返回一个 *string*，其中指示此工具栏特定实例的组（位置）。已返回的字符串将是 *top*、*bottom*、*left*、*right*、*center*、*fdright*、*fdbottom*、*tree* 之一。
</td></tr><tr><td>
line</td><td>

*int*</td><td>
返回工具栏所在组中的行号。例如，文件窗口顶部的第一个工具栏的行号将为 0。
</td></tr><tr><td>
pos</td><td>

*int*</td><td>

从工具栏行的左/上方返回像素位置。如果有多个具有相同 **行** 号的工具栏，则 **pos** 值将确定其显示顺序。
</td></tr></tbody>
</table>