# CLI

**CLI/临时脚本编辑器**具有两个主要功能：

- 向 Directory Opus 命令集提供一个非常简单的命令行界面 (CLI)。
- 在脚本模式下，它允许您设计和测试临时[脚本](/Manual/scripting/README.zh.md)。

您可以使用**工具/Opus CLI**菜单命令打开 CLI。

![](/Manual/images/media/cli.png) 

命令行允许您直接运行[内部命令](/Manual/reference/command_reference/internal_commands/README.zh.md)，无需首先配置按钮或热键。它类似于在命令模式中使用[即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md)字段。您还可以通过输入命令名称后跟 ? 符号（如上面的屏幕截图所示）来显示任何内部命令的完整模板。

启用**脚本解释器**选项会将 CLI 置于脚本模式，该模式允许您设计和测试临时脚本。下拉字段允许您选择脚本语言 - 如果您希望使用的语言未列出，只需输入名称即可。您需要查阅第三方语言的文档以了解“脚本引擎”的名称。

![](/Manual/images/media/cli_scriptmode.png)

按 **F5** 或单击**运行**按钮运行您的脚本。脚本中的任何错误、警告或文本输出（例如通过 **DOpus.Output** 方法）都将显示在编辑器下方的输出字段中。

（下面提到的快捷键适用于 Directory Opus 的英文版本。将鼠标悬停在按钮上以发现它们在您语言中的快捷键。）

**中止**（**Alt+A**）按钮可用于停止陷入循环的脚本。

**新建**（**Alt+N**）按钮清除脚本和输出字段，以便您可以重新开始。

**加载**（**Alt+L**）和**保存**（**Alt+S**）按钮允许您加载和保存脚本以便以后使用。

如果选中**清除**选项，则每次运行脚本时都会清除输出字段；否则，每次运行的输出都会累积。