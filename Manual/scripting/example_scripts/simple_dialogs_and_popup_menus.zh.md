# 简单对话框和弹出菜单

通过 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)** 对象，脚本可以轻松显示各种类型的对话框和弹出菜单。以下是几个示例。您可以在 **[CLI](/Manual/additional_functionality/cli.zh.md)** 中尝试所有这些，已设置为 **脚本模式**（类型设置为 *VBScript*）。

# 简单对话框和弹出菜单

![](/Manual/images/media/simple_message_dialog.png)

    ' 创建 Dialog 对象。您还可以从文件窗口、Tab、Func 和 Command 对象获取对话框对象。
    设置 dlg = DOpus.Dlg 
    ' 初始化对象，以显示带有三个按钮的简单消息。
    dlg.window = DOpus.文件窗口s(0)
    dlg.message = "简单对话框消息"
    dlg.title = "对话框标题"
    dlg.buttons = "首选 | 第二选择 | 取消"
    ' 显示对话框，并将结果输出到脚本日志
    ret = dlg.Show
    DOpus.Output "Dialog.Show 返回 " & ret

# 简单对话框和弹出菜单

![](/Manual/images/media/complex_message_dialog.png)

    ' 创建 Dialog 对象。
    设置 dlg = DOpus.Dlg 
    ' 初始化对象，以显示一个带三个按钮的消息，其中一个按钮包含多个选项的下拉菜单
    ' 该对话框还有一个警告图标、一个允许用户输入一行文本的文本字段、
    ' 以及可以打开或关闭的两个复选框。
    dlg.window = DOpus.文件窗口s(0)
    dlg.message = "更复杂的对话框消息。" & vbCrLf & "输入一些文本并选择您的选项。"
    dlg.title = "复杂对话框标题"
    dlg.buttons = "首选 | 第二选择 + 第三选择 + 第四选择 | 取消"
    dlg.icon = "warn"
    dlg.max = 128 ' 启用文本字段
    dlg.options(0).label = "复选框选项 1"
    dlg.options(1).label = "复选框选项 2"
    ' 显示对话框，并将结果输出到脚本日志
    ret = dlg.Show
    DOpus.Output "Dialog.Show 返回 " & ret
    DOpus.Output "您输入的字符串为 " & dlg.input
    DOpus.Output "设置的两个复选框分别为 " & dlg.options(0).state &" 和 " & dlg.options(1).state

# 简单对话框和弹出菜单

![](/Manual/images/media/drop_down_dialog.png)

    ' 创建 Dialog 对象。
    设置 dlg = DOpus.Dlg 
    ' 初始化对象，以显示一个下拉控件，使用户能够从很多选项中选取一个
    dlg.window = DOpus.文件窗口s(0)
    dlg.message = "下拉列表对话框消息"
    dlg.title = "下拉对话框标题"
    dlg.buttons = "确定 | 取消"
    dlg.choices = DOpus.Create.Vector("选项 1", "选项 2", "选项 3", "选项 4")
    dlg.selection = 0
    ' 显示对话框，并将结果输出到脚本日志
    ret = dlg.Show
    DOpus.Output "Dialog.Show 返回 " & ret
    DOpus.Output "选定的选项为 " & dlg.choices(dlg.selection)

# 简单对话框和弹出菜单

![](/Manual/images/media/selection_list_dialog.png)

    ' 创建 Dialog 对象。
    设置 dlg = DOpus.Dlg 
    ' 初始化对象，以显示一个列表项，用户可以打开或关闭这些项
    dlg.window = DOpus.文件窗口s(0)
    dlg.message = "列表项选择对话框消息"
    dlg.title = "列表项选择对话框标题"
    dlg.buttons = "确定 | 取消"
    dlg.choices = DOpus.Create.Vector("选项 1", "选项 2", "选项 3", "选项 4")
    dlg.list = DOpus.Create.Vector(True, False, True, False)
    ' 显示对话框，并将结果输出到脚本日志
    ret = dlg.Show
    DOpus.Output "Dialog.Show 返回 " & ret
    对于 i = 0 至 dlg.choices.size - 1
    DOpus.Output dlg.choices(i) & " 状态为 " & dlg.list(i)
    下一步

# 简单对话框和弹出菜单

![](/Manual/images/media/dialog_popup_menu.png)

    ' 创建 Dialog 对象。
    设置 dlg = DOpus.Dlg 
    ' 初始化对象，以显示一个弹出菜单，供用户选取
    dlg.window = DOpus.文件窗口s(0)
    dlg.choices = DOpus.Create.Vector("选项 1", "选项 2", "-", "选项 3", "选项 4")
    dlg.menu = DOpus.Create.Vector(2, 0, 0, 2, 0)
    ' 显示菜单，并将结果输出到脚本日志
    ret = dlg.Show
    DOpus.Output "Dialog.Show 返回 " & ret