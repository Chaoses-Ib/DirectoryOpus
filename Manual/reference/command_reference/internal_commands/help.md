# Help

The **Help** internal command can be used to:

- Display the program help file
- Display information about the program (the About dialog)
- Check for [program updates](/Manual/additional_functionality/update_checker.md)
- Access the licence manager to install your program certificate
- Send a quick email

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Displays the program help file.

*Example:* `Help`
</td></tr><tr><td>
ABOUT</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the About dialog, showing information about the current version of the program, copyright and contact details for technical support.

*Example:* `Help ABOUT`
</td></tr><tr><td>
CHECKUPDATE</td><td>
/O</td><td>

*(no value)*</td><td>

Checks online for [program updates](/Manual/additional_functionality/update_checker.md).

*Example:* `Help CHECKUPDATE`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Perform a silent check for updates - a dialog will only be displayed if an update is found.

*Example:* `Help CHECKUPDATE=quiet`
</td></tr><tr><td>
CRASHLOGS</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the [Crash Logs](/Manual/additional_functionality/crash_logs.md) dialog, which shows any crash logs that have been automatically generated and lets you submit them to GPSoftware for analysis.
</td></tr><tr><td>
LANG</td><td>
/K</td><td>

*\<language name\>*</td><td>

Displays a help file in the specified language, if one exists.

*Example:* `Help LANG=deutsch`
</td></tr><tr><td>
LICENCEMANAGER</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the licence manager, where you can view and manage your current program licence, or apply for a free evaluation licence.

*Example:* `Help LICENCEMANAGER`
</td></tr><tr><td>
NEWEMAIL</td><td>
/S</td><td>

*(no value)*</td><td>

Sends a quick email message. You must have configured Opus to send email via SMTP (on the **[Miscellaneous / Email](/Manual/preferences/preferences_categories/internet/email.md)** page in Preferences) for this function to work.

*Example:* `Help NEWEMAIL`
</td></tr><tr><td>
REF</td><td>
/K</td><td>

**commands  
dopusrt  
metadata  
statusbar  
wildcards  
scripting  
cmd\_*name***</td><td>

Provides a shortcut to displays certain reference sections of the help file. For example, you could define a hotkey to take you directly to the *[Wildcards](../../wildcard_reference/README.md)* reference section.

*Example:* `Help REF=wildcards`  
*Example:* `Help REF=cmd_CreateFolder`
</td></tr><tr><td>
RELEASENOTES</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the release notes for the current version.

*Example:* `Help RELEASENOTES`
</td></tr><tr><td>
THEMETESTER</td><td>
/S</td><td>

*(no value)*</td><td>

Opens a UI which can be useful for testing how various standard Windows controls look with colors from custom themes.

*Example:* `Help THEMETESTER`
</td></tr></tbody>
</table>

