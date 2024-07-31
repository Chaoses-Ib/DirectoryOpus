# Close

The **Close** command can be used to:

- Close Listers (either the current Lister or all)
- Collapse all open Listers to tabs in a single Lister
- Exit Directory Opus altogether
- Shutdown or restart the system immediately
- Schedule a system shutdown for some time in the future
- Automatically shutdown the system when all file operations are complete

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*no argument*</td><td>
-</td><td>
-</td><td>

Closes the active Lister. If the active Lister was the only one and the **Shutdown Directory Opus when the last Lister closes** option on the **[Launching Opus / Startup](/Manual/preferences/preferences_categories/launching_opus/README.md)** Preferences page is turned on, this will also exit the program.

*Example:* `Close`

This command is asynchronous. The Lister may not have closed yet when it completes. It should generally be the last command a button runs, as any later commands may fail to run if the window they are associated with has closed.
</td></tr><tr><td>
ALLLISTERS</td><td>
/O</td><td>

*(no value)*</td><td>

Closes all currently open Listers. The program will also exit if the **Shutdown Directory Opus when the last Lister closes** option is turned on. Add the **CURRENTDESKTOP** argument to only close the ones on the current virtual desktop.

*Example:* `Close ALLLISTERS`

This command is asynchronous. The Listers may not have closed yet when it completes. It should generally be the last command a button runs, as any later commands may fail to run if the window they are associated with has closed.
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

Collapses all open Listers to tabs in a single Lister. All Listers except the active one will be closed, and tabs will be opened in the remaining Lister for every Lister that closed.

*Example:* `Close ALLLISTERS=collapse`
</td></tr><tr><td>
</td><td>
</td><td>

**unique**</td><td>

Combine **unique** with **collapse** to prevent duplicate tabs for paths which are already open in the lister. Has no effect unless **collapse** is also specified. At most one tab for each path will be opened in the left or right of the lister, with all other listers closing at the end as usual. Note that if the lister you are collapsing things into already has multiple tabs for the same folder, they will be left as-is, but no additional tabs will open for it.

*Example:* `Close ALLLISTERS=collapse,unique`
</td></tr><tr><td>
ALLOTHERLISTERS</td><td>
/S</td><td>

*(no value)*</td><td>

Closes all open Listers **except** the active Lister. Add the **CURRENTDESKTOP** argument to only close the ones on the current virtual desktop.

*Example:* `Close ALLOTHERLISTERS`

This command is asynchronous. The Listers may not have closed yet when it completes.
</td></tr><tr><td>
ALLVIEWERS</td><td>
/S</td><td>

*(no value)*</td><td>

Closes any open [standalone viewer](/Manual/additional_functionality/viewing_images/README.md) windows. Add the **CURRENTDESKTOP** argument to only close the ones on the current virtual desktop.

*Example:* `Close ALLVIEWERS CURRENTDESKTOP`

This command is asynchronous. The viewers may not have closed yet when it completes. If run from a button or hotkey inside the viewer, it should be the last line, as subsequent lines may not execute if the window they are associated with closes first.
</td></tr><tr><td>
AT</td><td>
/K</td><td>

*\<HH:MM:SS\>*</td><td>

In conjunction with the **SYSTEM** argument this schedules an automatic shutdown of your system at a given time. The time to shutdown is given as a 24 hour time in HH:MM:SS format. If the time you specify is earlier than the current time of day, it will be taken to refer to the next day. When the time you specify is reached, a ten second countdown timer is displayed before the system it shutdown.

*Example:* `Close SYSTEM=shutdown AT 04:00:00`
</td></tr><tr><td>
AUTOLISTER</td><td>
/O</td><td>

*(no value)*</td><td>

In conjunction with the **[Prefs RESTORE](prefs.md)** command, this argument sets a global flag that specifies that when Opus restarts, it should use "auto-Lister" semantics (which basically means that when Opus restarts, it will open a Lister by default).

*Example:* `Close AUTOLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Disables "auto-Lister" semantics when Opus restarts.

*Example:* `Close AUTOLISTER=no`
</td></tr><tr><td>
CANCEL</td><td>
/S</td><td>

*(no value)*</td><td>

If you have previously scheduled a system shutdown with the **Close SYSTEM** and\*\* AT\*\* or **IN** arguments, this argument will cancel it.

*Example:* `Close CANCEL`
</td></tr><tr><td>
CURRENTDESKTOP</td><td>
/S</td><td>

*(no value)*</td><td>

When combined with **ALLLISTERS**, **ALLOTHERLISTERS**, or **ALLVIEWERS**, the **CURRENTDESKTOP** switch will make the command only close those windows which are on the currently active virtual desktop. (Virtual desktops are a feature of Windows 10 and above, so this argument has no effect on earlier versions.)

*Example:* `Close ALLLISTERS=collapse CURRENTDESKTOP`
</td></tr><tr><td>
IN</td><td>
/K</td><td>

*\<HH:MM:SS\>*</td><td>

Schedules an automatic shutdown in a certain amount of time (contrast with **AT**, which lets you specify an absolute time of day). The time is specified in HH:MM:SS format (or MM:SS or just SS). When the time you specify is reached, a ten second countdown timer is displayed before the system it shutdown.

*Example:* `Close SYSTEM=force,poweroff IN 60:00`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(no value)*</td><td>

Closes the Lister without triggering the **[OnCloseLister](../../scripting_reference/scripting_events/oncloselister.md)** script events that any [script add-ins](/Manual/scripting/script_add-ins/README.md) may have provided. You would probably want to use this if running the **Close** command from within an **OnCloseLister** event (to, e.g. close other Listers automatically in response to the user closing one).

*Example:* `Close NOSCRIPT`
</td></tr><tr><td>
PROGRAM</td><td>
/O</td><td>

*(no value)*</td><td>

Exits Directory Opus immediately.

*Example:* `Close PROGRAM`
</td></tr><tr><td>
</td><td>
</td><td>

**confirm**</td><td>

Exits Directory Opus after displaying a confirmation dialog.

*Example:* `Close PROGRAM=confirm`
</td></tr><tr><td>
</td><td>
</td><td>

**onlast**</td><td>

Close the program only if this is the last remaining Lister, otherwise just close the Lister. This command lets you create a unified close/quit command.

*Example:* `Close PROGRAM=onlast`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(no value)*</td><td>

Suppresses the confirmation dialog normally displayed when shutting the system down with the **Close SYSTEM** command. The system will immediately shutdown - there will be no chance to cancel. You can also use this in conjunction with the scheduled shutdown arguments **AT** and **IN**.

*Example:* `Close SYSTEM=shutdown QUIET`
</td></tr><tr><td>
SYSTEM</td><td>
/O</td><td>

*(no value)*</td><td>

Ends your Windows session and logs you off. A ten second countdown dialog will be displayed giving you a chance to cancel (unless you also use the **QUIET** argument).

*Example:* `Close SYSTEM`
</td></tr><tr><td>
</td><td>
</td><td>

**restart**</td><td>

Restarts (reboots) the system

*Example:* `Close SYSTEM=restart QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**shutdown**</td><td>

This shuts the system down (depending on your hardware, this may also power off the computer; or it may display the *"Your computer is now safe to be shutdown"* screen).

*Example:* `Close SYSTEM=shutdown`
</td></tr><tr><td>
</td><td>
</td><td>

**poweroff**</td><td>

This shuts the system down and powers off the computer.

*Example:* `Close SYSTEM=poweroff`
</td></tr><tr><td>
</td><td>
</td><td>

**sleep**</td><td>

Puts the system to sleep.

*Example:* `Close SYSTEM=sleep`
</td></tr><tr><td>
</td><td>
</td><td>

**suspend**</td><td>

Suspends the system (S4 hibernation).

*Example:* `Close SYSTEM=suspend`
</td></tr><tr><td>
</td><td>
</td><td>

**stay**</td><td>

Stay running. If not specified, Directory Opus will exit at the same time Windows shuts down. Combine with **sleep** or **suspend** to make Windows sleep or hibernate without exiting Opus.

*Example:* `Close SYSTEM=sleep,stay`
</td></tr><tr><td>
</td><td>
</td><td>

**force**</td><td>

Use this in addition to the other options to force the system to shutdown even if some programs are not responding. Normally the system will wait for all running programs to exit before shutting down. If you use this option the system will shutdown immediately and you may potentially lose unsaved data if some programs are currently busy.

*Example:* `Close SYSTEM=shutdown,force AT 03:30:00 QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**forceifhung**</td><td>

This is the same as the **force** option, but only if there actually are any non-responding programs. Otherwise the shutdown proceeds as normal.

*Example:* `Close SYSTEM=restart,forceifhung`
</td></tr><tr><td>
</td><td>
</td><td>

**switch**</td><td>

If fast user-switching is enabled, this command will let you switch users. (This cannot be scheduled via the **AT** argument.)

*Example:* `Close SYSTEM=switch`
</td></tr><tr><td>
</td><td>
</td><td>

**unattended**</td><td>

System restart or shutdown will be done in a way which avoids additional confirmation dialogs when running via Remote Desktop or Terminal Services. The dialogs this avoids come from Windows itself; Opus will still show its own confirmation dialogs unless you also use the **QUIET** argument. If any applications, for any logged-in users, have unsaved work then system dialogs may still be generated unless you also use **force** or **forceifhung** (there is no distinction between the two when combined with **unattended**).

*Example:* `Close SYSTEM=shutdown,force,unattended QUIET`
</td></tr><tr><td>
TOGGLE</td><td>
/S</td><td>

*(no value)*</td><td>

Use this argument in conjunction with the scheduled-shutdown options to toggle the scheduled shutdown on or off. If used in a toolbar or menu it causes the button to appear checked whenever a shutdown is scheduled, and unchecked if not (providing a visual indication of the current state of the shutdown scheduler).

*Example:* `Close SYSTEM=poweroff,force WHENFINISHED QUIET TOGGLE`
</td></tr><tr><td>
WHENFINISHED</td><td>
/S</td><td>

*(no value)*</td><td>

Schedules an automatic shutdown when all outstanding file operations have completed. For example, when you are downloading a large amount of data via FTP, you could use this to have the computer automatically shutdown when the download is complete.

Note that if there are currently no executing functions, the shutdown will be triggered immediately!

*Example:* `Close SYSTEM=shutdown WHENFINISHED`
</td></tr></tbody>
</table>

