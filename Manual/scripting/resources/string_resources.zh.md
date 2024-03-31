# 字符串资源

除了 *对话框资源*，脚本还可采用 *字符串资源*，这为脚本支持临时字符串语言提供了一种简单方法（即，对于不属于静态对话框但由脚本以编程方式使用的字符串）。对话框中定义的字符串（如 *按钮* 控件** 标签**）可以使用 *[语言叠加](/zh/script_editor/editors/dialog_editor/language_overlays.zh.md)* 功能进行翻译。

考虑以下 VBScript 片段，这是一个非常简单的例子。

    If DOpus.language = "francais" Then
    DOpus.Output "Bonjour!"
    ElseIf DOpus.language = "deutsch" Then
    DOpus.Output "Guten Tag!"
    Else
    DOpus.Output "Hello!"
    End If

这会测试 Opus 运行时的当前语言，并用这种语言打印一个适当的“hello”字符串，或者如果语言未知时用英语打印。对于单个字符串而言，这样做很好，但是，对于脚本中的每个字符串都必须这样做，可能会需要大量输入。通过使用字符串资源，上述脚本片段会简化为：

    DOpus.Output DOpus.Strings.Get("hello")

实际字符串本身以 XML 资源提供，与对话框定义类似。以下为提供上述字符串的字符串资源：

    <resources>
    <resource type="strings">
    <strings lang="francais">
    <string id="hello" text="Bonjour!" />
    </strings>
    <strings lang="deutsch">
    <string id="hello" text="Guten Tag!" />
    </strings>
    <strings lang="english">
    <string id="hello" text="Hello!" />
    </strings>
    </resource>
    </resources>

正如您所看到的，有三个 **strings** 标签，每个标签都有不同的 **lang** 属性（这指定了语言）。每个 **strings** 标签内部有一到多个 **string** 标签，它们提供了实际字符串。**id** 属性是您选择的一个名称——这是脚本引用字符串的方式。**text** 属性提供指定语言的字符串翻译。

**lang** 属性的值与 Directory Opus 语言库的名称相对应（可在 **/home/Language** 文件夹中找到）——**english**、**deutsch**、**francais**、**cat**、**czech**、**espanol** 等。

可以使用脚本编辑器中的 GUI 编辑器编辑字符串资源。如果您要在按钮脚本中使用 XML 资源，那么需要自己对它们进行编码。