# Special Page

The **Special** page lets you configure certain advanced options for an FTP site entry in the [FTP Address Book]().

The available options are:

- **Compression**: The use of zlib compression can be enabled to improve FTP throughput. You can choose from *None* (no compression), *Zlib for LIST only* (directory listings are compressed, but not file transfers) and Zlib for all transfers (both directory listings and file transfers are compressed). Note that when transferring binary files such as **.zip** or **.jpg** or other files that are already compressed, zlib compression will have little to no effect and may even make the transfer slower! When using compression you can choose the level (how much compression is applied) from 1 to 9. The higher the level of compression the greater the potential size saving but the more CPU power is required.
- **SSL Data Channel - Use Clear Data**: When using secure FTP via SSL, you have the option to encrypt just the control connection (which is where your login details are transmitted), or both the control and data connections. There's usually no reason to encrypt the data transfer - it's normally just your username and password that you want encrypted, and encrypting the data can slow down file transfers. Turn on the **Use Clear Data** option to specify that you don't want the data connection encrypted.
- **VMS Settings**: Lets you configure several options specific to VMS servers.
  - **Display all file versions**: VMS filesystems may store multiple versions of each file. Turn this on to see all of the versions.
  - **Escape characters**: Some VMS servers add extra escape characters before spaces and dots. Turn this on to correct for the additional escape characters.
  - **Show file versions as description**: Show VMS file version numbers in the file display's Description column.

- **Limit data ports**: This lets you limit the range of data ports Opus will use for data connections when transferring files.

 
