# Favorites

**Favorites** 对象包含所有定义的 [收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md) 的集合。它从 **[DOpus](dopus.zh.md).favorites** 属性中获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Favorite](favorite.zh.md)**</td><td>

您可以枚举 **Favorites** 对象以检索各个 **[Favorite](favorite.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法// 名称//</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<字符串:类型或名称\>  
\<字符串:路径\>  
\<整数:插入位置\> 或  
\<对象:**[Favorite](favorite.zh.md)**\></td><td>

*对象:***[Favorite](favorite.zh.md)**  
或 *对象:***Favorites**</td><td>

将一个新的收藏夹文件夹添加到收藏夹列表。请注意，您对列表所做的更改不会保存，直到您调用 **Save** 方法。

此方法执行三个不同的功能；它可以添加分隔符、子文件夹或收藏夹文件夹。

要添加分隔符，参数应为类型字符串 **sep**，可选地后跟插入位置（见下文）。

例如，`Favorites.Add("sep");`

您还可以通过将标题名称附加到 **sep:** 前缀来使分隔符成为标题（即在视觉上与其它项目不同的标签）。例如，`Favorites.Add("sep:Current Job");`

要添加文件夹，第一个参数应该是字符串 **folder:** 后跟文件夹的名称（作为单个参数），可选地后跟插入位置。

例如，`Favorites.Add("folder:Picture Locations");`

要添加一个新的收藏夹，第一个参数可以是收藏夹的名称（可选），第二个参数可以是要添加的文件夹的路径，或者可以省略名称，只提供路径。无论哪种情况，您都可以选择在最后一个参数中包含插入位置。

例如，

    Favorites.Add("myfave", "c:\folder\path");
    Favorites.Add("c:\folder\path");

在所有三种情况下，新项目默认情况下都添加到末尾，但您可以选择指定一个位置将项目插入到其它位置。例如，将 **0** 指定为插入位置将把它添加到列表的顶部。您可以提供一个数字或另一个 **[Favorite](favorite.zh.md)** 对象。

例如，`Favorites.Add("myfave", "c:\folder\path", 0);`

返回值是一个 **[Favorite](favorite.zh.md)** 或一个 **Favorites** 对象（取决于您是添加了子文件夹还是收藏夹文件夹）。
</td></tr><tr><td>
Delete</td><td>

\<对象:**[Favorite](favorite.zh.md)**\> 或  
\<对象:**Favorites**\></td><td>

*无*</td><td>

删除指定的收藏夹或子文件夹。请注意，您对列表所做的更改不会保存，直到您调用 **Save** 方法。
</td></tr><tr><td>
Find</td><td>

\<字符串:名称\>  
\<整数:索引\></td><td>

*对象:***Favorites**</td><td>

允许您找到当前级别下面一个或多个级别下的子文件夹。**name** 参数是子文件夹的名称或路径和名称（例如，"myfave"、"pictures/local" 等）。

可选的 **index** 参数允许您处理可能存在多个同名子文件夹的情况。**Favorites.Find("pictures", 1);** 将找到当前级别下面名为“pictures”的第二个子文件夹。
</td></tr><tr><td>
Save</td><td>

*无*</td><td>

*无*</td><td>

保存您对收藏夹列表所做的任何更改。在您调用此方法后，您所做的更改将反映在配置和Listers 中的收藏夹列表中。请注意，您只能对从 **[DOpus](dopus.zh.md).favorites** 属性获取的主“根”**Favorites** 对象调用此方法。
</td></tr><tr><td>
SetName</td><td>

\<字符串:名称\></td><td>

*无*</td><td>

更改此子文件夹的名称。请注意，您对列表所做的更改不会保存，直到您调用 **Save** 方法。您只能对引用子文件夹的 **Favorites** 对象调用此方法，而不能对主“根”文件夹调用此方法。
</td></tr></tbody>
</table>