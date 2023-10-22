# Email

Opus lets you send files via email with the **ZIP and Email Files** command (attached to the **Archive Files** drop-down on the toolbar). This provides a quick way to email someone some files without needing to create a new message in an email program and attach the files to it manually. The settings on this page let you configure how Opus sends the files. The **Send email via** drop-down lets you choose from three different methods; the one you pick will depends on your individual system and network.

1.  **Internal SMTP client\\**  
    This is the preferred method; it means Opus uses its own SMTP client to connect to a mail server and send the email directly. To use this method you must have access to an SMTP server that will accept relay messages. For home users, your ISP will usually provide this - corporate users however may not have access to an SMTP server directly. The settings for this option are:
    - **Email address**: This is the email address that will be used as the 'from' address for messages sent from within Opus.
    - **Name**: This is the (your) name that will be used as the 'from' name for messages sent from within Opus.
    - **SMTP Server**: This is the domain name or IP address of the relaying SMTP server to use. You can also specify the **Port** if the default of 25 isn't correct.
    - **Use SSL/TLS**: Turn this on if the server requires the use of SSL or TLS encryption. This option is enforced if sending through GMail. You can set **SSL** or **TLS** explicitly, or choose **Automatic** to have Opus determine the correct protocol automatically.
    - **Server requires authentication**: If your SMTP server requires authentication to relay messages, turn this option on and enter the **Username** and **Password** supplied by your ISP or network administrator.
    - **Maximum simultaneous SMTP threads**: This defines the maximum number of simultaneous outgoing messages - if more messages than this are sent at once the additional messages will be queued.  
      - **mailto: emulation**

This method uses the system registered associations for **mailto:** links to trigger an email message in your default email client. If you don't have an email client that handles mailto: links installed then this method won't work. Outlook is an example of a client that does provide support for mailto: links.  
- **MAPI client**

This method uses the MAPI system to invoke your default email handler. MAPI is rather out-dated these days and not all email programs support this option.
