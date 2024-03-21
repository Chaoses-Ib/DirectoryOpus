# Help

The **Help** internal command can be used to:

- Display the program help file
- Display information about the program (the About dialog)
- Check for [program updates](/Manual/additional_functionality/update_checker.md)
- Access the licence manager to install your program certificate
- Send a quick email

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Displays the program help file.<br /><br />*Example:* `Help` |
| ABOUT | /S | *(no value)* | Displays the About dialog, showing information about the current version of the program, copyright and contact details for technical support.<br /><br />*Example:* `Help ABOUT` |
| CHECKUPDATE | /O | *(no value)* | Checks online for [program updates](/Manual/additional_functionality/update_checker.md).<br /><br />*Example:* `Help CHECKUPDATE` |
|  |  | **quiet** | Perform a silent check for updates - a dialog will only be displayed if an update is found.<br /><br />*Example:* `Help CHECKUPDATE=quiet` |
| CRASHLOGS | /S | *(no value)* | Displays the [Crash Logs](/Manual/additional_functionality/crash_logs.md) dialog, which shows any crash logs that have been automatically generated and lets you submit them to GPSoftware for analysis. |
| LANG | /K | *\<language name\>* | Displays a help file in the specified language, if one exists.<br /><br />*Example:* `Help LANG=deutsch` |
| LICENCEMANAGER | /S | *(no value)* | Displays the licence manager, where you can view and manage your current program licence, or apply for a free evaluation licence.<br /><br />*Example:* `Help LICENCEMANAGER` |
| NEWEMAIL | /S | *(no value)* | Sends a quick email message. You must have configured Opus to send email via SMTP (on the **[Miscellaneous / Email](/Manual/preferences/preferences_categories/internet/email.md)** page in Preferences) for this function to work.<br /><br />*Example:* `Help NEWEMAIL` |
| REF | /K | **commands  <br />dopusrt  <br />metadata  <br />statusbar  <br />wildcards  <br />scripting  <br />cmd\_*name*** | Provides a shortcut to displays certain reference sections of the help file. For example, you could define a hotkey to take you directly to the *[Wildcards](../../wildcard_reference/README.md)* reference section.<br /><br />*Example:* `Help REF=wildcards`  <br />*Example:* `Help REF=cmd_CreateFolder` |
| RELEASENOTES | /S | *(no value)* | Displays the release notes for the current version.<br /><br />*Example:* `Help RELEASENOTES` |
| THEMETESTER | /S | *(no value)* | Opens a UI which can be useful for testing how various standard Windows controls look with colors from custom themes.<br /><br />*Example:* `Help THEMETESTER` |

