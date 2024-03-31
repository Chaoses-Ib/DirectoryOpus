**求值器的适用情况**

在 Opus 中，可以在许多不同的地方使用求值器。大多数是可选的——求值器可用于增强或扩展更简单的系统——但某些功能需要使用它。

- **[求值器列](/Manual/evaluator/applicable_contexts/evaluator_columns.zh.md)**——定义文件信息列，使用求值器生成其内容。
- **[求值器组](/Manual/evaluator/applicable_contexts/evaluator_groups.zh.md)**——为[文件组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 配置自定义规则，以扩展或替换内置的规则。
- **[过滤器和查找](/Manual/evaluator/applicable_contexts/filters_and_find.zh.md)**——[过滤的文件操作](/Manual/file_operations/filtered_operations/README.zh.md) 和 [高级查找工具](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md) 都允许您编写求值表达式，用于选择要进行操作的文件或在搜索中返回文件。当设置为使用 Opus Find 时，您还可以在 [搜索字段](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md) 中直接输入求值代码。
- **[文件信息提示](/Manual/evaluator/applicable_contexts/file_info_tips.zh.md)**——插入由求值器生成 [文件类型信息提示](/Manual/file_types/filetype_editor/info_tip.zh.md) 中的文本。
- **[函数](/Manual/evaluator/applicable_contexts/functions/README.zh.md)**——许多 [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) 可以使用求值器，标签和图标可以动态更改，命令行可以使用求值器插入文本（甚至可以完全生成）。
- **[重命名](/Manual/evaluator/applicable_contexts/rename.zh.md)**——将求值器的文本插入新的文件名中。
- **[重命名控制键](/Manual/evaluator/applicable_contexts/rename_control_keys.zh.md)**——为 [内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md) 定义 <kbd>Ctrl</kbd> 键序列，使用求值器选择、替换或删除文本，或移动光标。
- **[状态栏](/Manual/evaluator/applicable_contexts/status_bar.zh.md)**——在状态栏中插入由求值器生成的文本。
- **[列上下文菜单](/Manual/evaluator/applicable_contexts/column_context_menus.zh.md)**——求值器对列标题上下文菜单有专门的支持，可以根据单击哪个列来创建动态菜单。
- **[标签页上下文菜单](/Manual/evaluator/applicable_contexts/tab_context_menus.zh.md)**——求值器对文件夹标签页上下文菜单有专门的支持，可以根据单击哪个标签页或打开了多少标签页来创建动态菜单。