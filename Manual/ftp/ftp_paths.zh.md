# FTP 路径

FTP 位置在内部使用 URL 风格路径格式引用，前缀为 **ftp://**。此路径的完整格式如下：

**    ftp://<用户>:<密码>@<主机>:<端口>/<文件夹>**

因此，如果你在 *bigcompany.com* FTP 站点的用户名为 *jon*，密码为 *apple*，你可以使用路径字符串 **[ftp://jon:apple@bigcompany.com/](ftp://jon:apple@bigcompany.com/)** 建立连接。你可以在位置字段中输入这种类型的路径，或者在按钮和热键中使用它，将内部命令设置为自动使用 FTP。例如，你可以[设置一个按钮或热键](/Manual/customize/creating_your_own_buttons/README.zh.md) 使用原始命令 **复制到“[ftp://jon:apple@bigcompany.com](ftp://jon:apple@bigcompany.com)”** 自动将选定文件复制（上传）到此站点。

Opus 内部命令还支持为 **[FTP 通讯录](ftp_address_book/README.zh.md)** 中列出的站点使用简写符号。你可以使用通讯录条目的名称，前面加上一个星号符号，来代替 **ftp://** 风格的路径。

![](/Manual/images/media/ftp_shorthand.png) 

修改后指向通讯录条目的上述命令将为 **复制到 @Work\BigCompany**。以这种方式使用通讯录的优点在于，当站点用于时，站点当前设置会从通讯录条目中获取 - 因此，你对条目的配置所做的任何更改都会自动反映在引用该站点的任何命令中。