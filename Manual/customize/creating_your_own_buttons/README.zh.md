# 创建您自己的按钮

Opus 独有特色之一就是其工具栏完全可自定义。所有工具栏（和菜单）按钮均由一个或多个指令构成，包含以下内容：

- [内部指令](/Manual/reference/command_reference/internal_commands/README.zh.md)，它提供对 Opus 内部特性的访问权限。所有内部指令都有一组 [参数](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md)，可用于修改其行为，以便产生不同的结果（例如移动文件，而不是复制文件）。
- 外部指令让您可以在 Opus 内运行第三方程序。借助 [特殊代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)，您可以将信息（如选定文件的文件名）传递给外部程序，从而将它们更全面地集成到您的 Opus 配置中。

还可以使用 ActiveX 脚本语言（如 VBScript 或 JScript）将工具栏按钮编写为脚本。请参阅 [脚本](/Manual/scripting/README.zh.md) 页面，以进一步了解脚本按钮。

几个可能不显而易见的问题：

- 工具栏按钮和下拉菜单是同一事物。下拉菜单实际上只是一条垂直工具栏。
- Opus 附带的所有工具栏按钮和菜单都可更改。您可以编辑提供的按钮（在它们周围移动、删除它们、修改其功能等），并添加您自己的按钮（添加到标准工具栏或您创建的工具栏中）。您甚至可以完全关闭标准工具栏。

- 如果您在任何时候想要返回到默认工具栏，只需右键单击任何工具栏，然后选择“重置为默认值”命令。

关于 Opus 最重要的就是：

***如果您不喜欢某事，您可以随时更改！***

按钮和工具栏编辑有很多方面，在其部分中的页面内详细说明。要开始，请参阅以下列表，或在左侧“内容”标签页中展开此部分。

更多：

[编辑工具栏](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md)  
[命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md)  
[用户定义指令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md)  
[同步和异步函数](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.zh.md)  
[内部指令参数](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md)  
[将文件传递给外部程序](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md)  
[指令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md)  
[MS-DOS 批处理指令](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.zh.md)  
[嵌入重命名脚本](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.zh.md)  
[DDE 函数](/Manual/customize/creating_your_own_buttons/dde_functions.zh.md)  
[嵌入函数](/Manual/customize/creating_your_own_buttons/embedded_functions.zh.md)