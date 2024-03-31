# 将文件传递到外部程序

使用 Opus 作为简单的程序启动器很好，但更为有用的是将文件名称传递给您启动的程序这一能力。例如，您可以配置一个按钮来自动运行 Photoshop，在命令行中传递所选文件的文件名。如果您随后选择六个图像文件并单击 Photoshop 按钮，它们将自动在 Photoshop 中全部打开。

![](/Manual/images/media/passing_files.png) 

在上方的屏幕截图中，**{allfilepath}** 是一个特殊代码，用于在程序启动时在命令行中传递所有选定文件的名称。使用工具栏上的此命令，您可以选择一个或多个图像文件，然后单击按钮，将其加载到 Photoshop 中 - 或者，您可以将文件直接拖放到按钮上。

Opus 允许您将多种不同类型的信息传递到外部程序，包括所选文件的文件名、当前源文件夹的文件名、表示当前日期和时间的字符串等等。有关完整列表，请参见 [外部控件代码](/Manual/reference/command_reference/external_control_codes/README.zh.md) 部分。