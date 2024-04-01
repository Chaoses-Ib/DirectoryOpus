# 脚本事件

事件是在脚本文件中 Opus 在不同时间调用的函数。事件有三个主要类别：

- 大多数事件是 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 事件 — 它们在发生各种事件或活动时被调用。例如，在标签页中更改文件夹之前调用 **[OnBeforeFolderChange](/Manual/reference/scripting_reference/scripting_events/onbeforefolderchange.zh.md)** 事件。脚本加载项侦听的事件完全由脚本定义 — 只需实现适当的方法，Opus 就会在适当的时间调用它。
- [脚本函数](/Manual/scripting/script_functions.zh.md) 通过其 **[OnClick](/Manual/reference/scripting_reference/scripting_events/onclick.zh.md)** 事件进行调用 - 虽然实现此方法是可选的，因为在运行脚本按钮或热键时会执行整个脚本来。实现 **OnClick** 的优点是传递给方法的 **[ClickData](scripting_objects/clickdata.zh.md)** 对象可提供有关该命令环境的有用信息。
- [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 提供了一个对要重命名的每个文件都调用的事件。由于历史原因，有多个可实现的重命名事件 — 最简单且推荐使用 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 事件。

除了过时的重命名事件（**Rename_GetNewName** 和 **Rename_GetNewName2**）之外，所有事件函数都有一个参数 — 一个特定于事件的数据对象，它在每次调用事件时从 Opus 传递给脚本。每个对象都包含与该事件相关的属性（有时还有方法）。使用单个对象的好处是将来可以在不更改事件本身的函数签名的情况下添加其它属性。