# Default Settings

The **Default Settings** item in the [FTP Address Book]() is a special entry that lets you configure default parameters that apply to all your FTP sites. Individual sites can then override these parameters if desired.

When the **Default Settings** item is selected the **Site** tab changes to the **Global** tab, which lets you configure several global options that affect FTP in general.

- **Anonymous password**: This is the password used when connecting to an anonymous FTP site; some sites have a policy that you should use your own email address as the anonymous password, so you may want to change this setting.  
  \* **Global password**: This lets you configure a global password for the FTP address book. You can enter this password to reveal the details of individual site passwords, which are normally hidden. This defaults to **password** which obviously isn't very secure - we recommend you change this.  
  \* **Save password for newly added sites**: If this option is enabled and you add a new FTP connection to the address book using the **Add to Address Book** command in the **FTP** menu, Opus will automatically save the password to the address book entry.  
  \* **Cache site passwords**: This lets you enable or disable the caching of site passwords in memory, and how long they are cached for. If you don't store your passwords in the FTP address book, but instead prefer to enter them manually when connecting to a site, this option is useful as it can prevent you being repeatedly asked for the same password over and over again.  
  \* **Show site passwords in plain text**: If this option is turned on, the password field on the **Site** page for individual sites will display the stored password in plain text instead of masking it. You will need to enter the *global password* before this option can be enabled.  
  \* **Remember Quick Connect passwords**: When you connect to an FTP site using the **[FTP Connect](../ftp_connect.md)** command, Opus normally stores information about the last connection so that it can be quickly recalled next time you use the **FTP Connect** command. If you turn off this option Opus will not store the password for the last connection.

 
