# DDE 函数

DDE（[动态数据交换](http://zh.wikipedia.org/wiki/%E5%8A%A8%E6%80%81%E6%95%B0%E6%8D%AE%E4%BA%A4%E6%9D%A1)）是一个过时的系统，用于在 Windows 系统的不同程序之间传递数据。如今，它并没有得到太多使用——虽然可能令人惊讶，但[资源管理器替换](/Manual/basic_concepts/explorer_replacement.zh.md) 模式实际上是通过 DDE（某种程度上是出于历史原因）实现的。

尽管如此，你可能有一个支持 DDE 接口的旧程序，并且如果需要的话，可以配置一个按钮或热键，以向另一个应用程序发送一个称为 DDE 消息的东西。

![](/Manual/images/media/ddecommand.png) 

上面是一个示例命令，它建立一个 DDE 对话并向另一个程序发送一个命令。由于这个技术需要多条命令行，你必须在[高级命令编辑器](command_editor/advanced_command_editor.zh.md)中创建这个命令。上述功能中的四行是：

- **ddeexec**：**ddeexec** 指令指定要发送给另一个程序的“消息”。这将由该程序定义——上面的屏幕截图只是一个示例。**%1** [外部控制代码](/Manual/reference/command_reference/external_control_codes/codes_for_passing_filenames.zh.md) 用于在消息中包括所选文件的文件名。
- **ddeapp**：**ddeapp** 指令指定“应用程序名称”——当发送 DDE 消息时，这是另一个程序查找的名称。
- **ddetopic**：**ddetopic** 指令指定“消息主题”——同样，这取决于应用程序。
- 最后一行提供了用于启动另一个程序的实际命令行。这通常涉及传递某种命令行标志，告诉另一个程序你想让它在 DDE 模式下运行——就像上面的屏幕截图中带有 **/dde** 参数的情况一样。不过，这完全取决于所讨论的应用程序。