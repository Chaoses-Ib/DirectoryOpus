# 过滤器和查找

你可以用几种不同方式在过滤器（包括查找工具）中使用求值器：

- 在 [过滤控件](/Manual/file_operations/filtered_operations/README.zh.md) 中，你可以定义一个 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md)，如果以 `=` 开头，这会使用求值器。
- 同样，不同的命令让你可以从命令行定义文本过滤器（例如 `查找 FILTERDEF`），如果以 `=` 开头，这些也会使用求值器。
- 如果 [搜索框](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md) 设置为使用 Opus 查找，你可以直接输入评测表达式，以 `=` 开头。
-（Opus 13.3.4 及以上版本）快速过滤器（通过 [过滤栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md) 或 [即时查找栏](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md)）可以直接运行求值器代码，如果使用求值器代码，它们还可以调用预定义的过滤器并向它们传递参数。

求值表达式可以使用以下三种模式之一调用：

- *过滤模式*：在此模式下，将会针对每个文件或文件夹调用一次求值表达式，以确定它们是否与过滤器匹配或被过滤器拒绝。
- *递归模式*：在此模式下，将调用表达式以确定操作是否应递归到该文件夹。
- *快速过滤模式*：针对每个文件或文件夹调用一次表达式以确定是否应在文件列表中显示它。

特殊变量 `子文件夹` 和 `快速过滤器` 告诉你表达式调用的是哪种模式。处理递归模式（当 `子文件夹` 为 true 时）是可选的 - 如果表达式从不查询 `子文件夹` 值的值，Opus 将简单地递归到所有子文件夹并且不会在该模式下再次调用你。

此上下文中求值器可用的变量有：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

\<nobr\>*列名*\</nobr\></td><td>

*varies*</td><td>

所有 [列关键词](/Manual/reference/metadata_keywords/keywords_for_columns.zh.md) 作为变量在此求值上下文中可用。

请注意，一些关键词可能使用变量名中无效的字符（如 `:`）- 要访问它们，请使用 [val](/Manual/reference/evaluator/val.zh.md) 函数。
</td></tr><tr><td>
文件名称</td><td>

*string*</td><td>

返回正在为其运行过滤器的文件的完整名称。这可能与 **文件** 不同，后者（作为列关键词）返回 *名称* 列的值（例如可能隐藏文件扩展名）。
</td></tr><tr><td>
过滤器参数</td><td>

*string*</td><td>

在 *快速过滤器模式* 中，这返回紧跟快速过滤器中的预定义过滤器名称的参数字符串的值。例如，快速过滤器 `?bigfiles:5` 将调用名为 "bigfiles" 的过滤器，并且（如果它是求值过滤器）以这个变量将值 "5" 传递给它。
</td></tr><tr><td>
是否为 dir</td><td>

*bool*</td><td>

如果表达式正在针对文件夹运行，返回 **true**，如果针对文件运行，返回 **false**。
</td></tr><tr><td>
opt_anyword</td><td>

*bool*</td><td>

在 *快速过滤器模式* 中，如果启用 "任意单词" 选项，返回 **true**。
</td></tr><tr><td>
opt_ignore</td><td>

*bool*</td><td>

在 *快速过滤器模式* 中，如果启用 "忽略变音符号" 选项，返回 **true**。
</td></tr><tr><td>
opt_partial</td><td>

*bool*</td><td>

在 *快速过滤器模式* 中，如果启用 "部分匹配" 选项，返回 **true**。
</td></tr><tr><td>
opt_regex</td><td>

*bool*</td><td>

在 *快速过滤器模式* 中，如果启用 "正则表达式" 选项，返回 **true**。
</td></tr><tr><td>
快速过滤器</td><td>

*bool*</td><td>

如果表达式被调用用于快速过滤器，则返回 **true**。
</td></tr><tr><td>
子文件夹</td><td>

*bool*</td><td>

如果表达式在 *递归模式* 中调用，则返回 **true**。
</td></tr></tbody>
</table>

求值表达式的返回值取决于它被调用的模式，尽管在所有情况下，它都必须返回一个 *bool*：

- 在 *过滤模式* 中，如果项目与过滤器匹配，则应返回 **true**，否则返回 **false**。
- 在 *递归模式* 中，如果 Opus 应递归到文件夹中，则应返回 **true**，否则应返回 **false** 以跳过它。
- 在 *快速过滤模式* 中，如果应显示项目，则应返回 **true**，如果应隐藏它，则返回 **false**。