# 操作工具栏

此工具栏包含与文件和文件夹操作相关命令。顶级按钮（**复制文件**等）可快速访问最常用的文件功能，而附加在这些按钮上的下拉菜单中包含与父按钮相关的更复杂或使用频率较低命令（因此，例如，**复制文件**下拉菜单中包含**另存副本**和**复制**命令）。

大多数这些按钮要求在它们可用之前选择一个或多个文件或文件夹。它们通常使用[源地址和目标地址](/Manual/basic_concepts/source_and_destination.zh.md)概念——**复制文件**按钮将把所有从当前源文件列表中选中的项目复制到目标地址。在[双栏](../../dual_display/README.zh.md)文件窗口中，目标地址始终是非激活文件列表。如果目标文件列表不可用，Opus 将提示你选择目标文件夹。

![](/Manual/images/media/13/operations_toolbar.png)

##### 复制文件

父按钮将[复制](/Manual/file_operations/copying_moving_and_deleting_files/README.zh.md)选中的文件和文件夹到目标文件夹。附加在此按钮中的下拉菜单包含以下附加命令：

* **另存副本**：此命令支持你为复制的文件[提供新的文件名](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)——一次一个或使用通配符批量为所有选定的文件提供文件名。
* **复制**：此命令会在当前目录中复制选定的文件（即，在同一位置复制文件，不将它们复制到目标地址）。你必须为复制的文件和文件夹[提供新的文件名](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)。
* **更新全部**：此命令将选定的文件复制到目标地址，如果它们a) 不存在于目标地址中，或 b) 存在但比目标地址中的文件新（有关更多信息，请参阅[复制更新的文件](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。
* **更新现有**：此命令仅在选定的文件已经存在且比目标地址中的文件新时才会将选定的文件复制到目标地址（有关更多信息，请参阅[复制更新的文件](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。
* **发送到**：此子菜单包含系统***发送到***菜单，可将选定的文件和文件夹发送到不同目标地址。使用此下拉菜单相当于对文件右击，然后从*发送到*上下文菜单中进行选择。
* **复制过滤器**：此命令在当前文件窗口中打开或关闭递归[复制过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。

##### 移动文件

父按钮将[移动](/Manual/file_operations/copying_moving_and_deleting_files/README.zh.md)选中的文件和文件夹到目标地址。下拉菜单包含以下附加命令：

* **移动为**：此命令支持你在移动文件时为它们[提供新的文件名](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)——一次一个或使用通配符批量为所有选定的文件提供文件名。

##### 重命名

父命令支持你使用**[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)**对话框来重命名选定的文件和文件夹。下拉菜单包含一些关于原始重命名命令如何“编写脚本”来执行特殊重命名任务的示例：

* **使用简单重命名**：打开此开关可使**重命名**按钮触发简单重命名对话框（仅支持基本的通配符重命名），而不是高级重命名对话框。
* **单词大写**：将文件名中每个单词的首字母大写，将所有其他字母小写。
* **设为 Web 安全**：通过移除任何可能在 URL 中引起问题字符（除了 `-`, `0-9`, `a-z`, `A-Z`, `.`, `_`, `]` 和 `+`，其他所有字符都应移除），使文件名适合在网站中使用。
* **对文件编号**：在所选文件名前插入递增数字。此功能作为一个 VBScript [重命名脚本](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.zh.md)来实现，因此提供了一个更为复杂重命名功能良好的示例。
* **时间戳名称**：将日期和时间戳追加到选定文件名的后面。
* **下划线转换为空格**：将文件名中任何下划线替换为空格。

##### 新建文件夹

父命令显示一个对话框，允许你在活动文件列表中新建一个文件夹。如果你当前位于[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)根文件夹中，将新建一个集合，如果你当前位于[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md)根文件夹中，将新建一个库。下拉菜单包含以下附加命令：

* **新建压缩包**：此命令[新建一个压缩包](/Manual/file_operations/creating_archives/README.zh.md)（系统将提示你选择压缩包类型和压缩包格式适用的任何选项）。
* **新建文本文档**：此命令在当前文件夹中新建一个空文本文档（**.txt** 文件）。这相当于右击文件列表背景，然后从上下文菜单中选择**新建 -\> 文本文档**。
* **新建**：此子菜单显示系统**新建**菜单，支持你新建不同类型的新文件。
* **新建日期文件夹**：在当前文件列表中新建一个文件夹，其名称为当前日期和时间。
* **移至日期文件夹**：使用当前日期和时间新建一个文件夹，并将所有选定文件和文件夹自动移动到该文件夹。

##### 删除

父按钮将删除所有选定的文件和文件夹。默认情况下，如果可能，回收站将用于提供可撤消的删除，但这可以通过[配置](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)进行修改。在附加的下拉菜单中可找到以下附加命令：

* **安全擦除**：此命令使用[安全删除](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.zh.md)算法删除所有选定的文件，这使得其他人非常难以（如果不是不可能）恢复所删除信息。
* **从集合移除**：在[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)中使用时，此命令从该集合中移除所有选定的项目。如果你对集合项目使用父**删除**命令，则真实的​​文件和文件夹将被删除——使用**移除**命令可以从集合中将它们移除，而无需删除实际文件。
- **删除过滤器**：此命令在当前文件窗口中开启或关闭递归[删除过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。

**##### 管理员**

此按钮在当前文件窗口中打开[管理模式](/Manual/file_operations/uac_and_administrator_mode.zh.md)。

**##### 压缩包文件**

父命令可让你将所有选中的文件和文件夹添加到当前文件夹中的[新压缩包](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.zh.md)（系统会提示你输入压缩包类型和参数）。下拉菜单中包含以下其他命令：

- **文件到单独压缩包**：将所有选中的项目添加到单独的压缩包中（每个选中的文件或文件夹一个压缩包）。此命令默认创建 ZIP 文件；你可以通过编辑命令来更改使用的压缩包格式（如将 **Copy ARCHIVE=single** 更改为 **Copy ARCHIVE=.7z,single** 以默认使用 7zip）。
- **文件到目标压缩包**：这与父 **压缩包文件** 命令相同，只是新压缩包将创建在目标文件中。
- **将 ZIP 文件发送到电子邮件**：将选定的项目添加到 ZIP 压缩包，并通过电子邮件将压缩包发送给收件人（系统会提示你输入电子邮件地址）。
- **解压到文件夹**：将任何选定压缩包中的内容解压到以提取的压缩包命名的新的文件夹中（如 ***Pictures.zip*** 的内容将解压到一个名为 ***Pictures*** 的新文件夹中）。
- **解压到目标**：将任何选定压缩包中的内容解压到目标文件夹中。
- **解压到目标文件夹**：将任何选定压缩包中的内容解压到目标中的新文件夹中。

**##### 属性**

父按钮会显示所有选定项目的系统属性对话框。下拉菜单中的命令为：

      * **属性**：显示 **[[:file_operations:changing_attributes|更改属性和时间]]** 对话框，你可以用它来修改选定项目的属性和日期/时间戳。 
      * **描述**：显示 **[[:file_operations:file_descriptions|设置描述]]** 对话框，你可以用它为选定的项目分配一个描述字符串。 
      * **编辑元数据**：显示 **[[:file_operations:editing_metadata|设置元数据]]** 对话框，你可以用它来编辑任何选定文件的元数据。 
      * **设置**标记：此子菜单让你可以为选定的文件和文件夹分配一个标记。有标记的文件可以显示为不同的颜色和/或字体样式。使用配置中的 **[[:preferences:preferences_categories:labels:label_definitions|标记定义]]** 页面来创建和编辑你的标记。

**##### 幻灯片**

此按钮会启动选定的所有图像文件的[幻灯片](/Manual/additional_functionality/viewing_images/README.zh.md)。如果没有选定的文件，当前文件夹中的所有图像文件将被显示。下拉菜单中的命令为：

      * **显示图片**：在独立的查看器中显示选定的文件。 
      * **播放声音**：在内部声音播放器中播放选定的文件。

**##### 帮助**

“帮助”菜单包含通往各种实用网站的链接（[GP Software](http://www.gpsoft.com.au/) 支持站点以及[Opus 资源中心](http://resource.dopus.com/) 等主页），以及通往此帮助站点 itself 和检查更新功能的链接。它还有 **安全屏幕截图** 命令，你可以用它来截取 Opus 的屏幕截图，并且会遮蔽可能比较敏感的文件名称。