# 字符串编辑器

##### 字符串资源

脚本对话框通过[语言覆盖](dialog_editor/language_overlays.zh.md)的形式提供了多语言界面，脚本还可以使用*字符串资源*，它为脚本提供了一种支持临时字符串的多语言的简单方法。

考虑一下下面的 VBScript 片段，这是一个非常简单的示例。

    If DOpus.language = "francais" Then
      DOpus.Output "Une erreur s'est produite."
    ElseIf DOpus.language = "deutsch" Then
      DOpus.Output "Ein Fehler ist aufgetreten."
    ElseIf DOpus.language = "espanol" Then
      DOpus.Output "Ocurrió un error."
    Else
      DOpus.Output "An error occurred."
    End If

这将测试 Opus 当前运行的语言，并用相应的语言打印合适的“您好”字符串，如果没有找到匹配的语言，那么就显示英语。这对于一个字符串来说很好，但是对于脚本中的每个字符串都这样做，可能需要很多输入。使用字符串资源，上面的脚本片段简化为：

    DOpus.Output DOpus.Strings.Get("error")

##### 字符串编辑器

要添加新的字符串资源语言，请切换到脚本编辑器中的*资源*标签页，然后右键单击所述脚本文件，并从上下文菜单中选择**新建字符串**。Opus 将提示您选择要为其添加字符串的语言。

字符串资源编辑器是一个非常简单的网格，有两列。*名称*列允许您指定字符串的名称 - 在上面的示例中，将其设置为“error”。*翻译*列允许您提供所选语言的翻译。

![](/Manual/images/media/13/scripteditor_strings.png)