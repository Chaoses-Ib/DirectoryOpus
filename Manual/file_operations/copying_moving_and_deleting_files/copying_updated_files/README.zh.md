# 复制已更新文件

有两种不同的方法可以自动复制已更新的文件（即使用更新的文件覆盖较早版本的文件）：

- **更新全部**和**更新现有文件**命令提供了一种简单的单向文件同步形式
- **[同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)**工具提供了一种完整的双向同步系统，让你可以看到并控制要复制或删除哪些文件

##### “更新”命令

**更新全部**和**更新现有文件**命令位于默认工具栏**复制文件**按钮上的下拉菜单中。

这两个命令是标准**复制文件**命令的变体，并依赖于[源和目标](/Manual/basic_concepts/source_and_destination.zh.md)概念。选定的文件将从当前源文件列表复制到目标文件夹，条件如下：

- **更新全部：**如果文件
  - 在目标中不存在，**或**
  - 在目标中存在，但大小或版本低于要复制的文件

- **更新现有：**如果文件
  - 在目标中存在，**且**
  - 大小或版本低于要复制的文件（可以修改此规则，详见下文）。

不符合这些条件的文件将被跳过。你可以使用内部**[复制](/Manual/reference/command_reference/internal_commands/copy.zh.md)**命令参数修改测试条件：

- 更新全部：**UPDATETOLERANCE**参数可用于控制时间戳在被视为“较早版本”之前可以相差多久。
- 更新现有：除了**UPDATETOLERANCE**之外，**UPDATEEXISTING**参数还可用于在比较中忽略文件大小或日期

有关这些参数的详细信息，请参阅内部**[复制](/Manual/reference/command_reference/internal_commands/copy.zh.md)**命令描述；有关工具栏按钮配置的信息，请参阅[定制](/Manual/customize/README.zh.md)部分。

更多信息：

[同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md)