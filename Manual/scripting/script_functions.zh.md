# 脚本函数

*脚本函数* [在按钮或菜单中直接定义](/Manual/customize/creating_your_own_buttons/README.zh.md)-它们是按钮函数第三种类型，除了 *标准函数* 和 *MS-DOS 批处理函数*。

![](/Manual/images/media/script_function.png)

上面的截图是脚本函数的示例，它选择当前源文件列表中的所有“高分辨”图像（定义为垂直分辨率大于或等于 1080 像素的图像）。

脚本编辑器顶部的下拉菜单用于指定脚本语言 - 在这里它设置为 *VBScript*。**默认**按钮允许您将脚本“模板”保存为特定语言的默认模板，并随时恢复为默认设置。

**[OnClick](/Manual/reference/scripting_reference/scripting_events/onclick.zh.md)** 函数是一个已定义的脚本入口点，Opus 将在每次单击按钮（或按下热键）时调用该函数。传入它的**[ClickData](/Manual/reference/scripting_reference/scripting_objects/clickdata.zh.md)** 对象提供许多属性和方法，您可以使用它们与启动该函数的文件窗口进行交互。

当函数编辑器设置为运行*脚本函数*时，它将具有三个独立的标签页，将该函数分割为：

- **修饰符**：应用于脚本的任何 [命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md)（例如 **@filesfromdroponly**）。
- **脚本代码**：定义脚本的实际代码。
- **资源**：脚本[资源](resources/README.zh.md)。

在函数编辑器的底部，**运行**按钮允许您立即测试当前脚本，而无需退出*自定义*模式。当您使用**运行**按钮时，编辑器下方将显示一个输出面板，其中显示任何错误或脚本文本输出。

**资源**标签页定义脚本可用的任何[资源](resources/README.zh.md)。对话框是主要类型的资源，但也支持字符串资源，允许您用多种语言定义字符串。

![](/Manual/images/media/image063.png)

虽然您可以根据需要在 XML 中手动编写对话框资源，但使用内置[对话框编辑器](/Manual/scripting/script_editor/editors/dialog_editor/README.zh.md)进行设计会容易得多。