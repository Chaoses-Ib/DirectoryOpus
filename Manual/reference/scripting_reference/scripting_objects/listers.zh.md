# 列出对象

**文件窗口s** 对象是当前打开的所有 [文件窗口s](/Manual/basic_concepts/the_lister/README.zh.md) 的集合。可通过 **[DOpus](dopus.zh.md).listers** 属性获取。

**注意：**如果您正在寻找一个作为 **Dialog** 父对象的窗口，那么这可能不是正确的地方。脚本不应假设 **DOpus.listers(0)** 或 **DOpus.listers.lastactive** 是启动它们的 lister。大多数脚本事件都提供一个对象，该对象可以为您创建预配置的 **Dialog**，或者包含 **SourceTab** 属性或类似的可以执行相同操作的属性。在几乎所有情况下，您都应使用它们。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合：***[文件窗口](lister.zh.md)**</td><td>

允许您列举当前打开的文件窗口。

不要假设 **DOpus.listers(0)** 是启动您脚本的窗口。请参见页面顶部的说明。
</td></tr><tr><td>
lastactive</td><td>

*对象：***[文件窗口](lister.zh.md)**</td><td>

返回一个 **[文件窗口](lister.zh.md)** 对象，表示最近活动的文件窗口窗口。

不要假设 **DOpus.listers.lastactive** 是启动您脚本的窗口。请参见页面顶部的说明。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
ToFront</td><td>

\<lister\>  
\[\<lister\>...\]</td><td>

*无*</td><td>

将一个或多个文件窗口窗口移到最前面。此方法接受一个或多个参数；每个参数都可以是 **[文件窗口](lister.zh.md)** 对象或 **[Vector](vector.zh.md)** 的 **[lister](lister.zh.md)** 对象。最后一个窗口将置于顶部，其它所有窗口都将按相反顺序低于该窗口。
</td></tr><tr><td>
更新</td><td>

*无*</td><td>

*无*</td><td>

脚本首次访问 **DOpus.listers** 属性时，会对所有当前打开的文件窗口拍照。如果脚本随后自身打开或关闭文件窗口，此集合不会反映这些更改。要重新同步集合，请调用 **更新** 方法。
</td></tr></tbody>
</table>