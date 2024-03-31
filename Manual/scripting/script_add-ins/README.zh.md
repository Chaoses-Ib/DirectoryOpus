# 脚本插件

*脚本插件* 是一些安装在 Opus *脚本插件* 文件夹中的脚本文件（你可以通过在位置字段中键入 **/dopusdata/Script AddIns** 找到该文件夹）。脚本插件是一些纯文本文件，其扩展名指定了所用脚本语言（例如，扩展名为 **.js** 的文件将是 *JScript* 脚本）。一个或多个脚本插件可以打包在称为 *[脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)*（具有 **.osp** 后缀名的 zip 文件）的压缩包文件中，还可以选择性地附带一组图标。

[脚本函数](script_functions.zh.md) 仅在单击其所在的按钮时才会被调用，而脚本插件可以在响应一个或多个 [事件](/Manual/reference/scripting_reference/scripting_events/README.zh.md) 时自动调用。每个脚本都可以为一个或多个已定义的事件入口点提供处理，Opus 将自动调用为相关事件提供处理的每个脚本。脚本被通知的某些事件包括：标签被激活或停用，在文件夹变化之前和之后，当视图模式发生变化以及当文件窗口被打开或关闭时。脚本插件还可以实现 [自定义命令](example_scripts/adding_a_new_internal_command.zh.md)，这样便可以以类似于 *用户命令* 的方式来扩展 Opus 内部命令集，以及 [自定义列](example_scripts/adding_a_new_column.zh.md)，这样便可以为文件和文件夹添加其他信息列。

**[脚本管理](/Manual/scripting/script_management/README.zh.md)** 对话框显示已安装的任何插件脚本的列表。你可以使用复选框来启用或禁用每个脚本。

![](/Manual/images/media/script_list_001.png)

如果你在列表中选择一个脚本，它将显示有关该脚本的更多信息（说明、版权信息、脚本实现的命令、列和事件的列表）。如果脚本支持这些操作，**关于** 和 **配置** 按钮将变为活动状态。单击 **编辑** 按钮将在默认文本编辑器中打开该脚本（仅限独立脚本）。

你可以通过将它们拖放到 *脚本* 列表中，来轻松地安装新脚本或脚本包。你还可以使用脚本列表上方的工具栏中的 **新脚本** 按钮创建一个新的脚本。这将显示 *创建新脚本* 对话框：

![](/Manual/images/media/newscript.png)

该对话框让你可以创建一个 *JScript* 或 *VBScript* 脚本的模板。选择理想的语言，并输入一个名称、可选说明和版权字符串，然后使用列表中的复选框来选择你希望脚本为其创建函数的事件。

列表中的最后两个事件 *NewScriptCommand* 和 *NewScriptColumn* 让你可以创建添加内部命令或列的脚本。当你打开此选项时，它将激活并让你为该命令或列输入一个新的名称。按回车键来接受新名称，另一个 *NewScriptXXX* 条目将被添加到列表中。用这种方式，你可以轻松地为添加多个内部命令或列的脚本创建一个模板。

更多内容：

[脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)