# Alias

**别名** 对象代表一个已定义的 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)。可以通过枚举或索引 **[Aliases](aliases.zh.md)** 对象来获取它。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
返回别名的名称。
</td></tr><tr><td>
path</td><td>

*对象:***[Path](path.zh.md)**</td><td>

将别名的目标作为 **[Path](path.zh.md)** 对象返回。
</td></tr><tr><td>
system</td><td>

*布尔值*</td><td>

如果对象是系统定义的别名，则为 **True**，如果是用户定义的别名，则为 **False**。
</td></tr></tbody>
</table>