# Proxy Page

The **Proxy** page lets you configure Opus to use a proxy server when connecting to a site in the [FTP Address Book](). A proxy server is an "intermediary" server that accepts a connection from one computer (the "client") and establishes an outgoing connection to the target server (the "host") on the client's behalf. They are often used in corporate networks to provide security or caching features. You should consult your network administrator if you're not sure what proxy settings you need to use.

Turn on the **Connect via FTP Proxy** to enable the use of a proxy server. When this is enabled, the options for the proxy are:

- **Proxy type**: Use this drop-down to specify the type of proxy server being used. Most proxy types specify the use of a standard FTP proxy server, and let you control how your username and password are sent to the server (there are several variants like **USER username@host**, **USER user@proxyuser@host**, etc). The **Custom Template** option lets you have complete control over the way your user details are sent. You can also choose to use a **SOCKS4** or **SOCKS5** proxy from this drop-down.
- **Proxy address**: Specify the host name or IPv4 address of the proxy server here.
- **Port**: Specify the port number that the proxy server listens on. For standard FTP proxies this is normally port **21**, and for SOCKS proxies this is normally **1080**.
- **Delimiter**: Specify the delimiter character used when sending your login details to the proxy server. This is normally the **@** character.
- **Proxy user name** and **Proxy password**: For some options in the **Proxy type** drop-down, the **Proxy user name** and **Proxy password** fields will appear. These let you supply different login credentials for the proxy server, instead of using the username and password for the remote FTP server.
- **SOCKS 5 Authentication**: When *SOCKS5* is chosen from the **Proxy type** drop-down, this option enables the display of the **Proxy user name** and **Proxy password** fields. Use this option if your SOCKS5 proxy requires authentication.

When **Custom Template** is selected from the **Proxy type** drop-down, you can fully control the connection string used to connect to the FTP proxy. This connection string is built from control codes that are used to insert your login details into the string. The codes you can use are:

- **%h**: Host name of the remote FTP site
- **%u**: User name for the FTP site
- **%p**: Password for the FTP site
- **%x**: User name for the proxy server
- **%y**: Password for the proxy server

You can specify separate templates for both the **USER** and **PASS** commands. See the examples given in the actual dialog for more information.
