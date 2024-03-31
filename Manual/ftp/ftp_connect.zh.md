# FTP 连接

FTP 连接对话框允许您快速连接到 FTP 站点，而无需使用 [FTP 通讯录](ftp_address_book/README.zh.md)。要访问此功能，请从工具栏中的 FTP 菜单中选择 **FTP 连接** 命令。

![](/Manual/images/media/ftp_connect.png) 

您还可以右键单击树中的 FTP 项，然后从上下文菜单中选择 **FTP 连接**。

![](/Manual/images/media/ftp_connect_dialog.png)

**FTP 连接** 对话框中提供了以下选项：

- **FTP 主机**：这是要连接到的 FTP 站点的主机地址（域名或 IPv4 地址）。附加到此控件的下拉列表显示 [FTP 通讯录](ftp_address_book/README.zh.md) 的内容，并且从此处选择一个站点会使用该站点的相关信息填充对话框中的字段。例如，您可以使用此功能从通讯录中连接到一个站点，并使用与站点条目中存储的用户名不同的用户名。
- ![](/Manual/images/media/ftp_connect_-_recall.png)：这是 *“调取”* 按钮。单击此按钮将调取最后一次通过 **FTP 连接** 对话框连接到的站点的详细信息。
- **连接**：从下拉列表中选择 FTP 连接类型。提供的选项包括：                                                            
  - **标准连接**：常规的、未加密的 [FTP](http://en.wikipedia.org/wiki/FTP) 连接。
  - **安全 TLS 显式**：加密的（安全）FTP 连接。它使用 TLS 上的 [明确 FTPS](http://en.wikipedia.org/wiki/FTPS#Explicit)。
  - **安全 SSL 隐式**：加密的（安全）FTP 连接。它使用 SSL 上的 [隐式 FTPS](http://en.wikipedia.org/wiki/FTPS#Implicit)。
  - **通过 SSH 的安全 SFTP**：加密的（安全）FTP 连接。它使用 [通过 SSH 的 SFTP](http://en.wikipedia.org/wiki/SSH_file_transfer_protocol) 协议。

- **端口**：远程 FTP 服务器监听的端口。标准端口（最常用的端口）是标准 FTP 和明确 FTPS 的 **21**，隐式 FTPS 的 **990**，以及通过 SSH 的 SFTP 的 **22**。您可以根据需要更改端口号。
- **使用 PASV（被动）模式**：当 Opus 启动到或从远程服务器的文件传输时，将向站点建立单独的数据连接。可以通过 [两种方式](http://en.wikipedia.org/wiki/FTP#Protocol_overview)建立此连接。*活动*（PORT）模式是 Opus 告诉远程站点连接到您计算机上的特定数据端口 - 远程服务器连接到您进行数据传输。*被动*（PASV）模式是 Opus 向服务器询问要连接到的端口 - 在这种情况下，Opus 连接到服务器进行数据传输。当您处于防火墙之后或您的本地网络使用 [NAT](http://en.wikipedia.org/wiki/NAT)（网络地址转换）时，通常需要被动模式 - 在任何远程服务器可能无法与您建立直接连接时，您都应使用被动模式。

这是一个“三态”复选框 - 它具有正常的状态打开 (![](/Manual/images/media/tristate_-_2.png)) 和关闭 (![](/Manual/images/media/tristate_-_1.png))，以及第三个状态 (![](/Manual/images/media/tristate_-_3.png))。在第三种状态，被动模式设置将来自站点的通讯录条目（如果从下拉列表中选择了站点）或来自您的默认 FTP 设置，这些设置定义在 FTP 通讯录的顶部。 \* **匿名登录**：如果您希望与该站点进行匿名连接（如果该站点允许），请打开此选项。如果您进行匿名连接，则无需用户名和密码即可登录。

- **用户名**：如果您未进行匿名登录，请在此处指定您在 FTP 站点的用户名（登录名）。
- **密码**：如果您未通过匿名方式登录，请在此处输入 FTP 站点的密码。
- **远程目录**：如果您在此处指定目录路径，Opus 会尝试在连接到站点后自动将目录更改为该文件夹。如果您将其留空，站点上的起始目录将由远程 FTP 服务器定义。

除了 **FTP 连接** 命令之外，您还可以只需在位置字段中输入 URL 即可与 FTP 站点建立即时连接。例如，要以匿名方式连接到 Microsoft FTP 服务器，请单击位置字段并输入 [ftp://ftp.microsoft.com](ftp://ftp.microsoft.com/)，然后按 **Enter** 键。您还可以使用此方法使用用户名和密码进行连接，例如：

![](/Manual/images/media/ftp_connect_manually.png) 