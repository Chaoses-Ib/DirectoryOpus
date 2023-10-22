# FTP Connect

The FTP Connect dialog lets you make a quick connection to an FTP site without going through the [FTP Address Book](ftp_address_book/RAEDME.md). To access this function, select the **FTP Connect** command from the FTP menu on the toolbar.

![](/Manual/images/media/ftp_connect.png) 

You can also right-click the FTP item in the tree and choose **FTP Connect** from the context menu.

![](/Manual/images/media/ftp_connect_dialog.png)

The options available in the **FTP Connect** dialog are:

- **FTP host**: This is the host address (domain name or IPv4 address) of the FTP site to connect to. The drop-down attached to this control displays the contents of your [FTP Address Book](ftp_address_book/RAEDME.md), and selecting a site from here will populate the fields of the dialog with the information for that site. For example, you could use this to connect to a site from your address book with a different username to the one stored in the site entry.
- ![](/Manual/images/media/ftp_connect_-_recall.png): This is the *recall* button. Clicking this button will recall the details of the last site you connected to through the **FTP Connect** dialog.
- **Connection**: Select the FTP connection type from the drop-down. The available options are:                                                            
  - **Standard Connection**: A normal, unencrypted [FTP](http://en.wikipedia.org/wiki/FTP) connection.
  - **Secure TLS Explicit**: An encrypted (secure) FTP connection. This uses [Explicit FTPS](http://en.wikipedia.org/wiki/FTPS#Explicit) over TLS.
  - **Secure SSL Implicit**: An encrypted (secure) FTP connection. This uses [Implicit FTPS](http://en.wikipedia.org/wiki/FTPS#Implicit) over SSL.
  - **Secure SFTP via SSH**: An encrypted (secure) FTP connection. This uses [SFTP via the SSH](http://en.wikipedia.org/wiki/SSH_file_transfer_protocol) protocol.

- **Port**: The port that the remote FTP server listens on. The default ports (which are the most commonly used) are **21** for standard FTP and explicit FTPS, **990** for implicit FTPS and **22** for SFTP via SSH. You can change the port number if needed.
- **Use PASV (passive) mode**: When Opus initiates a file transfer to or from a remote server, a separate data connection is established to the site. This can be established in [two ways](http://en.wikipedia.org/wiki/FTP#Protocol_overview). *Active* (PORT) mode is where Opus tells the remote site to connect to a specific data port on your machine - the remote server connects to you for the data transfer. *Passive* (PASV) mode is where Opus asks the server for a port to connect to - in this case, Opus connects to the server for the data transfer. Passive mode is often needed when you are behind a firewall, or your local network is using [NAT](http://en.wikipedia.org/wiki/NAT) (network address translation) - any time the remote server may not be able to establish a direct connection to you, you should use passive mode.

This is a "tri-state" checkbox - it has the normal states of on (![](/Manual/images/media/tristate_-_2.png)) and off (![](/Manual/images/media/tristate_-_1.png)), as well as a third state (![](/Manual/images/media/tristate_-_3.png)). In the third state the passive-mode setting will come from the site's address book entry (if a site was selected from the drop-down list) or from your default FTP settings, defined at the top of the FTP address book.  
\* **Anonymous login**: Turn this option on if you wish to make an anonymous connection to the site (if the site allows it). If you make an anonymous connection you don't need a username and password to login.

- **User name**: If not using an anonymous login, specify your user name (login name) for the FTP site here.
- **Password**: If not logging in anonymously, enter your password for the FTP site here.
- **Remote dir**: If you specify a directory path here, Opus will attempt to automatically change directory to this folder after connecting to the site. If you leave this empty the starting directory on the site will be defined by the remote FTP server.

As well as the **FTP Connect** command, you can also make an ad-hoc connection to an FTP site by simply entering the URL in the location field. For example, to connect anonymously to the Microsoft FTP server, click in the location field and enter [ftp://ftp.microsoft.com](ftp://ftp.microsoft.com/) and press the **Enter** key. You can also use this method to connect with a username and password, for example:

![](/Manual/images/media/ftp_connect_manually.png) 
