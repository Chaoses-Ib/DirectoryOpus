# 确认文件替换对话框

在复制文件时，经常会遇到文件已存在于目标文件夹中的情况。在此情况下，Opus 会正常显示 **确认文件替换** 对话框，询问你的操作。

![](/Manual/images/media/13/file_replace.png)

此对话框的目的是为你提供有关现有文件（已存在于目标文件夹中的文件）和新文件（你正在复制的文件）的足够信息，以帮助你决定要采取什么操作。

##### 基本信息

为这两个文件提供基本信息为 **名称**、**位置**、**大小**、**日期**（上次修改日期）和 **描述**（文件的描述）。当此信息在两个文件之间不同时，它会以 **粗体** 显示，以便于直观看到这两个文件存在哪些差异（位置除外，因为位置几乎始终不同，突出显示位置会使更重要的差异更难以注意到）。该对话框还使用两个小图标来指示哪个文件较大、哪个较新。

##### 缩略图

如果可能，还会为这两个文件列表缩略图图像，如果没有，则会显示文件图标。缩略图（或图标）具有一些额外功能：

- 如果为文件列表缩略图，将鼠标悬停在缩略图顶部会显示一个较大的预览图像。
-  يمكنك右键单击缩略图或图标以显示文件的上下文菜单。
-  يمكنك双击缩略图或图标来打开文件。

右键单击文件缩略图（或图标）时显示的上下文菜单可以使用 [文件类型](/Manual/file_types/README.zh.md) 系统进行自定义。例如，你可以添加一条命令以使用外部比较工具来比较这两个文件。

##### 继续复制文件

从根本上来说，你需要决定是否仍要复制该文件。如果你 **确实** 仍要复制该文件，则可用的选项有：

![](/Manual/images/media/13/replace_-_replace.png)

- **替换：**将传入文件复制到现有文件的上方。你可以单击按钮的主体部分来执行此操作。或者，单击按钮右侧的箭头以打开菜单，然后选择第一个选项。
- **全部替换：**替换当前文件，并在操作期间自动替换任何后续冲突文件。你可以使用菜单选择此选项，或者作为快捷方式，在单击 **替换** 按钮时按住 <kbd>Shift</kbd> 键。
- **重命名新文件：**自动选择传入文件的备用名称，以便它和现有文件并行存在。（若要手动指定新名称，请参阅下文。）作为快捷方式，可以通过按住 <kbd>Ctrl</kbd> 并单击按钮来访问菜单项。
- **全部重命名新文件：**自动选择传入文件的备用名称及所有后续冲突文件。作为快捷方式，按住 <kbd>Ctrl+Shift</kbd>。
- **重命名旧文件：**自动选择现有文件的备用名称，以便它和传入文件并行存在。作为快捷方式，按住 <kbd>Alt+Ctrl</kbd>。
- **全部重命名旧文件：**自动选择现有文件的备用名称及所有后续冲突文件。作为快捷方式，按住 <kbd>Alt+Shift</kbd>。
- **保留较新的：**将传入文件复制到现有文件的上方，但仅当传入文件的修改时间比现有文件更新时才执行此操作。否则，保留现有文件不变，根本不复制传入文件。（这是通过比较两个文件的 **修改** 时间戳来完成的。如果两个时间戳相同，则会跳过传入文件。）
- **保留较新的（全部）：**对于此以及所有后续冲突，如果传入文件的修改时间较新，则将传入文件复制到现有文件的上方，否则跳过它。

你还可以使用 [复制文件/确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md) 配置页上的选项将选定的 [重命名预设](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.zh.md) 添加到 **替换**下拉菜单中。

除了上面讨论的自动重命名选项外，你还可以手动编辑传入文件的名称。如果编辑了名称，则 **替换** 按钮会变为 **重命名** 按钮，单击该按钮将使用指定名称复制传入文件并将现有文件保留原样。

文件名编辑字段响应 [内联重命名](../renaming_files/inline_rename.zh.md) 功能支持的相同（可配置）控件键。

##### 放弃复制文件

如果你决定 **不想** 复制该文件，则可用的选项有：

![](/Manual/images/media/13/replace_-_skip.png)

- **跳过：**跳过此文件。不会复制传入文件，现有文件保持不变。你可以单击按钮的主体部分来执行此操作。或者，单击按钮右侧的箭头以打开菜单，然后选择第一个选项。
- **全部跳过：**跳过此文件，并在操作期间跳过所有后续冲突文件。你可以使用菜单选择此选项，或者作为快捷方式，在单击 **跳过** 按钮时按住 <kbd>Shift</kbd> 键。
- **跳过相同的：**如果传入文件和现有文件的 **大小** 和 **修改** 时间戳相同，则跳过此文件和任何后续文件。*请注意，不比较实际的文件内容！*对于两个文件大小或修改时间戳不同的后续冲突，系统仍会提示你。你可以按住 <kbd>Ctrl</kbd> 并单击按钮作为快捷方式。

你还可以通过单击 **中止** 按钮或关闭对话框来中止整个操作。

##### 恢复 FTP 传输

如果你正在将文件复制到或从 [FTP 站点](/Manual/ftp/README.zh.md) 中复制，并且远程 FTP 服务器支持 *恢复*，你还可以选择 **恢复** 复制（以及一个 **全部恢复** 下拉菜单）。如果你选择 **恢复** 选项，Opus 将尝试恢复文件传输在（可能）中断之前的状态。例如，如果你正在复制的文件为 100 KB，而现有文件仅为 50 KB，Opus 将从 50 KB 标记开始传输数据。此选项仅在现有文件小于新文件时可用。选择此选项时，你需要确定自己在做什么，因为如果你意外恢复复制了错误的文件，很容易导致文件损坏。