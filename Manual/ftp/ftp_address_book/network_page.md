# Network Page

The **Network** page is where you specify various connection-related options for a site entry in the [FTP Address Book]().

The three sections this page is divided into (**Connection**, **Reconnect** and **Site-to-Site**) can all be individually enabled or disabled for any given site. When a section is set to **Use defaults**, the settings for that section come from the equivalent page in the [Default Settings](default_settings.md).

The **Connection** section specifies various connection-related options for the site:

- **Allow special directory names beginning with space**: Some FTP servers allow files and folders to be made inaccessible if they begin with a space character. With this option enabled Opus will compensate for leading spaces in file names and let you access them.
- **Keep last directory**: If this option is turned on, Opus will update the **Initial directory** field on the **[Site](site_page.md)** page with the current directory when you disconnect from the site. This lets you return to your most recently visited location the next time you reconnect to the site.
- **Rescan directory after change**: After you have copied files to a remote FTP site, it's possible for the idea Opus has of the remote directory contents to get out of sync with the server. This can especially be the case if the remote site doesn't support the setting of file timestamps. If you turn this option on, Opus will automatically refresh the directory listing whenever you copy a file to the server.
- **Use PASV (passive) mode**: When Opus initiates a file transfer to or from a remote server, a separate data connection is established to the site. This can be established in [two ways](http://en.wikipedia.org/wiki/FTP#Protocol_overview). *Active* (PORT) mode is where Opus tells the remote site to connect to a specific data port on your machine - the remote server connects to you for the data transfer. *Passive* (PASV) mode is where Opus asks the server for a port to connect to - in this case, Opus connects to the server for the data transfer. Passive mode is often needed when you are behind a firewall, or your local network is using [NAT](http://en.wikipedia.org/wiki/NAT) (network address translation) - any time the remote server may not be able to establish a direct connection to you, you should use passive mode.
- **Timeout**: This lets you modify the local network timeout for FTP transfers. You can try adjusting this if you experience excessive timeouts on active (PORT) connections. We recommend using PASV mode in most cases.

The **Reconnect** section specifies the behavior when automatically reconnecting a connection that has been lost:

- **Retry count** and **Delay**: If a connection attempt to the FTP server fails, this specifies how many times the connection will be retried, and how long between retries, before giving up and reporting an error.
- **Automatically reconnect if connection lost**: If the connection to a site is lost unexpectedly (e.g. due to a timeout at the server end, or a network glitch), Opus will try to automatically reconnect to the site if this option is on. If turned on Opus will display an error and you will need to attempt the reconnection manually.
- **Keep link alive** and **Delay**: This option lets you attempt to work around server timeouts by enabling a "keep alive" mode. If enabled, Opus will regularly send a dummy packet to the remote server, which should prevent the other end from timing out the connection. The **Delay** option lets you specify the delay between keep alive packets in seconds. Many FTP sites discourage keep-alive mechanisms; it's generally viewed as more polite to only stay connected to the site when needed, rather than indefinitely.

The **Site-to-Site** section lets you enable site-to-site transfers for the site. A site-to-site transfer can be used when you are copying files from one remote FTP site to another FTP site - if the remote servers support it, the file transfer can go direct from one site to the other without the data having to be relayed through your local computer. Not all servers support this behavior so if you find site-to-site transfers aren't working you can turn it off.

- **Attempt for uploads**: Attempts site-to-site transfers when uploading to this site from another FTP site.
- **Attempt for downloads**: Attempts site-to-site transfers when downloading to this site from another FTP site.

 
