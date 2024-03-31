# FTP 地址簿

FTP 地址簿可让你维护 FTP 站点集合，每个 FTP 站点都有自己的登录详细信息和其他配置。如果你有大量站点需要跟踪，你还可以将它们组织到文件夹中。要显示 FTP 地址簿，请从默认工具栏的 FTP 菜单或文件夹树中 FTP 项的右键单击上下文菜单选择编辑地址簿命令。

![](/Manual/images/media/ftp_addresses_-_left.png) 

FTP 地址簿对话框的左侧显示了你的地址簿条目。顶部的工具栏用于添加或编辑条目；**新建 FTP 站点** (![](/Manual/images/media/favorites_-_add.png)) 按钮[将新站点添加到列表](adding_a_new_site.zh.md)，**复制 FTP 站点** (![](/Manual/images/media/filters_-_duplicate.png)) 复制现有站点，**新建文件夹** (![](/Manual/images/media/favorites_-_folder.png)) 按钮创建一个可用于组织站点的文件夹，**重命名** (![](/Manual/images/media/filters_-_rename.png)) 按钮重命名现有站点或文件夹，**删除** (![](/Manual/images/media/favorites_-_delete.png)) 按钮删除选定的站点或文件夹。

下拉 **连接** (![](/Manual/images/media/ftp_connect_button.png)) 按钮可让你在地址簿中建立与所选站点的连接。还有许多其他方式可用于连接到站点；主要只是在你编辑地址簿时才提供此类便利。

对话框顶部的 **文件** 菜单包含以下命令：

- **导入**：导入之前导出的地址簿文件。你可以使用导出/导入功能将你的地址簿从一台计算机复制到另一台计算机。导入地址簿时的选项有：                           
  - **导入到新文件夹**：导入的地址簿内容将放置在你现有地址簿的一个新文件夹中。
  - **与现有条目合并**：导入文件的内容将合并。与现有地址簿发生冲突的任何站点条目都将被覆盖。例如，当你用台式机上创建的新条目更新笔记本电脑时，可以使用此选项。
  - **替换所有现有条目**：你的现有地址簿将被完全丢弃，导入的文件将取代它。

- **导出**：将 FTP 地址簿导出到文件。然后，你可以在另一台计算机上使用导入功能进行导入。导出时的选项包括：                           
  - **导出所有条目**：你的整个地址簿都将导出。
  - **仅导出所选项目**：如果你在运行 **导出** 命令之前从地址簿中选择了一个文件夹或站点，则可以仅导出该文件夹或站点。
  - **从导出文件中删除 FTP 密码**：如果你启用此选项，则任何存储的密码都将从导出的文件中省略。如果你与工作同事共享一个 FTP 站点文件夹，你可能希望执行此操作；他们可以导入站点配置，并在其计算机上输入自己的密码，而且你不会向他们透露你的密码。

- **新建 FTP 站点**：创建一个新的 FTP 站点（与使用 ![](/Manual/images/media/favorites_-_add.png) 按钮相同）。
- **复制 FTP 站点**：复制所选 FTP 站点（与使用 ![](/Manual/images/media/filters_-_duplicate.png) 按钮相同）。
- **新文件夹**：在地址簿中创建一个新文件夹（与使用 ![](/Manual/images/media/favorites_-_folder.png) 按钮相同）。
- **创建快捷方式**：此命令为选定的 FTP 站点创建一个快捷方式，并将其放置在桌面上。双击快捷方式是在 Opus 中打开站点还是不在 Opus 中打开站点，取决于 Opus 是否被配置为系统 [默认 FTP 处理程序](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.zh.md#ftp)。你还可以使用拖放来创建到站点的快捷方式。
- **重命名**：重命名所选文件夹或站点（与使用 ![](/Manual/images/media/filters_-_rename.png) 按钮相同）。
- **删除**：删除所选文件夹或站点（与使用 ![](/Manual/images/media/favorites_-_delete.png) 按钮相同）。

**编辑** 菜单包含标准的 **复制** / **剪切** / **粘贴** 命令；你可以使用这些命令将设置从一个 FTP 站点复制到另一个 FTP 站点，或在文件夹之间移动站点。你还可以使用标准拖放技术重新排列地址簿。地址簿中列出的所有站点和文件夹都有一个上下文菜单，通过鼠标右键单击访问该上下文菜单 - 这是访问上述命令的另一种方式。

地址簿中的特殊 **[默认设置](/Manual/ftp/ftp_address_book/default_settings.zh.md)** 条目并不是一个真正的站点；相反，它允许你配置默认设置，这些默认设置适用于除非站点条目覆盖它们的全部 FTP 站点。每个站点的配置分为若干页面，每个页面包含一个或多个部分，并且可以将站点的各个部分设置为使用默认设置或在站点级别覆盖它们。

![](/Manual/images/media/ftp_addressbook_tabs.png) 

每个站点条目的页面包括：

- **[站点](/Manual/ftp/ftp_address_book/site_page.zh.md)**：定义该站点的名称、主机、用户和密码详细信息。对于 **默认设置** 项，**站点** 页将替换为 **全局** 页。
- **[网络](/Manual/ftp/ftp_address_book/network_page.zh.md)**：与连接到站点相关的各种选项。
- **[显示](/Manual/ftp/ftp_address_book/display_page.zh.md)**：定义从站点显示哪些消息，以及是否启用日志记录。
- **[索引](/Manual/ftp/ftp_address_book/index_page.zh.md)**：控制是否下载每个目录的索引文件（如果存在）。
- **[声音](/Manual/ftp/ftp_address_book/sounds_page.zh.md)**：允许你配置许多事件触发的声音；例如，你可以让在连接超时或发生错误时播放声音。
- **[其他](/Manual/ftp/ftp_address_book/misc_page.zh.md)**：与服务器功能和通信相关的各种设置。
- **[速度](/Manual/ftp/ftp_address_book/speed_page.zh.md)**：允许你在需要时选择限制上传和/或下载速度。
- **[特殊](/Manual/ftp/ftp_address_book/special_page.zh.md)**：针对服务器特定功能的各种高级设置。
- **[代理](/Manual/ftp/ftp_address_book/proxy_page.zh.md)**：允许你配置连接时要使用的代理服务器。

更多内容：

[默认设置](/Manual/ftp/ftp_address_book/default_settings.zh.md)  
[站点页面](/Manual/ftp/ftp_address_book/site_page.zh.md)  
[网络页面](/Manual/ftp/ftp_address_book/network_page.zh.md)  
[显示页面](/Manual/ftp/ftp_address_book/display_page.zh.md)  
[索引页面](/Manual/ftp/ftp_address_book/index_page.zh.md)  
[声音页面](/Manual/ftp/ftp_address_book/sounds_page.zh.md)  
[其他页面](/Manual/ftp/ftp_address_book/misc_page.zh.md)  
[速度页面](/Manual/ftp/ftp_address_book/speed_page.zh.md)  
[特殊页面](/Manual/ftp/ftp_address_book/special_page.zh.md)  
[代理页面](/Manual/ftp/ftp_address_book/proxy_page.zh.md)