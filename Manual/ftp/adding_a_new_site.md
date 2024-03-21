# Adding a new Site

To add a new FTP site entry in the [FTP Address Book](ftp_address_book/README.md), click the **New FTP Site** (![](/Manual/images/media/favorites_-_add.png)) button or right-click on the site list and choose the **New FTP Site** command. This displays the **Create New FTP Site** dialog, which lets you configure the basic parameters for the new FTP site.

The options available when creating a new site are:

- **Site name**: This specifies the name of the site as it will be shown in the address book.
- **Comment**: This lets you specify a comment for the site entry; as well as being displayed in the address book, it is displayed in the **Description** column in the file display if you select the FTP folder in the tree.
- **Connection**: This is how you specify the connection type for the FTP site. The available options are:
  - **Standard Connection**: A normal, unencrypted [FTP](http://en.wikipedia.org/wiki/FTP) connection.
  - **Secure TLS Explicit**: An encrypted (secure) FTP connection. This uses [Explicit FTPS](http://en.wikipedia.org/wiki/FTPS#Explicit) over TLS.
  - **Secure SSL Implicit**: An encrypted (secure) FTP connection. This uses [Implicit FTPS](http://en.wikipedia.org/wiki/FTPS#Implicit) over SSL.
  - **Secure SFTP via SSH**: An encrypted (secure) FTP connection. This uses [SFTP via the SSH](http://en.wikipedia.org/wiki/SSH_file_transfer_protocol) protocol.  
    Please note that the secure FTP options require the purchase of the optional *Advanced FTP* feature.      
- **Host address**: The host address of the FTP site. This can be specified as either its domain name (e.g. **ftp.microsoft.com**) or its IPv4 address (e.g. **64.4.30.34**).
- **Port**: The port that the remote FTP server listens on. The default ports (which are the most commonly used) are **21** for standard FTP and explicit FTPS, **990** for implicit FTPS and **22** for SFTP via SSH. You can change the port number if needed.
- **Anonymous login**: Turn this option on if you wish to make an anonymous connection to the site (if the site allows it). If you make an anonymous connection you don't need a username and password to login.
- **User name**: If not using an anonymous login, specify your user name (login name) for the FTP site here.
- **Ask for password**: Set this checkbox if you want Opus to ask you for your password whenever you connect to the site. You might want this if you don't want to store your site passwords in the Opus configuration. This is a "tri-state" checkbox - it has the normal states of on (![](/Manual/images/media/tristate_-_2.png)) and off (![](/Manual/images/media/tristate_-_1.png)), as well as a third state (![](/Manual/images/media/tristate_-_3.png)). The third state means "use default" - the state of the global **Always ask for password for login** option on the FTP Address Book's [Default Settings](ftp_address_book/default_settings.md) page will be used.
- **Password**: As an alternative to the above option, enter your password for the FTP site here if you want Opus to remember it in the configuration for the site. The password will be masked when displayed unless the **Show site passwords in plain text** option is turned on on the FTP Address Book's [Default Settings](ftp_address_book/default_settings.md) page.
- **Initial directory**: If you specify a directory path here, Opus will attempt to automatically change directory to this folder whenever it connects to the site. If you leave this empty the starting directory on the site will be defined by the remote FTP server.
- **Adjust directory and file dates for site time zone**: Set this to have file timestamps automatically adjusted to compensate for the timezone of the remote FTP server. If turned on you must select the timezone of the remote server from the drop-down list. You can also turn on the **Adjust for daylight saving changes** option to have Opus automatically compensate for daylight saving time (summer time) when adjusting timestamps.

The first entry in the drop-down list is **Automatic (Serv-U)**. This is a special option for when the remote FTP site is running the *Serv-U* software, which has special provisions for timezone handling.

All these site settings (and others) can be changed through the address book once the site has been added.
