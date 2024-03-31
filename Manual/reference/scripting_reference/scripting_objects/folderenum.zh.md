**FolderEnum** 对象由 **[FSUtil](fsutil.zh.md).ReadDir** 方法返回。它让你枚举文件夹的项（可选递归）。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
complete</td><td>

*bool*</td><td>

枚举完成时为 **True**，否则为 **False**。
</td></tr><tr><td>
error</td><td>

*int*</td><td>
如果发生错误，则返回错误代码。成功时返回 0。
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

*none*</td><td>

*none*</td><td>

关闭用于执行枚举的底层文件系统句柄。如果你想删除刚才枚举的文件夹，可以使用这个方法。调用此方法后，**complete** 属性将返回 **True**。
</td></tr><tr><td>
Next</td><td>

\<int:count\>  
\<**[Vector](vector.zh.md)**:vector\></td><td>

*object:***[Item](item.zh.md)** 

或

*object:***[Vector](vector.zh.md)**</td><td>

返回枚举中的下一个项。

默认情况下（不提供任何参数），返回一个 **[Item](item.zh.md)** 对象。为了提高性能，你可以指定一个数字作为第一个参数，以便一次返回多个项 - 在这种情况下，返回一个 **[Item](item.zh.md)** 对象的 **[Vector](vector.zh.md)**。指定 **-1** 以在一次调用中返回文件夹中的所有项。

你还可以创建你自己的 **[Vector](vector.zh.md)**，并将其作为第二个参数传递，以使 Opus 停止每次创建一个新的 **[Vector](vector.zh.md)**。
</td></tr></tbody>
</table>