# Simple Command Editor

![](/Manual/images/media/command_editor_1.png)

See the [Command Editor]() page for a description of the elements which the Simple and Advanced modes have in common. This page only covers things unique to the Simple mode.

In the Command Editor's Simple mode (shown above), the **Function** field is only a single line. In this mode you can specify the function (what the button actually does when you click it) in three different ways:

- Using the drop-down attached to the field, you can select a pre-defined command (as shown on the [Commands Tab](../../the_customize_dialog/commands/RAEDME.md) in the Customize dialog). When you select a pre-defined command from the drop-down, the function field will be populated with the underlying Opus internal command and arguments. For example, selecting **Viewer Pane** from the drop-down will fill the field in with **Set VIEWPANE=Toggle** as shown above.
- You can directly enter the name of an [Opus internal command](/Manual/reference/command_reference/internal_commands/RAEDME.md), with its optional arguments.
- You can select an external program to run using the Browse button (![](/Manual/images/media/browse.png)). You can append various [external control codes](/Manual/reference/command_reference/external_control_codes/RAEDME.md) to the external program's command line in order to [pass filenames of selected files](../passing_files_to_external_programs.md) to the program.

![](/Manual/images/media/function_-_notepad.png)

This would launch **Notepad**, passing it the name of the first selected file in the file display.

When you select an external program to run, the **Start in** and **Run** fields will be enabled.

- **Start in**: When a command runs an external program, this field specifies the folder that the program will start in (in other words, the new program's current directory).
- **Run**: When running an external program this lets you specify how the program's window is to appear. You can choose from *Normal Window* (the program itself defines the window size), *Minimized* (the program will open minimized to the taskbar), *Maximized* (it will open full screen) and *Hidden* (it won't show a window at all). Not all programs will respect these settings. You need to be careful when using *Hidden* as it can result in the program running without any visible user interface - you should only use it when you know that's definitely what you want. It's most useful when launching a DOS script that runs and quickly exits, as it lets you hide the quick "flash" of the DOS command prompt.

Click the **Advanced** button to switch to [Advanced mode](advanced_command_editor.md).
