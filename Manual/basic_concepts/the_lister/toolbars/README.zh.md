# 工具栏

工具栏是与 Opus 交互的主要方式之一，可让您对文件执行操作并启动程序。关于 Opus 工具栏的一些重要要点：

- Opus 中的所有工具栏和菜单都可通过 [自定义](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md) 函数进行 [配置](/Manual/customize/README.zh.md)。
- 在 Opus 中，工具栏和菜单是同一个东西。
- 工具栏按钮可以运行 [内部命令](/Manual/reference/command_reference/internal_commands/README.zh.md)、[脚本](/Manual/scripting/README.zh.md) 并启动 [外部程序](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)，并且可以自动传递所选文件和其它信息。
- 工具栏按钮可以具有关联的 *热键*，让您可以通过键盘而不是鼠标启动该功能。您可以从自定义对话框中选择始终启用工具栏的热键 - 即使工具栏未当前打开，其热键仍然有效。
- 工具栏要么显示在文件窗口中，要么 [浮动](/Manual/additional_functionality/floating_toolbars/README.zh.md) 在桌面上，或者同时显示。您甚至可以在需要时浮动相同工具栏的多个副本。
- 工具栏按钮可以包含文本 **标记**、图形图像或同时包含两者。
- 可以将工具栏设置为在更改到特定显示模式或访问特定文件夹时 [自动出现](/Manual/basic_concepts/the_lister/toolbars/dynamic_toolbars.zh.md)。
- 可以将多个工具栏保存到 [工具栏集中](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.zh.md)，然后可以在以后重新加载。
- 可以使用 [文件窗口布局](layouts/README.zh.md) 系统保存带有其自己的工具栏的特定文件窗口。
- 文件窗口默认显示的工具栏存储在被称为 *默认工具栏集* 中 - 只要文件窗口没有在它所来自的布局中定义其自己的工具栏集，就会使用此工具栏集。使用 **设置/工具栏/设置为默认工具栏集** 命令更新默认工具栏集，如果您想要更改默认使用的工具栏。  
  \* Opus 随五个 [默认工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/README.zh.md) 一起提供 - 您能编辑它们，但是不能删除它们。 您可以创建任意多您想要的其它工具栏。

您可以使用 [自定义](/Manual/customize/README.zh.md) 中的列表、通过 **设置/工具栏** 菜单或右击任意工具栏中的空白处以打开其上下文菜单来开启和关闭工具栏。

更多内容：

[默认工具栏](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/README.zh.md)  
[动态工具栏](/Manual/basic_concepts/the_lister/toolbars/dynamic_toolbars.zh.md)  
[工具栏集](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.zh.md)