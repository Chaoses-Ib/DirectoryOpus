# 脚本

Directory Opus 脚本接口让你可以使用任何已安装的 ActiveX 脚本语言编写脚本。这允许脚本使用你可能已知晓的常用语言编写。JScript（JavaScript 的变体）和 VBScript 已内置于 Windows 中，在兼容性、帮助和来自 Directory Opus 支持论坛的示例方面通常是最简单的选择，并且易于与其它用户共享。其它语言如 Perlscript 和 Python 可以从第三方提供者处获取。

通过脚本接口你可以：

- 查询列表工具、标签、路径和工具栏的状态
- 获取文件和目录的列表，并发现它们的信息（基本信息如名称、大小、修改时间等，以及元数据如 EXIF 信息、MP3 标签等）
- 从脚本代码中编写按钮和快捷键函数，而不必诉诸于“重命名”技巧
- 测试特定系统设置的状态（类似于传统函数中的 **@ifset**）
- 构建文件集合，并对它们运行命令（Opus 内部命令和外部程序）
- 显示对话框和弹出菜单
- 访问剪贴板、环境变量和目录别名
- 扩展 Opus 内部命令的列表
- 添加可以显示在文件列表和信息提示中的其它文件和目录信息列
- 基于特定事件自动触发脚本
- 保存和加载配置（Opus 提供了一个可以用来编辑脚本配置的编辑器）

脚本接口表现为一系列的对象，可以导出你可以调用的方法和你能够查询（有时候可以设置）的属性。

有三种方法可以使用带有 Opus 的脚本。

- **[重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)** 让你在 [高级重命名](file_operations/renaming_files/advanced_rename/README.zh.md) 对话框中编写脚本，该脚本提供对文件重命名的完全控制。
- **[脚本函数](/Manual/scripting/script_functions.zh.md)** 是直接在按钮、菜单或快捷键中定义的脚本（customize/creating_your_own_buttons/README.zh.md）。
  \* **[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)** 是安装在 Opus *脚本加载项* 目录中的脚本文件。而脚本函数是由用户驱动的（例如，当用户单击按钮以专门运行脚本时，它们执行），脚本加载项则是事件驱动的。它们提供一个或多个定义的事件处理程序，Opus 将在特定情况下调用它们，它们还用于实现 [自定义命令](/Manual/scripting/example_scripts/adding_a_new_internal_command.zh.md) 和 [列](/Manual/scripting/example_scripts/adding_a_new_column.zh.md)。

请参阅 [脚本参考](scripting/README.zh.md) 部分，了解 Opus 脚本对象的完整指南，以及 [示例脚本](/Manual/scripting/example_scripts/README.zh.md) 部分，了解各种类型的脚本的某些示例。

通过 **DOpus.Output** 函数从脚本输出的任何错误/警告或文本都会显示在 *脚本日志* 面板（作为 *实用面板* 的一部分）中。你可以使用 **[配置 / 其它 / 高级](preferences/preferences_categories/miscellaneous/advanced_options.zh.md): script_output_level** 选项来选择在日志中显示的信息类型。

你还可以使用 **[CLI](additional_functionality/cli.zh.md)** 工具来设计和测试临时脚本。更多：

[脚本参考](reference/scripting_reference/README.zh.md)  
[重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)  
[脚本函数](/Manual/scripting/script_functions.zh.md)  
[脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)  
[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)  
[资源](/Manual/scripting/resources/README.zh.md)  
[示例脚本](/Manual/scripting/example_scripts/README.zh.md)