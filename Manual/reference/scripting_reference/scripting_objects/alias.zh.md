# 别名

**别名**对象代表定义的 [目录别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)。通过枚举或为 **[别名](aliases.zh.md)** 指定索引可以获取对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回别名的名称。
</td></tr><tr><td>
路径</td><td>

*对象:***[路径](path.zh.md)**</td><td>

以 **[路径](path.zh.md)** 对象形式返回别名的目标。
</td></tr><tr><td>
系统</td><td>

*bool*</td><td>

如果对象为系统定义的别名，则为 **True**，如果为用户定义，则为 **False**。
</td></tr></tbody>
</table>