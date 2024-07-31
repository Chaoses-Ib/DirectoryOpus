# 脚本事件

脚本文件中的事件是 Opus 在不同时间调用的函数。主要有三种类型的事件：

- 大多数事件都是 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 事件 - 它们在发生各种事件或活动时被调用。例如，**[OnBeforeFolderChange](/Manual/reference/scripting_reference/scripting_events/onbeforefolderchange.zh.md)** 事件会在标签页中的文件夹改变之前被调用。脚本加载项监听哪些事件完全由脚本定义 - 只要实现相应的方法，Opus 就会在适当的时候调用它。
- [脚本函数](/Manual/scripting/script_functions.zh.md) 通过它们的 **[OnClick](/Manual/reference/scripting_reference/scripting_events/onclick.zh.md)** 事件被调用 - 尽管实现此方法是可选的，因为在运行脚本按钮或热键时会执行整个脚本。实现 **OnClick** 的优势是可以传递给方法的 **[ClickData](scripting_objects/clickdata.zh.md)** 对象，它可以提供有关命令环境的有用信息。
- [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 提供一个事件，该事件会为每个被重命名的文件调用。出于历史原因，有许多不同的重命名事件可以被实现 - 最简单且推荐的是 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 事件。

除了遗留的重命名事件（**Rename_GetNewName** 和 **Rename_GetNewName2**）之外，所有事件函数都只有一个参数 - 一个特定于事件的数据对象，每次事件被调用时从 Opus 传递到脚本。每个对象都包含与事件相关的属性（有时还有方法）。使用单个对象的好处是，将来可以添加额外的属性，而无需更改事件本身的函数签名。