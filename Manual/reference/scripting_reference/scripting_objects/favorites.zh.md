# 收藏夹

**收藏夹**对象保存所有已定义的 [收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md) 的集合。它从 **[DOpus](dopus.zh.md).favorites** 属性中检索。

<table>
<thead><tr><th>
属性名</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[收藏夹](favorite.zh.md)**</td><td>

你可以枚举 **收藏夹**对象以检索各个 **[收藏夹](favorite.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法// 名称//</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
添加</td><td>

\<字符串:typeOrName\>  
\<字符串:path\>  
\<int:insertpos\> 或  
\<对象:**[收藏夹](favorite.zh.md)**\></td><td>

*对象:***[收藏夹](favorite.zh.md)**  
或 *对象:***收藏夹**</td><td>

将新的收藏夹文件夹添加到收藏夹列表。请注意，在你调用 **保存** 方法之前，你对列表所做的更改不会被保存。

此方法执行三个单独的功能；它可以添加分隔符、子文件夹或收藏夹文件夹。 

要添加分隔符，参数应为类型字符串 **sep**，后跟可选的插入位置（见下文）。

例如，`Favorites.Add("sep");`

还可以通过将标题名称附加到 **sep:** 前缀来使分隔符成为标题（即与其他项目在视觉上有所不同的标签）。例如，`Favorites.Add("sep:Current Job");`

要添加文件夹，第一个参数应该是字符串 **folder:**，后跟文件夹的名称（作为单个参数），后跟可选的插入位置。

例如，`Favorites.Add("folder:Picture Locations");`

要添加新的收藏夹，第一个参数可以是收藏夹的名称（可选），第二个参数可以是所添加文件夹的 路径，或可以省略名称，而只提供路径。在任何一种情况下，你都可以选择将插入位置作为最后一个参数包含在内。

例如，

    Favorites.Add("myfave", "c:\folder\path");
    Favorites.Add("c:\folder\path");

在这三种情况下，默认情况下，新项目都会被添加到末尾，但你可以选择指定一个位置将该项目插入到其他位置。例如，为插入位置指定 **0** 将它添加到列表的顶部。你可以提供一个数字或另一个 **[收藏夹](favorite.zh.md)**对象。

例如，`Favorites.Add("myfave", "c:\folder\path", 0);`

返回值是 **[收藏夹](favorite.zh.md)**或 **收藏夹** 对象（取决于你添加的是子文件夹还是收藏夹文件夹）。
</td></tr><tr><td>
删除</td><td>

\<对象:**[收藏夹](favorite.zh.md)**\> 或  
\<对象:**收藏夹**\></td><td>

*无*</td><td>

删除指定的收藏夹或子文件夹。请注意，在你调用 **保存** 方法之前，你对列表所做的更改不会被保存。
</td></tr><tr><td>
查找</td><td>

\<字符串:name\>  
\<int:index\></td><td>

*对象:***收藏夹**</td><td>

让你找到当前一个级别以下一个或多个级别的子文件夹。**名称**参数是所要查找的子文件夹的名称或路径和名称（例如 "myfave"、"pictures/local" 等）。

可选的 **index** 参数让你能够处理当有多个子文件夹具有相同名称时的情形。**Favorites.Find("pictures", 1);** 将找到当前级别以下名为 "pictures" 的第二个子文件夹。
</td></tr><tr><td>
保存</td><td>

*无*</td><td>

*无*</td><td>

保存你对收藏夹列表所做的任何更改。一旦你调用此方法，你所做的更改将反映在配置中，以及文件窗口中的收藏夹列表中。请注意，你只能在从 **[DOpus](dopus.zh.md).favorites** 属性获取的主 "根" **收藏夹** 对象上调用此方法
</td></tr><tr><td>
设置名称</td><td>

\<字符串:name\></td><td>

*无*</td><td>

更改此子文件夹的名称。请注意，在你调用 **保存** 方法之前，你对列表所做的更改不会被保存。你只能对引用子文件夹（而不是主 "根" 文件夹）的 **收藏夹** 对象调用此方法。
</td></tr></tbody>
</table>