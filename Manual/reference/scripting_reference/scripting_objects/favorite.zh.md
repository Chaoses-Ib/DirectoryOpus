# Favorite

一个 **Favorite** 对象代表一个 [收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md)。可以通过枚举或索引 [Favorites](favorites.zh.md) 对象来获取。

<table>
<thead><tr><th>
属性名</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回收藏夹文件夹或子文件夹的名称。
</td></tr><tr><td>
文件夹</td><td>

*布尔值*</td><td>

如果这是一个子文件夹，则返回 **True**，如果它是一个收藏夹文件夹或分隔符，则返回 **False**。

如果此对象是一个子文件夹，它也像一个 **[Favorites](favorites.zh.md)** 对象和一个 **Favorite** 对象一样，可以被枚举，并可以添加和删除元素。
</td></tr><tr><td>
分隔符</td><td>

*布尔值*</td><td>

如果这是一个分隔符，则返回 **True**。
</td></tr><tr><td>
路径</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回此收藏夹文件夹所指向的路径，作为一个 **[Path](path.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法// 名称//</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
设置标题</td><td>

\<字符串:标题\></td><td>

*无*</td><td>

如果这是一个分隔符（即 **分隔符** 属性返回 **True**），这允许您将分隔符变为标题，或更改标题文本。

请注意，您对列表所做的更改不会被保存，直到您调用 **[Favorites](favorites.zh.md).保存** 方法。
</td></tr><tr><td>
设置名称</td><td>

\<字符串:名称\></td><td>

*无*</td><td>

更改此收藏夹文件夹的名称。请注意，您对列表所做的更改不会被保存，直到您调用 **[Favorites](favorites.zh.md).保存** 方法。
</td></tr><tr><td>
设置路径</td><td>

\<字符串:路径\> 或  
\<对象:**[Path](path.zh.md)**\></td><td>

*无*</td><td>

更改此收藏夹文件夹所指向的路径。请注意，您对列表所做的更改不会被保存，直到您调用 **[Favorites](favorites.zh.md).保存** 方法。
</td></tr></tbody>
</table>