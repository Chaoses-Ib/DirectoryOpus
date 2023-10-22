# Site Page

The **Site** page is where you specify the basic configuration for a site entry in the [FTP Address Book]().

- **Site name**: This specifies the name of the site as shown in the address book.  
  \* **Comment**: This lets you specify a comment for the site entry; as well as being displayed here, it is displayed in the **Description** column in the file display if you select the FTP folder in the tree.  
  \* **Connection**: This is how you specify the connection type for the FTP site. The available options are:  
  \* **Standard Connection**: A normal, unencrypted [FTP](http://en.wikipedia.org/wiki/FTP) connection.
  - **Secure TLS Explicit**: An encrypted (secure) FTP connection. This uses [Explicit FTPS](http://en.wikipedia.org/wiki/FTPS#Explicit) over TLS.
  - **Secure SSL Implicit**: An encrypted (secure) FTP connection. This uses [Implicit FTPS](http://en.wikipedia.org/wiki/FTPS#Implicit) over SSL.
  - **Secure SFTP via SSH**: An encrypted (secure) FTP connection. This uses [SFTP via the SSH](http://en.wikipedia.org/wiki/SSH_file_transfer_protocol) protocol.  
    Please note that the secure FTP options require the purchase of the optional *Advanced FTP* feature.        
    \* **Host address**: The host address of the FTP site. This can be specified as either its domain name (e.g. **ftp.microsoft.com**) or its IPv4 address (e.g. **64.4.17.175**).  
    \* **Port**: The port that the remote FTP server listens on. The default ports (which are the most commonly used) are **21** for standard FTP and explicit FTPS, **990** for implicit FTPS and **22** for SFTP via SSH. You can change the port number if needed.  
    \* **Anonymous login**: Turn this option on if you wish to make an anonymous connection to the site (if the site allows it). If you make an anonymous connection you don't need a username and password to login. The **Anonymous password** specified in the [Default Settings](default_settings.md) will be used when making the connection.  
    \* **User name**: If not using an anonymous login, specify your user name (login name) for the FTP site here.  
    \* **Authentication**: Use this to select the authentication method if not using an anonymous login. You can choose from the following options:  
    \* **Ask for password**: Select this if you want Opus to ask you for your password whenever you connect to the site.
  - **Use stored password**: You can enter your password in the **Password** field below and Opus will authenticate connections automatically. Note that the system administrator can disable the storing of passwords; see the bottom of this page for details.
  - **Use private key file**: For SFTP connections you can specify a private key file that's used to authenticate. If the key file has a passphrase you will be prompted for the passphrase during the connection process and given the option to save it for the future.  
    \* **Password**: As an alternative to the above option, enter your password for the FTP site here if you want Opus to remember it in the configuration for the site. The password will be masked when displayed unless the **Show site passwords in plain text** option is turned on on the [Default Settings](default_settings.md) page.  
    \* **Private key file**: For SFTP connections, you can set the **Authentication** method to **Use private key file**, and then use this field to specify the filename of the key file to use.   
    \* **Initial directory**: If you specify a directory path here, Opus will attempt to automatically change directory to this folder whenever it connects to the site. If you leave this empty the starting directory on the site will be defined by the remote FTP server. If you turn on the **Keep last directory** option on the [Network](network_page.md) page, Opus will automatically update this field with the current directory when you disconnect from the site.  
    \* **Adjust directory and file dates for site time zone**: Set this to have file timestamps automatically adjusted to compensate for the timezone of the remote FTP server. If turned on you must select the timezone of the remote server from the drop-down list. You can also turn on the **Adjust for daylight saving changes** option to have Opus automatically compensate for daylight saving time (summer time) when adjusting timestamps.

The first entry in the drop-down list is **Automatic (Serv-U)**. This is a special option for when the remote FTP site is running the *Serv-U* software, which has special provisions for timezone handling.

For security in a corporate environment, it's possible to prevent Opus from saving FTP passwords, using an administrator-only registry setting. To do this, set the **PreventSaveFTPCredentials** value under **HKEY_LOCAL_MACHINE\Software\GPSoftware\Directory Opus** to **DWORD:1**.

  
