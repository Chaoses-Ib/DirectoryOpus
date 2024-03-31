# 别名

**别名**对象包含所有已定义 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md) 的集合。它从 **[DOpus](dopus.zh.md).aliases** 方法中检索。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<缺省值\>*</td><td>

*集合:***[别名](alias.zh.md)**</td><td>

您可以枚举 **别名**对象，或按名称查询单个别名的值（例如 *DOpus.Output(DOpus.aliases("desktop").path);*)
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>
**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
添加</td><td>

\<string:名称\>  
\<string:路径\></td><td>

*无*</td><td>

使用指定名称和路径向系统添加一个新别名。请注意您**不**应在别名名称中提供前导斜杠 (/)。
</td></tr><tr><td>
删除</td><td>

\<string:名称\></td><td>

*无*</td><td>
删除指定的别名。
</td></tr><tr><td>
更新</td><td>

*无*</td><td>

*无*</td><td>

更新此对象的**状态**。当 **别名** 对象首次通过 **DOpus.aliases** 检索时，将对当时的别名进行快照。如果您通过该对象进行更改，它将反映这些更改，但除非您调用 **更新** 方法，否则不会检测到脚本外部进行的任何更改（例如通过 **收藏夹 ADD=别名** 命令）。
</td></tr></tbody>
</table>