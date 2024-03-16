# Synchronous and Asynchronous functions

External programs launched from toolbar buttons and hotkeys can be either synchronous or asynchronous.

- Synchronous in this context means that:
  - Functions that contain multiple commands will run those commands one at a time. Opus will wait for each command to finish before running the next.
  - When a command makes use of selected files, and more than one file is selected, the files will be processed one at a time.

- Asynchronous is the reverse:
  - A function that contains multiple commands will run the commands simultaneously (or at least, will not wait for one command to finish before running the next).
  - When multiple files are selected, Opus will not wait for the first file to be processed before moving on to the next.

As a simple example of the difference, take a command that runs Notepad and passes it the name of the selected item:

\<ib:inline-code\>`notepad.exe {f}`\</ib:inline-code\>

If only one file were selected when you ran this command, Notepad would open showing the selected file, and that would be that. If, however, three files were selected when you ran the command, the behaviour would vary:

- If run synchronously, Notepad would open showing the first file. When you close that instance of Notepad, another one would immediately open showing the second file. Closing the second Notepad window would open a third instance, showing the third file.
- If run asynchronously, you would get three copies of Notepad opening simultaneously, each one showing a different file.

By default, a function that contains a single command will run asynchronously, and functions that contain two or more commands will run synchronously. You can override this in several ways:

- Using the **@async** [command modifier](command_modifiers.md), you can force a command to run asynchronously.
- Using the **@sync** [command modifier](command_modifiers.md), you can force a command to run synchronously.
- You can set the **function_default_async** flag on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences to *True* to make all functions (single or multiple commands) run asynchronously by default.

Internal commands always run synchronously - Opus will always wait for an internal command in a function to finish before moving on to the next instruction. If you want to run an internal command asynchronously for some reason, you can run it using the [DOpusRT](/Manual/reference/dopusrt_reference/RAEDME.md) command (i.e. **dopusrt /cmd**) - it then behaves as an external program, and will respect the **@sync** and **@async** modifiers.
