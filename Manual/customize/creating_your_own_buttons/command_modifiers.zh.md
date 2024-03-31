# 命令修饰符

Opus 支持各种命令修饰符，可用于工具栏按钮和热键中，以修改功能行为。命令修饰符本身不是命令 - 大多数情况下，您可以将它们视为控制如何执行功能的选项。

每个修饰符都在单独的行中给出 - 因此，要在函数中使用命令修饰符，您必须在 [高级命令编辑器](command_editor/advanced_command_editor.zh.md) 中编辑函数（因为简单编辑器不支持多行函数）。一些修饰符（如 **@async**）会影响函数中的单个命令，并与命令出现在同一行中 - 而另一些修饰符会影响整个函数，并单独提供在一行中。

![](/Manual/images/media/command_modifiers_001.png) 

此屏幕截图是一个简单函数的示例，该函数使用了两个命令修饰符：

- **@filesonly** 修饰符导致函数仅使用选定的文件 - 任何当前选定的文件夹都将被忽略。**{f}**[外部控制代码](/Manual/reference/command_reference/external_control_codes/README.zh.md) 表示依次将每个文件名传递给记事本。
- **@async** 修饰符导致后续命令在本例中 **notepad.exe** 异步运行。如果选择多个文件，将为每个文件执行记事本的实例，而不等待前一个实例返回。

请参阅 [命令修饰符参考](/Manual/reference/command_reference/command_modifier_reference.zh.md) 页面，了解可用命令修饰符的完整列表。