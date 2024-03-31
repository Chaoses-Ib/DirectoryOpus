# 响应事件

当一个或多个 [事件](/Manual/reference/scripting_reference/scripting_events/README.zh.md) 发生时，[脚本加载项](../script_add-ins/README.zh.md) 将被激活。

以下是一个对两个不同事件做出反应的脚本加载项示例。使用它的方法是在 *Script Addins* 文件夹中创建一个新的 **.vbs** 文件（在位置字段中键入 **/dopusdata/Script Addins** 以找到此文件夹）。

此示例对文件夹更改 (**[OnAfterFolderChange](/Manual/reference/scripting_reference/scripting_events/onafterfolderchange.zh.md)**) 和视图模式更改 (**[OnDisplayModeChange](/Manual/reference/scripting_reference/scripting_events/ondisplaymodechange.zh.md)**) 事件做出反应。

在这两种情况下，它检查当前文件夹是否为 *Pictures* 库（**lib://Pictures** 或子文件夹）。如果是，它会根据当前视图模式自动更改排序模式：

- 如果显示设置为 *缩略图* 模式，列表将按日期排序
- 否则，列表将按名称排序

    ' 将脚本类型设置为 VBScript 以使用此脚本
    ' **OnInit** 事件由 Directory Opus 调用以初始化脚本
    Function OnInit(ByRef initData) ' 提供有关脚本的基本信息
    initData.name = "Example Event Script"
    initData.desc = "Script that shows an example of responding to events"
    initData.copyright = "(c) 2016 Jonathan Potter"
    initData.default_enable = True End Function
    ' **OnAfterFolderChange** 事件在读取文件夹后调用
    Function OnAfterFolderChange(ByRef afterFolderChangeData) ' **AfterFolderChangeData** 对象的 **result** 属性告诉我们读取是否成功
    If afterFolderChangeData.result Then ' 检查读取的路径是否以 lib://Pictures 开头
    If Left(afterFolderChangeData.tab.path, 14) = "lib://Pictures" Then
    ' 路径匹配，因此调用我们的 **CheckPictureSorting** 子例程以根据需要更新排序模式
    ' 我们将文件夹所在的 **Tab** 作为参数传递给子例程
    Call CheckPictureSorting(afterFolderChangeData.tab)

    End If

    End If End Function
    ' **OnDisplayModeChange** 事件在每次视图模式更改时调用
    Function OnDisplayModeChange(ByRef displayModeChangeData) ' **DisplayModeChangeData** 对象为我们提供了更改模式的 **Tab**
    ' 查看当前在标签页中显示的文件夹是否为 lib://Pictures 或子文件夹
    If Left(displayModeChangeData.tab.path, 14) = "lib://Pictures" Then
    Call CheckPictureSorting(displayModeChangeData.tab)
    End If

    End Function
    ' 这是一个由以上两个事件调用的子例程，并且将 **Tab** 对象作为参数传递。
    ' 它创建一个 **Command** 对象并使用 **IsSet** 方法来查看标签页中当前的视图模式是否为缩略图
    ' - 如果是，它使用 RunCommand 方法将排序顺序设置为“修改日期”
    ' - 如果不是，它将排序顺序设置为“名称”
    Sub CheckPictureSorting(ByRef objTab)

    Set objCmd = DOpus.CreateCommand
    objCmd.SetSourceTab(objTab)
    If objCmd.IsSet("VIEW=Thumbnails") Then
    objCmd.RunCommand("Set SORTBY=modified")
    Else
    objCmd.RunCommand("Set SORTBY=name")
    End If
    Set objCmd = Nothing End Sub