# 简单脚本函数

这是 [脚本函数](../script_functions.zh.md) 的示例，可以显示当前文件夹中最大的文件的文件名，并可择将其选中。

要使用此函数，您需要：

- [创建新工具栏按钮](/Manual/customize/creating_your_own_buttons/README.zh.md) 或热键并在 [编辑器](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md) 中进行 [编辑]( /Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.zh.md)
- 在 [命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/README.zh.md) 中单击 **高级** 按钮，切换至 [高级命令编辑器](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.zh.md)
- 将 **函数** 下拉列表设置为 **脚本函数**

    // 将脚本类型设置为 JScript 以使用此脚本
    // 主脚本入口点。clickData 是 **ClickData** 对象
    function OnClick(clickData) {
    // 初始化变量以跟踪最大的文件
    largestFile = null;
    // 创建枚举器对象，以让我们轻松枚举当前标签页中的文件。
    // clickData.func 是 **Func** 对象
    // func.sourcetab 是 **Tab** 对象
    // sourcetab.files 是 **Item** 对象的集合
    enumFiles = new Enumerator(clickData.func.sourcetab.files);
    enumFiles.moveFirst();
    // 枚举标签页中的文件
    while (enumFiles.atEnd() == false) {
    // 如果这是迄今为止遇到的最大文件，则跟踪它
    // 文件大小可通过 **Item** 对象及其 **size** 属性获取
    // 我们使用 **FileSize** 对象的 **cy ** 属性，因为这可以更轻松地以数字比较两个大小
    if (largestFile == null || largestFile.size.cy < enumFiles.item().size.cy)
    largestFile = enumFiles.item();
    enumFiles.moveNext();
    }
    // 创建 **Dialog** 对象以显示结果
    dlg = clickData.func.Dlg;
    if (largestFile == null) {
    // 未找到文件，因此显示警告消息
    dlg.message = "此文件夹中没有文件!";
    dlg.buttons = "OK";
    dlg.icon = "warn";
    }
    else {
    // 构建信息消息来报告最大文件
    // 对话框将有两个按钮，让用户可以选择该文件
    dlg.message = "最大文件是 '" + largestFile.name + "' - " + largestFile.size.fmt;
    dlg.buttons = "将其选中 | 取消";
    dlg.icon = "info";
    }
    dlg.title = "最大文件查找器";
    // 显示对话框。如果用户单击“将其选中”按钮，它将返回 1
    if (dlg.Show() == 1) {
    // 初始化并运行选择命令以选择最大的文件
    // 这利用了 clickData.func 通过按钮提供给的 **Command** 对象
    clickData.func.command.ClearFiles();
    clickData.func.command.AddFile(largestFile);
    clickData.func.command.RunCommand("Select FROMSCRIPT DESELECTNOMATCH MAKEVISIBLE");
    }
    else {
    // 未选中文件，因此确保任何已选中的内容不受影响
    clickData.func.command.deselect = false;
    }
    }