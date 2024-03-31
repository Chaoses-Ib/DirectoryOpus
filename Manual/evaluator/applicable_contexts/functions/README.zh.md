# 按钮和功能

功能（例如那些您添加到工具栏按钮或热键的功能）可以通过多种方式使用求值器：

- [标签](/Manual/evaluator/applicable_contexts/functions/labels.zh.md) 可以使用 **@label** 修改符动态生成。
- [图标](/Manual/evaluator/applicable_contexts/functions/icons.zh.md) 可以使用 **@icon** 和相关修改符动态修改。
- 按钮 [工具提示](/Manual/evaluator/applicable_contexts/functions/tooltips.zh.md) 可以使用求值表达式生成。
- 按钮 [状态](/Manual/evaluator/applicable_contexts/functions/dynamic_state.zh.md)，例如启用/禁用、隐藏/显示和选中/未选中，可以使用求值器修改。
- 使用 **@if** 和 **@ifset** 在按钮中进行 [条件行为](/Manual/evaluator/applicable_contexts/functions/conditional_behavior.zh.md) 可以使用求值器执行。
- **[@eval](/Manual/evaluator/applicable_contexts/functions/evaluation_clauses.zh.md)** 修改符允许您运行求值器代码行作为函数的一部分。
- 求值器表达式的返回值可以使用 `{= ... =}` 代码[插入](/Manual/evaluator/applicable_contexts/functions/insertion_code.zh.md) 到命令行。
- 求值器可用于生成 [命令行](/Manual/evaluator/applicable_contexts/functions/commands.zh.md)，然后将其执行，就好像它是函数的一部分一样。