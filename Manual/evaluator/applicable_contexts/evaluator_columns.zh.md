# 求值器列

[求值器列](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.zh.md) 配置页面让您创建生成使用求值器的内容的列。

当有列显示时，求值表达式会针对每个文件或文件夹调用一次。在此求值上下文中，以下变量可用：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

<nobr>*列名称*</nobr></td><td>

*各异*</td><td>

所有 [列关键字](/Manual/reference/metadata_keywords/keywords_for_columns.zh.md) 都可作为此求值上下文中的变量。

请注意，一些关键字可能使用变量名称中无效的字符，如 `:` - 若要访问它们，请使用 [val](/Manual/reference/evaluator/val.zh.md) 函数。
</td></tr><tr><td>
file_name</td><td>

*字符串*</td><td>

返回求值列所属文件的完整名称。这可能与 **file** 不同，后者（作为列关键字）返回 *名称* 列的值（例如可能隐藏文件扩展名）。
</td></tr><tr><td>
is_dir</td><td>

*布尔值*</td><td>

如果为文件夹运行表达式，则**为真**，如果为文件运行表达式，则**为假**。
</td></tr><tr><td>
operation</td><td>

*字符串*</td><td>

如果列用于排序，则返回“排序”（如果您想控制排序顺序）。如果列用于分组，则返回“分组”（列定义中必须启用**自定义分组**选项）。否则返回“显示”。
</td></tr></tbody>
</table>

求值表达式的返回值将用作列的数据。根据 [列定义](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.zh.md) 中的 **类型** 设置，此值在列中的显示方式有所不同。

列可以通过在调用它们来建立排序顺序时返回不同的值来控制其排序顺序。例如，您的列可能希望按正确的日期顺序进行排序（例如，基于 `modifieddate` 列），但返回文本字符串以显示。在求值用于排序时，`operation` 值将设置为 ““排序””。

如果在列定义中启用了 **自定义分组** 选项，列还可以选择其默认组。`operation` 值将设置为 ““分组””，您应返回希望将项目置入其中的组的名称。