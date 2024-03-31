# MS-DOS 批处理命令

Opus 按钮或热键功能可以设置为 *MS-DOS 批处理功能* 模式。此模式中的一个功能的运行方式就像 **.bat** 批处理文件一样，它可以使用 MS-DOS 命令、分支和逻辑指令，还可以运行仅设计为从命令行运行的外部程序。您还可以在批处理功能中包含常规 Opus 内部命令（请注意，当尝试使用 **Set** 或 **Copy** 等与内部命令冲突的外部命令时，可能会造成混乱 - 使用下面描述的 **@externalonly** 修饰符解决此问题）。

![](/Manual/images/media/dos_batch_function.png) 

上面的屏幕截图演示了一个简单的 MS-DOS 批处理功能示例。它使用 MS-DOS **dir** 指令生成当前源文件夹的目录列表。使用 **\>** 重定向符号，目录列表将保存到目标路径中，文件名以当前源文件夹命名。

分解该功能：

- 使用 **Function** 下拉菜单将类型设置为 **MS-DOS Batch Function**。这对于使用 **dir** 指令是必要的 - **dir** 不是一个真正的程序或命令，它是一个仅由 MS-DOS 命令解释器理解的指令。
- 命令的第一行 **cd {sourcepath}** 将批处理脚本的当前目录设置为当前源文件夹。这是 **dir** 将生成其列表的文件夹。
- 第二个命令调用 **dir** 指令（\*\* /w\*\* 标志打开“宽”模式）。**\>** 字符会重定向该命令的输出，在 **\>** 后面，外部控制代码的组合会提供输出文件名。
  - **{destpath}** - 当前目标目录的路径
  - **{sourcepath\|nopath\|noterm}** - 当前源目录，不含路径或尾随终止符（即目录的名称）
  - **.txt** - 输出文件的扩展名。

当您运行 MS-DOS 批处理功能时，Opus 实际上会创建磁盘上的一个临时批处理文件，并在调用它之前将指令写入其中。如果您查看由上述功能创建的批处理文件，您将看到类似以下内容：

    @echo off
    chcp 1252 > nul
    C:
    cd "\Users\Jon\Documents"
    dir /w > "C:\Test\Documents.txt"

  
这些指令会根据该功能的参数和定义自动写入到 **.bat** 文件。

- **@echo off** 是一个标准的 MS-DOS 指令，它可以防止在批处理文件运行时将每个命令都回显到提示窗口
- **chcp 1252 \> nul** 初始化命令提示符的代码页（1252 是标准的 Windows 代码页）。
- **C:** 设置命令提示符的当前驱动器 - 这是从命令定义中的 **cd {sourcepath}** 指令自动生成的。
- **cd "\Users\Jon\Documents"** 设置当前驱动器上的当前目录 - 同样，这是从 **cd {sourcepath}** 指令自动生成的。
- **dir /w \> "C:\Test\Documents.txt"** 负责生成实际的目录列表。在这个示例中，源文件夹名为 Documents，目标文件夹为 C:\Test* - 所以由 **{destpath}{sourcepath\|nopath\|noterm}.txt** 生成的输出文件名为 C:\Test\Documents.txt。

[命令修饰符](command_modifiers.zh.md) 中有几个与 MS-DOS 批处理功能特别相关：

- **@leavedoswindowopen** 可用于强制 DOS 提示窗口在函数完成之后保持打开（让您看到任何输出或错误消息）。
- **@codepage** 可用于将 DOS 提示符的代码页更改为默认值 *1252*。
- **@externalonly** 告诉 Opus 忽略可能与内部命令重合的任何命令名称（例如 Set 或 Copy）。通常情况下，内部命令会覆盖外部命令。
- **@nocall** 用于调用批处理文件而不将控制权返回给父函数。
- **@runbatch** 和 **@norunbatch** 控制外部程序和内部命令如何在 MS-DOS 批处理功能中进行交互
- **@runmode:hide** 可用于防止 DOS 提示窗口短暂闪烁。

有关命令修饰符的完整描述，请参见 [命令修饰符参考](/Manual/reference/command_reference/command_modifier_reference.zh.md)。