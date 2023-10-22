# DDE Functions

DDE ([Dynamic Data Exchange](http://en.wikipedia.org/wiki/Dynamic_Data_Exchange)) is an antiquated system for passing data between different programs on a Windows system. These days, it's not used much - although perhaps surprisingly, [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) mode is actually implemented via DDE (for historical reasons more than anything).

Nonetheless, you may have an old program that supports a DDE interface, and should the need arise, it's possible to configure a button or hotkey to send what's called a DDE message to another application.

![](/Manual/images/media/ddecommand.png) 

Above is an example command that establishes a DDE conversation and sends a command to another program. As this technique requires multiple command lines, you must create the command in the [Advanced Command Editor](command_editor/advanced_command_editor.md). The four lines in the above function are:

- **ddeexec**: The **ddeexec** instruction specifies the "message" that is to be sent to the other program. This will be defined by that program - the above screenshot is only an example. The **%1** [external control code](/Manual/reference/command_reference/external_control_codes/codes_for_passing_filenames.md) is used to include the name of the selected file in the message.
- **ddeapp**: The **ddeapp** instruction specifies the "application name" - this is the name that the other program looks for when DDE messages are sent.
- **ddetopic**: The **ddetopic** instruction specifies the "message topic" - again, this is application specific.
- The final line provides the actual command line used to launch the other program. This will normally involve passing some sort of command line flag telling the other program you want it to run in DDE mode - as in the above screenshot, with the **/dde** parameter. Again though, this is entirely dependent on the application in question.
