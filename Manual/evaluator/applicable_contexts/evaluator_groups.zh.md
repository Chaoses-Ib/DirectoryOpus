# 求值员组

[求值员组](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.zh.md) 配置页面可以让你创建自己文件分组方案，它可以扩展或替换内置的分组规则。

当文件列表设置为使用某个分组方案进行分组时，它求值表达只调用一次文件或文件夹。在此求值上下文中，启用以下变量：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

<nobr>*column name*</nobr></td><td>

*变化的*</td><td>

**日期和时间**、 **名称和路径**、 **文件大小**和 \*\*通用 \*\*类目中的大多数[列关键字](/Manual/reference/metadata_keywords/keywords_for_columns.zh.md)在这个求值上下文中可用作为变量。请注意，只提供文件本身的内在基本信息-引用需要从文件提取的元数据的任何列不受支持。
</td></tr><tr><td>
file_name</td><td>

*字符串*</td><td>

返回正在为其运行表达式的文件的全名。这可能不同于**file**（作为一个列关键字），它返回*名称*列的值（例如，它可能隐藏了文件扩展名）。
</td></tr><tr><td>
is_dir</td><td>

*布尔值*</td><td>
如果表达式正在为文件夹运行，则为**真**，如果表达式正在为文件运行，则为**假**。
</td></tr><tr><td>
scheme</td><td>

*str*</td><td>
包含分组方案的名称。
</td></tr><tr><td>
value</td><td>

*变化的*</td><td>

这提供基于其进行分组的项目的价值。其类型取决于为分组选择的列。例如，如果按文件名进行分组，`value`将是*str*字符串类型并包含该项目的 filename。
</td></tr></tbody>
</table>

求值表达式的返回值定义将要放入项目的组。

- 如果组方案使用静态组，这应该是组索引（用作*int*），如配置中所示。
- 如果组方案使用动态组，这应该是组名称（用作*str*）。

对于动态组，还可以返回一个*值集合*，它定义了组名称和组顺序。这允许您拥有按除按字母顺序外的方式排序的动态组。

例如，假设您想要组“A”和“B”，但出于某些原因希望组“B”排在前面。

要将项目放在组“B”中，您可能会这样做：

    return [ name = "B"; order = 0; ];

而要将项目放在组“A”中，您可能会这样做：

    return [ name = "A"; order = 1; ];

组“B”将被排在组“A”之前，因为它的`order`值较低。`order`值可以是任何数据类型-例如，如果按日期列分组，则可以返回`value`作为按日期顺序对组进行排序的顺序。

（Opus 13.3.4及更高版本）还可以通过在返回的集合中包含`collapse`值来指示组是默认展开还是折叠。例如：

    return [ name = "C"; order = 2; collapse = true; ];