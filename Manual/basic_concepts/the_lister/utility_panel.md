# Utility Panel

The Utility Panel is a multi-purpose panel that appears at the bottom of the Lister whenever certain functions are activated. It acts as a container for several different functions. You rarely turn on the Utility panel directly (although using the raw **[Set](/Manual/reference/command_reference/internal_commands/set.md)** command you can); instead, it is displayed in a particular mode whenever one of the following commands is chosen:

- **Find Files** from the **Tools** menu: Displays the utility panel in [Find](../searching_and_filtering/find_files/RAEDME.md) mode, which lets you search your computer for files and folders.
- **Synchronize** from the **Tools** menu: Displays the panel in [Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) mode, a function that lets you synchronize the contents of two different folders.
- **Find Duplicate Files** from the **Tools** menu: [Duplicate Files](/Manual/additional_functionality/duplicate_file_finder.md) mode lets you search your computer for any duplicated files (or for duplicates of a specific file).
- **FTP Log** from the **Help** menu (**Logs** sub-menu) or **Display FTP Logs** from the **FTP** menu: Displays [FTP](/Manual/ftp/RAEDME.md) site activity.
- **File Log** from the **Help** menu: Displays a [log of file actions](/Manual/file_operations/tracking_and_undoing_file_operations.md) (files copied, deleted, renamed, etc). The log can be quite handy at times - anyone who's ever dropped files into the wrong folder by mistake and then spent 20 minutes looking for them will know what we're talking about! You can enable the file log (and configure it) from the **[File Operations / Logging page](/Manual/preferences/preferences_categories/file_operations/logging.md)** in Preferences.
- **Undo Log** from the **Help** menu: Displays the most recent file actions that can be [undone](/Manual/file_operations/tracking_and_undoing_file_operations.md) (e.g. if a file has been deleted to the recycle bin, you can recover the file).
- **Email Log** from the **Help** menu: Displays a log of any [outgoing email](/Manual/preferences/preferences_categories/internet/email.md) that Opus has sent.
- **Other Log** from the **Help** menu: Displays miscellaneous logs - currently only [scripts](/Manual/scripting/RAEDME.md) make use of this.

When the utility panel is displayed, you can switch between its various modes using the dropdown in the title bar.

![](/Manual/images/media/utility_pane_dropdown.png) 
