# 示例重命名脚本

这是一个 [重命名脚本](../rename_scripts/README.zh.md) 的示例，它会将图像文件的解析度添加到其文件名中。

您可以通过 **[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)** 对话框使用此脚本（打开 **脚本模式** 选项以显示脚本编辑器）。您也可以将 [脚本嵌入按钮](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.zh.md) 中。

    ' 设置脚本类型为 VBScript 以使用此脚本
    选项显示
    ' 主函数重命名项。该方式针对每个文件传递一个 **GetNewNameData** 对象
    函数 OnGetNewName(按引用 GetNewNameData)
    Dim 项目，meta
    ' 从 **GetNewNameData** 对象的 **项** 属性获取提供的 **项** 对象
    Set 项目 = GetNewNameData.Item
    ' 请求其元数据。这将返回一个 **元数据** 对象。
    Set 元数据 = 项目.元数据
    ' 如果元数据的基本类型为“图像”，那么我们知道这是一个图像文件
    如果 元数据 = “图像” 然后
    ' 构建并返回新名称
    ' 它由以下部分组成
    ' - “名称词干”（原始文件名减去文件扩展名）
    ' - 从 **ImageMeta** 对象（来自 **元数据.图像** 属性）获取的图像宽度和高度
    ' - 原始文件名扩展名
    OnGetNewName = 项目.名称词干 & " (" & 元数据.图像.图像宽度 & "x" & 元数据.图像.图像高度 & ")" & 项目.扩展名
    别外
    ' 该项不是图像，因此返回 True 以跳过它
    OnGetNewName = True

    尾如果

    尾函数

