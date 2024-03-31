# Directory Opus 13 - 详细发布说明

# 求值器

- “求值器”是一种新类型的简单脚本。它允许执行条件逻辑和字符串操作，而这些操作在全脚本中不适用。
- 求值器不会替代旧脚本和命令。相反，它介于两者之间，并与它们结合使用。它不如成熟的脚本强大，但开销也更低，并且保证不会陷入循环中（因为它没有循环！），这允许在可能导致问题的调用正常脚本的地方使用求值器。
- 例如，求值器代码可用于使工具栏按钮根据某些条件改变其图标和标签。
- 支持条件逻辑、简单的布尔、数学和字符串操作以及从 Opus 获取各种信息的函数和变量。
- 工具 > Opus CLI/临时脚本编辑器现在具有一个求值器模式，可以让你使用它进行试验。
  - 开始输入或按下 Ctrl+空格键，获得列出求值器功能的弹出式建议。
  - 在弹出列表中，将光标悬停在函数上以了解详细信息。
- *命令:* `Set EVALUATORDISABLE=Toggle` 允许你在出错时禁用求值器。将在下一次重启时或通过再次运行命令重新启用它。
- 其他部分更详细地讨论求值器，因为它可以用于各种方式。

------------------------------------------------------------------------

下一篇：[文件窗口默认值](/Manual/release_history/opus13_detailed/lister_defaults.zh.md)