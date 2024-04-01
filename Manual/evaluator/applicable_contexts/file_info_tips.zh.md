# 文件信息提示和平铺

可以在 [文件信息提示](/Manual/file_types/filetype_editor/info_tip.zh.md) 和 [平铺模式](/Manual/file_types/filetype_editor/tiles_mode.zh.md) 的定义中使用求值器，以插入求值返回的文本。

使用 `{= ... =}` 代码插入求值表达式。根据需要， `{=` 和 `=}` 标记之间的表达式可以跨越多行。该表达式的返回值将插入到信息提示或平铺中。

你还可以使用求值器实现隐藏部分——使用 `{!= ... =}` 使用求值表达式打开隐藏部分。如果表达式返回 **false**，则隐藏部分内的所有内容都将被隐藏。像往常一样用 `{!}` 关闭隐藏部分。

在此求值上下文中，以下变量可用于：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

<nobr>*列名*</nobr></td><td>

*不同*</td><td>

所有 [列关键字](/Manual/reference/metadata_keywords/keywords_for_columns.zh.md) 作为变量在此求值上下文中可用。

注意，某些关键字可能使用变量名中无效的字符，例如 `:`——要访问它们，需使用 [val](/Manual/reference/evaluator/val.zh.md) 函数。

此外，**foldersize**、**foldercontents** 和 **infotip** 关键字也受支持。
</td></tr><tr><td>
file_name</td><td>

*字符串*</td><td>

返回正在为其运行表达式的文件的完整名称。这可能不同于 **file**（作为列关键字）返回 *名称* 列的值（例如，可能隐藏文件扩展名）。
</td></tr><tr><td>
is_dir</td><td>

*布尔值*</td><td>

如果表达式是为文件夹运行的，则为 **True**；如果表达式是为文件运行的，则为 **false**。
</td></tr></tbody>
</table>

返回值对于插入应为 *str*，对于隐藏部分应为 *bool*。

- 如果表达式是插入（使用 `{= ... =}` 代码），则求值表达式返回的值将插入到代码出现处的信息提示或平铺中。
- 如果表达式用于隐藏部分（使用 `{!= ... =}` 代码），则应返回 **true** 以显示隐藏部分的内容，或返回 **false** 以隐藏它们。