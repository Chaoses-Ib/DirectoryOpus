# 选择事件

此页面允许您覆盖使用鼠标选择文件夹树中文件夹时运行的命令。您可以为鼠标的左键和中键配置命令（鼠标右键始终用于快捷菜单），还可以在按住 <kbd>Alt</kbd>、<kbd>Ctrl</kbd> 和 <kbd>Shift</kbd> 键时设置单独的命令。

每个事件的命令必须是在按钮或热键上可实现的命令。您可以使用 [Opus 内部命令](/Manual/customize/creating_your_own_buttons/internal_command_arguments.zh.md) 或外部程序（使用 [标准控制代码](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md) 向其传递参数）。如果您想运行超过一条简单的单行命令，则可以创建更复杂的 [用户定义命令](/Manual/customize/creating_your_own_buttons/user-defined_commands.zh.md），然后为事件指定用户命令的名称。

这些事件的默认设置如下：

### 鼠标左键

- **默认**：`转到`。将选定的文件夹读入当前与该树关联的文件列表中。
- <kbd>Alt</kbd>：`转到 新标签页`。将选定的文件夹读入新标签页中。
- <kbd>Ctrl</kbd>：`转到 打开在其他窗格`。将选定的文件夹读入双栏屏中，即**不**当前与该树关联的文件列表。如果该树当前不在双栏屏模式下，它将自动进入该状态。

### 鼠标中键

- **默认**：`转到 新标签页`。将选定的文件夹读入新标签页中。
- <kbd>Ctrl</kbd>：`转到 新标签页 打开在其他窗格`。将选定的文件夹读入另一文件列表中的新标签页中。