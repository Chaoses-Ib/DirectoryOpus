# Toolbar

**Toolbar** 对象表示一个工具栏。 **Toolbar** 对象可以表示一个特定工具栏实例（在特定文件窗口中打开），也可以表示磁盘上的工具栏本身，该工具栏不必当前打开。

- 从 **[Toolbars](toolbars.zh.md)** 对象（反过来来自 **[DOpus](dopus.zh.md).Toolbars** 方法）检索时，该对象表示磁盘上的工具栏。您可以从其属性中找出它当前在何处使用。
- 从 **[Lister](lister.zh.md).toolbars** 属性检索时，它表示该特定文件窗口中工具栏的一个实例。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回工具栏的名称。
</td></tr><tr><td>
deftoolbar</td><td>

*布尔值*</td><td>

如果这是默认（出厂提供）工具栏，则返回 **True**，否则如果它是用户创建的，则返回 **False**。  
（旧脚本可能会使用“default”而不是“deftoolbar”；这已过时，因为它在 JScript 中不起作用，因为“default”是一个保留字。）
</td></tr><tr><td>
listers</td><td>

*集合:***[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象的集合，表示该工具栏当前打开的所有文件窗口。
</td></tr><tr><td>
docks</td><td>

*集合:***[Dock](dock.zh.md)**</td><td>

返回一个 **[Dock](dock.zh.md)** 对象的集合，表示该工具栏当前的所有浮动实例。
</td></tr><tr><td>
group</td><td>

*字符串*</td><td>

返回一个 *字符串*，指示该工具栏特定实例的组（位置）。返回的字符串将是 *顶部*、*底部*、*左侧*、*右侧*、*中心*、*fdright*、*fdbottom*、*tree* 之一。
</td></tr><tr><td>
line</td><td>

*整数*</td><td>
返回工具栏组中它所在的行的行号。例如，文件窗口顶部的第一个工具栏的 line 为 0。
</td></tr><tr><td>
pos</td><td>

*整数*</td><td>

返回工具栏行从左/顶部的像素位置。如果两个或多个工具栏具有相同的 **line** 值，则 **pos** 值决定它们显示的顺序。
</td></tr></tbody>
</table>