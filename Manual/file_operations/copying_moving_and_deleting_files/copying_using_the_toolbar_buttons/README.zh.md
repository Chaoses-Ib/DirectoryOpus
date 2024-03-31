# 使用工具栏按钮进行复制

除了复制粘贴和拖放之外，复制文件的第三种方式是使用工具栏上的 **复制文件** 和 **移动** 按钮。

这些按钮使用 [来源和目标](/Manual/basic_concepts/source_and_destination.zh.md) 概念。选定的文件将从当前来源文件夹复制或移动到当前目标文件夹 - 如果没有当前目标文件夹，Opus 将提示您选择目标文件夹。

##### 复制文件

![](/Manual/images/media/13/copy_menu.png)

**复制文件** 按钮的附加下拉菜单包含以下文件复制命令：

- **复制文件**: 将选定的文件和文件夹复制到目标文件夹。
- **复制为**: 允许您输入新的文件名或提供一个通配符模式来 [在复制文件时重命名文件](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)
- **复制**: 在同一文件夹中创建选定文件的副本。
- **复制到包含日期的名称**: 创建选定文件的副本，其名称后跟当前日期。
- **全部更新**: 更新所有文件。仅复制在目标中不存在或存在但较新的文件。有关详细信息，请参见 [复制更新的文件](copying_updated_files/README.zh.md)。
- **更新现有**: 更新现有文件。仅复制在目标中已经存在且较新的文件。有关详细信息，请参见 [复制更新的文件](copying_updated_files/README.zh.md)。
- **创建快捷方式**: 在目标文件夹 (.lnk) 中创建指向所选文件的快捷方式。有关详细信息，请参见 [创建链接和连接](/Manual/additional_functionality/making_links_and_junctions.zh.md)。
- **创建高级链接**: 在目标文件夹中创建指向所选文件的交界处和软链接。有关详细信息，请参见 [创建链接和连接](/Manual/additional_functionality/making_links_and_junctions.zh.md)。
- **发送到**: 这会显示标准系统 *发送到* 菜单，允许您将选定的文件发送到各种位置。
- **启用复制过滤器**: 启用 [递归过滤器](../filtered_operations/README.zh.md)，它允许您有选择地复制子文件夹的内容。
- **复制设置**: 打开 [复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md) 偏好设置页面。

##### 移动

![](/Manual/images/media/13/move_menu.png)

**移动** 按钮的附加下拉菜单包含以下命令：

- **移动**: 将选定的文件和文件夹移动到目标。
- **移动为**: 输入新文件名或通配符模式以 [在移动文件时重命名文件](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)。
- **移动到包含日期的文件夹**: 创建一个以当前日期为名称的文件夹，并将选定的文件和文件夹移动到其中。

更多：

[复制时使用通配符](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)