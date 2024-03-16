# Email

Opus lets you send files via email with the **ZIP and Email Files** command (attached to the **Archive Files** drop-down on the toolbar). This provides a quick way to email someone some files without needing to create a new message in an email program and attach the files to it manually.

- **Email address**: This is the email address that will be used as the 'from' address for messages sent from within Opus.
- **Name**: This is the (your) name that will be used as the 'from' name for messages sent from within Opus.
- **SMTP Server**: This is the domain name or IP address of the relaying SMTP server to use.
- **Port**: SMTP port, usually 25 or 587.
- **Use SSL/TLS**: Turn this on if the server requires the use of SSL or TLS encryption. This option is enforced if sending through GMail. You can set **SSL** or **TLS** explicitly, or choose **Automatic** to have Opus determine the correct protocol automatically.
- **Server requires authentication**: If your SMTP server requires authentication to relay messages, turn this option on and enter the **Username** and **Password** supplied by your ISP or network administrator.
- **Send email via**: There are three different methods Opus can use to send emails:
  - **Internal SMTP client**: This is the preferred method; it means Opus uses its own SMTP client to connect to a mail server and send the email directly. To use this method you must have access to an SMTP server that will accept relay messages. For home users, your ISP will usually provide this - corporate users however may not have access to an SMTP server directly.
  - **mailto: emulation**: This method uses the system registered associations for \<ib:inline-code\>`mailto:`\</ib:inline-code\> links to trigger an email message in your default email client. If you don't have an email client that handles \<ib:inline-code\>`mailto:`\</ib:inline-code\> links installed then this method won't work. Outlook is an example of a client that does provide support for \<ib:inline-code\>`mailto:`\</ib:inline-code\> links.
  - **MAPI client**: This method uses the MAPI system to invoke your default email handler. MAPI is rather out-dated these days and not all email programs support this option.
- **Maximum SMTP threads**: This defines the maximum number of simultaneous outgoing messages - if more messages than this are sent at once the additional messages will be queued.
