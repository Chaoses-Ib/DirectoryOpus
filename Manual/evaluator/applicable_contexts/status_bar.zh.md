# 状态栏

您可以在 [状态栏](/Manual/preferences/preferences_categories/file_displays/status_bar.zh.md) 中使用求值器插入求值返回的文本。

使用 `{= ... =}` 代码插入一个求值表达式。在 `{=` 和 `=}` 标记之间的表达式可以跨越多行（如果需要）。表达式返回的值将插入到状态栏中。

在此求值上下文中，以下变量可用：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

<nobr>*状态代码*</nobr></td><td>

*变化*</td><td>

所有 [状态栏代码](/Manual/reference/status_bar_codes/README.zh.md) 都可以在此求值上下文中用作变量（生成图像或图形的代码除外）。

请注意，某些关键字可能使用诸如 `:` 之类的字符，而这些字符在变量名称中无效 - 要访问它们，请使用 [val](/Manual/reference/evaluator/val.zh.md) 函数。
</td></tr><tr><td>
路径</td><td>

*路径*</td><td>
返回状态栏正在显示其信息的当前路径。
</td></tr></tbody>
</table>

返回值应为一个 *str*，将被插入到状态栏中。