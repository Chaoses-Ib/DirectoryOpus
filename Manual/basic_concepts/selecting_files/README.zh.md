# 选择文件

每当要对文件执行某项操作（复制、删除或仅查看）时，您都必须先选择该文件。Directory Opus 中的大多数文件操作都会对所有当前选定的文件（及文件夹）进行操作，因此了解如何选择文件以及如何得知选择的文件数量很重要。

### 手动选择文件

有关使用鼠标或键盘选择文件的信息，请参阅[使用鼠标或键盘](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/README.zh.md)。

### 自动选择文件

内部的[选择](/Manual/reference/command_reference/internal_commands/select.zh.md)命令允许您通过很多不同方式自动选择文件。默认的**编辑**菜单有许多预定义的**选择**命令：

- **全选**：选择当前文件夹中的所有项目。
- **按模式选择**：显示一个对话框，允许您使用[简单通配符模式](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md)选择文件。您可以将该对话框切换为高级模式，以允许您使用[多个不同条件](/Manual/basic_concepts/selecting_files/advanced_selection.zh.md)选择文件。
- **反向选择**：反转文件夹中所有项目的选中状态。

在**编辑 / 其它选择**子菜单中提供更多命令：

- **重新选择文件**：选择先前执行的命令使用了（且取消选择了）的所有文件。
- **选择相同扩展名**：选择与当前选定文件具有相同扩展名的所有文件（例如选择一个 .txt 文件，然后使用此命令自动选择所有其它 .txt 文件）。
- **选择空文件夹**：选择完全没有任何内容的所有文件夹。
- **选择零字节文件夹**：选择其中包含零字节的所有文件夹（即它们不为空 - 它们可能包含子文件夹或零字节文件）。
- **选择展开的文件夹项**：选择位于[展开的文件夹](/Manual/basic_concepts/expandable_folders.zh.md)内的项目。
- **选择源到目标**：选择具有与源中当前选定文件相同名称的目标中的文件。
- **将所有源选择到目标**：选择具有与源中的文件相同名称的目标中的文件（它们不需要被选中）。
- **将所有源选择到目标（忽略扩展名）**：选择具有与源中的文件相同名称的目标中的文件（忽略文件扩展名）。
- **选择源而非目标**：选择源中不存在于目标中的文件。
- **选择到复选框**：设置复选框状态以匹配当前选择。如果文件列表尚未设置为[复选框模式](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.zh.md)，则会将其设置为该模式。
- **复选框到选择**：设置选择以匹配复选框状态。
- **选择重复项...**：显示[重复文件查找程序](/Manual/additional_functionality/duplicate_file_finder.zh.md)的选择对话框。

### 状态栏上显示的计数

了解当前选择了多少个文件和文件夹的最简单方法是查看[状态栏](the_lister/status_bar.zh.md)。

![](/Manual/images/media/13/status_bar_1.png)

状态栏显示您在当前文件列表中选择的文件夹和文件数（以及总数）。无论何时单击**复制文件**或**删除**之类的按钮，都将使用这些选定文件在该功能中。

更多信息：

[使用鼠标和键盘选择](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/README.zh.md)  
[简单的通配符选择](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.zh.md)  
[高级选择](/Manual/basic_concepts/selecting_files/advanced_selection.zh.md)