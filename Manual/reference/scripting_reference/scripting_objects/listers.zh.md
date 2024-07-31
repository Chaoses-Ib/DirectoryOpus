# Listers

**Listers** 对象是一个包含所有当前打开的 [Listers](/Manual/basic_concepts/the_lister/README.zh.md) 的集合。可以通过 **[DOpus](dopus.zh.md).listers** 属性获取它。

**注意：**如果您正在寻找一个窗口用作 **Dialog** 的父级，您可能找错了地方。脚本不应该假设 **DOpus.listers(0)** 或 **DOpus.listers.lastactive** 是启动它们的 lister。大多数脚本事件会为您提供一个对象，它可以为您创建一个预配置的 **Dialog**，或者包含一个 **SourceTab** 属性或类似的属性，可以执行相同操作。在几乎所有情况下，您应该使用它们。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Lister](lister.zh.md)**</td><td>

允许您枚举当前打开的文件窗口。

不要假设 **DOpus.listers(0)** 是启动您的脚本的窗口。请参阅页面顶部的说明。
</td></tr><tr><td>
lastactive</td><td>

*对象:***[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象，表示最近激活的文件窗口窗口。

不要假设 **DOpus.listers.lastactive** 是启动您的脚本的窗口。请参阅页面顶部的说明。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
ToFront</td><td>

\<lister\>  
\[\<lister\>...\]</td><td>

*无*</td><td>

将一个或多个文件窗口窗口移到最前面。此方法接受一个或多个参数；每个参数可以是 **[Lister](lister.zh.md)** 对象或 **[Vector](vector.zh.md)** 的 **[lister](lister.zh.md)** 对象。最后一个窗口将放在最上面，所有其它窗口将按相反顺序排列在其下方。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

脚本第一次访问 **DOpus.listers** 属性时，将拍摄所有当前打开的文件窗口的快照。如果脚本随后自己打开或关闭文件窗口，这些更改将不会反映在此集合中。要重新同步集合，请调用 **Update** 方法。
</td></tr></tbody>
</table>