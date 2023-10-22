# Display Page

The **Display** page is where you specify which messages from an FTP server are displayed and whether logging is enabled for a site entry in the [FTP Address Book]().

The two sections this page is divided into (**Display** and **Log**) can all be individually enabled or disabled for any given site. When a section is set to **Use defaults**, the settings for that section come from the equivalent page in the [Default Settings](default_settings.md).

The **Display** section lets you control which site messages are displayed and how Opus interprets certain aspects of the directory listing.

- **Display progress windows**: This option causes Opus to display intermediate messages from the site during certain activities (login, change directory and folder listing).
- **Hide files beginning with '.'**: Unix-based systems often have special files that begin with a dot character. If this option is enabled these files will be hidden from the list.
- **Show directory messages**: This option causes the "directory information" messages to be displayed in the log (if logging is enabled). These are messages that the server administrator can configure for individual folders on the server. If enabled Opus will display these in the log when you change directory.
- **Show startup messages**: This option causes the site's "welcome" message to be display in the log (if logging is enabled). This is a message that the server administrator can configure the site to display upon connection. If enabled Opus will display this in the log when you connect to the site.
- **Treat unknown links as**: Unix systems often use links to make files and folders appear to be located in multiple places. Depending on the software the FTP server is running it can sometimes be impossible for Opus to distinguish between links to files and links to folders. In these cases, the link will be interpreted according to this option. You can choose **automatic** (Opus makes its best guess), or specify **file** or **folder**.
- **Logical parent directory**: Directories on FTP servers are often accessed via links, so the path that Opus sees as the current directory may not be the absolute path to the folder. This can cause problems when going up the folder tree as the "true" parent of a folder may not be the "logical" parent (i.e. simply stripping off the last component in the path may not give you the path of the true parent folder). When this option is turned off, Opus will send an FTP **UP** command when going up in the folder tree - when turned on, Opus strips off the last component and sends an FTP **CD** command to change to the logical directory.

The **Log** section lets you control logging for the FTP site.

- **Enable log**: Enables logging for connections to this site. The basic log option shows commands sent to the FTP site and responses received.
- **Enable debug**: Enables debug logging - diagnostic information will be logged as well as the normal commands/responses. Use this when trying to diagnose problems with the connection.
- **Display log automatically upon connection**: This option causes the log for the site to be automatically displayed in the Lister when you connect to the site.

The log for an FTP site can be displayed using the **Display FTP Logs** command in the drop-down **FTP** menu, or from the **Logs** sub-menu in the **Help** menu on the toolbar. You can also use the **Display log automatically** option above to have the log automatically displayed whenever you connect to the site.
