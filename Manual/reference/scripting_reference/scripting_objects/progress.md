# Progress

The **Progress** object lets you display and control a standard Directory Opus progress indicator dialog. This object can be obtained from the **[Command](command.md).progress** property. The basic steps for using a **Progress** object are:

1.  Initialize the fundamental properties.
2.  Call the **Init** method to create the dialog (this creates it but does not show it to the user).
3.  When ready, call the **Show** method to make the dialog visible. 
4.  Call the appropriate methods to initialize the state of the progress bars (by setting the total number of files, total byte size, etc).
5.  As your operation progresses, advance the progress bars using methods like **StepFiles** and **StepBytes**.
6.  If appropriate, poll the state of the *Abort* and other control buttons using **GetAbortState**.
7.  Call the **Hide** method and destroy the object when your operation is finished.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
abort</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the *Abort* button should be available, or **False** to disable it.
</td></tr><tr><td>
bytes</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the dialog should show progress in bytes rather than whole files.
</td></tr><tr><td>
delay</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the dialog should delay before appearing after the **Show** method is called. The delay is configured by the user in Preferences.
</td></tr><tr><td>
full</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** to enable a "full size" progress indicator with two separate progress bars (one for files and one for bytes).
</td></tr><tr><td>
owned</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the dialog should be owned by its parent window (the parent is given later, when the dialog is created via the **Init** method).
</td></tr><tr><td>
pause</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the *Pause* button should be available.
</td></tr><tr><td>
skip</td><td>

*bool*</td><td>

Before calling **Init**, set to **True** if the *Skip* button should be available. (This just makes it so the *Skip* button can be enabled. You must still call **EnableSkip** later to actually enable it; usually once per file.)
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddFiles</td><td>

\<int:count\>  
\<**[FileSize](filesize.md)**:bytes\></td><td>

*none*</td><td>

Adds the specified number of files to the operation total. The *bytes* argument is optional - in a "full size" progress indicator this lets you add to the total byte size of the operation.
</td></tr><tr><td>
ClearAbortState</td><td>

*none*</td><td>

*none*</td><td>

Clears the state of the three "control" buttons (*Abort* / *Pause* / *Skip*) so they no longer register as being clicked when **GetAbortState** is called.  
If you only want to clear the *Skip* state, you should normally do that as part of a call to **EnableSkip** instead. That way you avoid accidentally clearing one of the other states if they become set between you calling **GetAbortState** and **ClearAbortState**. In fact, there are very few situations where you should call **ClearAbortState**.
</td></tr><tr><td>
EnableSkip</td><td>

*\<*bool:enable\>  
*\<*bool:delay\>  
*\<*bool:clear\></td><td>

*none*</td><td>

Enables the progress dialog's *Skip* button. For **EnableSkip** to work, you must have set the **skip** property to **True** before the progress dialog was created by the **Init** method.  
**enable**: If **True**, the *Skip* button should be enabled; otherwise, it should be disabled.  
**delay** (optional, **True** by default): If **True**, there will be a short delay before the *Skip* button is enabled, with it temporarily disabled during the delay; otherwise, the change is instant. See below for why a delay is usually a good idea.  
**clear** (optional, **True** by default): If **True**, any record of the user pushing the *Skip* will be cleared, such that **GetAbortState** no longer returns **"s"**. You usually want this if the progress dialog just moved to a new item.  
If you support the *Skip* button, you should normally call **EnableSkip** once per file, just after you call **SetName** and similar methods. When used that way, you'll usually want **delay** and **clear** to both be **True**, otherwise clicks of the *Skip* button intended for one file could affect the file(s) that come after it. For example, if a file takes a long time but then finishes just as the user gets tired of waiting and clicks *Skip*, the delay and cleared state ensure the unwanted click is harmless.
</td></tr><tr><td>
FinishFile</td><td>

*none*</td><td>

*none*</td><td>
Finish the current file. If the byte size of the current file has been set the total progress will be advanced by any remaining bytes.
</td></tr><tr><td>
GetAbortState</td><td>

\<bool:autoPause\>  
\<string:wanted\>  
\<bool:simple\></td><td>

*string*</td><td>

Polls the state of the three "control" buttons. This returns a *string* that indicates which, if any, of the three buttons have been clicked by the user. The button states are represented by the following letters in the returned string:

**a** - Abort  
**p** - Pause  
**s** - Skip

If none of the states apply, an empty string is returned.  
**autoPause** (optional, **False** by default): If **True**, pausing is handled for you automatically. Calls to **GetAbortState(True)** block while paused and don't return until unpaused; the "**p**" state is never returned. (Note that clicking *Skip* or *Abort* will implicitly unpause the operation.)  
**wanted** (optional): If you only want to check one or two of the states, pass a string with their letters. For example, **GetAbortState(True,"ap")** will test for the *Abort* and *Pause* states, but not the *Skip* one. All states will be checked if the argument is an empty string or not given at all.  
**simple** (optional, **True** by default): If **True**, the result string will have at most one letter, indicating the most important state. If **False**, it is possible for multiple states to be indicated at once. For example if *Skip* and then *Pause* are clicked, in that order, without the script clearing the *Skip* state, then **GetAbortState(False,"",False)** would return "**ps**" while **GetAbortState(False)** would return just "**p**".  
To clear the state of the three buttons, call the **ClearAbortState** method. To clear just the *Skip* button's state, use the **EnableSkip** method.
</td></tr><tr><td>
Hide</td><td>

*none*</td><td>

*none*</td><td>

Hides the progress indicator dialog. The dialog object itself remains valid, and can be redisplayed with the **Show** method if desired.
</td></tr><tr><td>
HideFileByteCounts</td><td>

*\<*bool:show\></td><td>

*none*</td><td>

Hides or shows the *"XX bytes / YY bytes"* string in the progress dialog. You can use this to hide the string if the progress does not indicate a number of bytes (e.g. when it indicates a percentage). Pass **True** for the *show* argument to show the string and **False** to hide it.
</td></tr><tr><td>
Init</td><td>

\<**[Tab](tab.md)**:parent\>  
or \<**[Lister](lister.md)**:parent\>

\<string:title\></td><td>

*none*</td><td>

Initializes the dialog. This method causes the actual dialog to be created, although it will not be displayed until the **Show** method is called. The fundamental properties shown above must be set before this method is called - once the dialog has been created they can not be altered.  
The *parent* parameter can be either a **[Tab](tab.md)**or a **[Lister](lister.md)**- this controls which window the dialog is centered over, and if the **owned** property is set to **True** which window it is owned by (always appears on top of). If no parent is provided the dialog will not be associated with any particular window.  
The *title* parameter specifies the window title of the dialog.
</td></tr><tr><td>
InitFileSize</td><td>

*none*</td><td>

*none*</td><td>
Resets the byte count for the current file to zero.
</td></tr><tr><td>
Restart</td><td>

*none*</td><td>

*none*</td><td>
Resets the total completed file and byte counts to zero.
</td></tr><tr><td>
SetBytesProgress</td><td>

\<**[FileSize](filesize.md)**:bytes\></td><td>

*none*</td><td>
Sets the total completed byte count.
</td></tr><tr><td>
SetFileSize</td><td>

\<**[FileSize](filesize.md)**:bytes\></td><td>

*none*</td><td>
Sets the size of the current file.
</td></tr><tr><td>
SetFiles</td><td>

\<int:count\></td><td>

*none*</td><td>
Sets the total number of files.
</td></tr><tr><td>
SetFilesProgress</td><td>

\<int:count\></td><td>

*none*</td><td>
Sets the total completed file count.
</td></tr><tr><td>
SetFromTo</td><td>

\<string:header\>  
\<string:from\>  
\<string:to\></td><td>

*none*</td><td>

Sets the text at the top of the dialog that indicates the source and destination of an operation. The *header* argument refers to the string that normally says *From:* - this allows you to change it in case that term is not applicable to your action. The *from* argument is the source path, and the *to* argument (if there is one) is the destination path. Note that if you specify a destination path this always has a *To:* header appended to it.  
If you omit the *to* argument entirely (not just passing an empty string), the destination line will become blank, including the *To:* header. Use that if you want the second line to be used sometimes but not always. If you never want anything on the second line, use the **SetStatus** method instead as it will not add space for the extra line.
</td></tr><tr><td>
SetName</td><td>

\<string:name\></td><td>

*none*</td><td>
Sets the name of the current file.
</td></tr><tr><td>
SetPercentProgress</td><td>

\<int:percent\></td><td>

*none*</td><td>
Sets the current progress as a percentage (from 0 to 100).
</td></tr><tr><td>
SetStatus</td><td>

\<string:status\></td><td>

*none*</td><td>

Sets the text displayed in the status line at the top of the dialog.  
This sets a single-line status message, while **SetFromTo** can be used to indicate source and destination paths on two lines.
</td></tr><tr><td>
SetTitle</td><td>

\<string:title\></td><td>

*none*</td><td>
Sets the title of the dialog.
</td></tr><tr><td>
SetType</td><td>

\<string:type\></td><td>

*none*</td><td>

Sets the type of the current item - either *file* or *dir*.
</td></tr><tr><td>
Show</td><td>

*none*</td><td>

*none*</td><td>

Displays the progress indicator dialog. Call this once you have created the dialog using the **Init** method.
</td></tr><tr><td>
SkipFile</td><td>

\<bool:complete\></td><td>

*none*</td><td>

Skips over the current file. Set the *complete* argument to **True** to have the file counted as "complete", or **False** to count it as "skipped".
</td></tr><tr><td>
StepBytes</td><td>

\<**[FileSize](filesize.md)**:bytes\></td><td>

*none*</td><td>
Step the byte progress indicator the specified number of bytes.
</td></tr><tr><td>
StepFiles</td><td>

\<int:count\></td><td>

*none*</td><td>
Step the file progress indicator the specified number of files.
</td></tr></tbody>
</table>

