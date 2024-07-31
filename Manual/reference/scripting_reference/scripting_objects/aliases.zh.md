# Aliases

**Aliases** 对象包含所有已定义的 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md) 的集合。它可以通过 **[DOpus](dopus.zh.md).aliases** 方法获取。  

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Alias](alias.zh.md)**</td><td>

你可以枚举 **Aliases** 对象，或者通过名称查询单个别名的值（例如 *DOpus.Output(DOpus.aliases("desktop").path);*)
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<字符串:名称\>  
\<字符串:路径\></td><td>

*无*</td><td>

在系统中添加一个新的别名，使用指定的名称和路径。注意，在别名名称中 **不要** 包含开头的斜杠 (/)。
</td></tr><tr><td>
Delete</td><td>

\<字符串:名称\></td><td>

*无*</td><td>
删除指定的别名。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

更新此对象的当前状态。当第一次通过 **DOpus.aliases** 获取 **Aliases** 对象时，会获取该时刻别名的快照。如果通过对象进行更改，它会反映这些更改，但任何在脚本外部进行的更改（例如，通过 **Favorites ADD=alias** 命令）都不会被检测到，除非你调用 **Update** 方法。
</td></tr></tbody>
</table>