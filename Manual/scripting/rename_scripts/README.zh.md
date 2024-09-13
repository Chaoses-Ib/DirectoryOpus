# 重命名脚本

这无疑是 *[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)* 对话框最强大的功能，但也是最复杂的功能。您可以编写重命名脚本，让您可以完全控制重命名操作的结果。

![](/Manual/images/media/rename_scripts.png)

以下是脚本化重命名的一个相当简单的示例。您可以看到脚本编辑器已显示。这最初预先填充了一个不执行任何操作的脚本，您可以对其进行编辑。

顶部的 *脚本类型* 下拉框用于指定脚本语言 - 在上面的示例中，选择了 *VBScript*。

1.  对于要重命名的每个文件，Opus 都会调用 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 函数。
2.  传递给 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 函数的参数是 **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.zh.md)** 对象。
3.  从中我们获取 **item** 属性，它返回 **[Item](/Manual/reference/scripting_reference/scripting_objects/item.zh.md)** 对象。
4.  从 Item 对象中，我们获取 **metadata** 属性，它返回一个 **[Metadata](/Manual/reference/scripting_reference/scripting_objects/metadata.zh.md)** 对象。
5.  我们检查此对象的默认值 - 如果它返回“*image*”，我们知道该项目是一个图像文件。
6.  我们建立一个新名称，该名称由原始文件的名词干组成（**Item.name_stem** 属性，由 VBScript **LCase** 函数转换为小写）。
7.  然后我们附加一个显示图像尺寸的字符串（从提供 **picwidth** 和 **picheight** 属性的 **Meta.image** 对象中提取）。
8.  最后附加原始文件名扩展名（**Item.ext**）。
9.  新名称从 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 函数返回（上面所示的 VBScript 惯例是通过将其分配给函数本身的名称来返回值）。
10. 如果图像不是图像文件，我们将返回 **True**，这将告诉 Opus 跳过该文件而不将其重命名。

所有错误消息或脚本输出的其它文本都可以在 *其它日志* 日志窗口中查看，可以通过 [工具面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md)（或 **帮助** 菜单中的 **日志 / 其它日志** 命令）进行访问。如果您发现脚本的行为与预期不符，则应检查此日志以查看是否生成了任何错误消息。您还可以使用 **DOpus.Output** 脚本方法将自己的文本输出到此日志，这有助于调试。

默认配置提供了 *Number Files* 脚本作为默认重命名预设之一，它是使用 VBScript 实现的，因此请随时查看它以获得更多复杂的示例。最后，请参阅 [Opus 资源中心](https://resource.dopus.com/c/rename?u=chaoses-ib) 上的 [重命名脚本部分](https://resource.dopus.com/c/rename?u=chaoses-ib)，以了解您可以下载和使用的重命名脚本示例，并且可以在论坛上寻求帮助撰写重命名脚本。

出于传统原因（因此，为早期版本的 Opus 编写的脚本仍将起作用），Opus 还支持两个替代函数。我们建议所有新脚本都使用上面所示的 **OnGetNewName** 事件。

最初支持的函数是 **Rename_GetNewName**，它采用多个参数，提供有关要重命名的文件的基本信息：

    Function Rename_GetNewName ( strFileName, strFilePath, 
     fIsFolder, strOldName, ByRef strNewName 
     )
    Rename_strNewName = 
     LCase(strNewName)
    End Function

新名称在“按引用传递”变量 **strNewName** 中返回。第二个替代函数 **Rename_GetNewName2** 是为不支持“按引用传递”变量的脚本语言提供的。唯一的区别是 **strNewName** 不是按引用传递的，并且您使用函数的返回值指定新名称。使用 **Rename_GetNewName2** 的以上示例看起来会像这样：

    Function Rename_GetNewName2 ( strFileName, strFilePath, 
     fIsFolder, strOldName, strNewName 
     )
    Rename_GetNewName2 = 
     LCase(strNewName)
    End Function

了解更多：

[重命名对话框中的自定义字段](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.zh.md)