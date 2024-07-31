# FolderEnum

**FolderEnum** 对象由 **[FSUtil](fsutil.zh.md).ReadDir** 方法返回。它允许您枚举（可选地递归地）文件夹的内容。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
complete</td><td>

*bool*</td><td>

**True** 表示枚举已完成，否则为 **False**。
</td></tr><tr><td>
error</td><td>

*int*</td><td>
如果发生错误，则将返回错误代码。成功时将返回 0。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Close</td><td>

*无*</td><td>

*无*</td><td>

关闭用于执行枚举的底层文件系统句柄。如果您想删除刚刚枚举的文件夹，可以调用此方法。调用此方法后，**complete** 属性将返回 **True**。
</td></tr><tr><td>
Next</td><td>

\<int:count\>  
\<**[Vector](vector.zh.md)**:vector\></td><td>

*object:***[Item](item.zh.md)** 

或

*object:***[Vector](vector.zh.md)**</td><td>

返回枚举中的下一个项目。

默认情况下（没有提供参数），将返回单个 **[Item](item.zh.md)** 对象。为了提高性能，您可以指定一个数字作为第一个参数，以便一次返回多个项目 - 在这种情况下，将返回一个 **[Vector](vector.zh.md)** 的 **[Item](item.zh.md)** 对象。指定 **-1** 以在一次调用中返回文件夹中的所有项目。

您还可以创建自己的 **[Vector](vector.zh.md)** 并将其作为第二个参数传递，以阻止 Opus 每次都创建新的 **[Vector](vector.zh.md)**。
</td></tr></tbody>
</table>