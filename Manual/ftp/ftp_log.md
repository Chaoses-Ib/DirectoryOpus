# FTP Log

Opus can maintain a separate log for each FTP site you connect to. To enable logging for an FTP site, turn on the **Enable log** option (and optionally the **Enable debug** option) on the **[Display](ftp_address_book/display_page.md)** page for the site entry in the [FTP Address Book](ftp_address_book/README.md). Or to enable logging for all FTP connections, turn on the same option for the **[Default Settings](ftp_address_book/default_settings.md)** entry.

The FTP Log is displayed in the Lister's [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md), which appears at the bottom of a Lister. To display the log, select the **Display FTP Logs** command in the drop-down **FTP** menu, or from the **Logs** sub-menu in the **Help** menu on the toolbar. You can also use the **Display log automatically** option for a site entry to have the log automatically displayed whenever you connect to the site.

![](/Manual/images/media/ftp_log.png)

The buttons at the top of the log display let you **Save** (![](/Manual/images/media/ftp_log_-_save.png)) the log to a text file, **Copy** (![](/Manual/images/media/ftp_log_-_copy.png)) any selected text to the clipboard, and **Clear** (![](/Manual/images/media/ftp_log_-_clear.png)) the log. The drop-down attached to the **Clear** button gives you the option to clear all logs, otherwise only the currently displayed log is cleared.

The **Log** drop-down lets you select which site's log you are viewing. A separate log is maintained for each FTP site you connect to. The drop-down also contains an **All Activity** option which is a unified log showing all FTP output. If you connect to multiple sites at the same time you can keep an eye on all the FTP activity at once using the unified log.

The **Float** (![](/Manual/images/media/ftp_log_-_float.png)) button on the right of the log panel lets you float the FTP log display free of the Lister. When you do this the Utility Panel will shrink to take up minimal space. This can be handy if you want to put the FTP log on another monitor to keep an eye on your FTP activity. When you close the floating log it returns automatically to the Lister it came from.

There are a couple of options in [Preferences](/Manual/preferences/README.md) that affect the FTP log:

- The FTP log font can be configured on the [Fonts](/Manual/preferences/preferences_categories/colors_and_fonts/fonts.md) page in Preferences.
- The maximum size of each individual log can be configured on the [File Operations / Logging](/Manual/preferences/preferences_categories/file_operations/logging.md) page.
