# 收藏**

**收藏**对象表示[收藏夹文件夹](/Manual/basic_concepts/the_lister/navigation/favorites.zh.md)。它通过枚举或编入[收藏夹](favorites.zh.md)对象而检索。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回收藏夹文件夹或子文件夹的名称。
</td></tr><tr><td>
文件夹</td><td>

*bool*</td><td>

如果是子文件夹，则返回 **True**，如果是收藏夹文件夹或分隔符，则返回 **False**。

如果此对象是子文件夹，它也像 **[收藏夹](favorites.zh.md)** 对象一样表现得像 **收藏夹** 对象，并且可以枚举并添加和移除其中的元素。
</td></tr><tr><td>
分隔符</td><td>

*bool*</td><td>

如果是分隔符，则返回 **True**。
</td></tr><tr><td>
路径</td><td>

*object:***[路径](path.zh.md)**</td><td>

返回此收藏夹文件夹引用的路径为 **[路径](path.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法//名称//</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
SetHeading</td><td>

\<string:标题\></td><td>

*无*</td><td>

如果这是分隔符（即 **separator** 属性返回 **True**），则允许您将分隔符设为标题或更改标题文本。

请注意，在调用 **[收藏夹](favorites.zh.md).Save** 方法之前，您对列表所做的更改不会被保存。
</td></tr><tr><td>
SetName</td><td>

\<string:名称\></td><td>

*无*</td><td>

更改此收藏夹文件夹的名称。请注意，在调用 **[收藏夹](favorites.zh.md).Save** 方法之前，您对列表所做的更改不会被保存。
</td></tr><tr><td>
SetPath</td><td>

\<string:路径\> 或  
\<object:**[路径](path.zh.md)**\></td><td>

*无*</td><td>

更改此收藏夹文件夹引用的路径。请注意，在调用 **[收藏夹](favorites.zh.md).Save** 方法之前，您对列表所做的更改不会被保存。
</td></tr></tbody>
</table>