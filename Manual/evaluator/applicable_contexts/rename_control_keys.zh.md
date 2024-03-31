# 重命名控制键

[控制键](/Manual/preferences/preferences_categories/file_operations/renaming_files/control_keys.zh.md) 偏好设置页面允许您定义用于 [内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md) 的 <kbd>Ctrl</kbd> 键序列，此序列使用求值器来选择、取代或删除文本，或移动光标。

每当按其定义的键时，都会调用求值表达式。

在此求值上下文中，可使用以下变量：

<table>
<thead><tr><th>
变量</th><th>
类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
dir</td><td>

*bool*</td><td>

如果是目录，则为 **True**；如果是文件，则为 **false**。
</td></tr><tr><td>
exthidden</td><td>

*bool*</td><td>

如果文件名扩展名当前隐藏，则为 **True**。
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

如果是目录，则为 **True**；如果是文件，则为 **false**（与 *dir* 相同）。
</td></tr><tr><td>
file_name</td><td>

*string*</td><td>
文件的原名称。
</td></tr><tr><td>
name</td><td>

*str*</td><td>
文件的原名称。
</td></tr><tr><td>
nameext</td><td>

*str*</td><td>
文件的文件名原扩展名。
</td></tr><tr><td>
namestem</td><td>

*str*</td><td>
文件名原词干（即不带扩展名）。
</td></tr><tr><td>
path</td><td>

*path*</td><td>
文件所在路径（不包含文件名）。
</td></tr><tr><td>
selend</td><td>

*int*</td><td>
当前选择范围结束位置。
</td></tr><tr><td>
selstart</td><td>

*int*</td><td>
当前选择范围开始位置。
</td></tr><tr><td>
valext</td><td>

*str*</td><td>
编辑字段中当前值的文件名扩展名。
</td></tr><tr><td>
valstem</td><td>

*str*</td><td>
编辑字段中当前值的文件名词干。
</td></tr><tr><td>
valleft</td><td>

*str*</td><td>
当前选择范围左侧的当前值部分。
</td></tr><tr><td>
valright</td><td>

*str*</td><td>
当前选择范围右侧的当前值部分。
</td></tr><tr><td>
valsel</td><td>

*str*</td><td>
当前所选的当前值部分。
</td></tr><tr><td>
value</td><td>

*str*</td><td>
编辑字段中的当前值。
</td></tr></tbody>
</table>

求值器有一个特定于此上下文的函数 - `RestoreExt()`. 如果目前编辑字段中隐藏了文件名扩展名（即，如果 `exthidden` 是 **true**），则此表达式可以调用此函数来显示文件名扩展名。

求值表达式可以返回一个字符串来更新编辑字段中的值。

它还可通过更改 `selstart` 和 `selend` 变量的值来修改选择范围。

若要更新选择范围而不更改字符串的内容，只需返回 `true` 而非字符串。

如果它不想对值或选择进行任何更改，则它还可以返回 `false`。