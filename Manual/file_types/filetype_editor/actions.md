# Actions

The **Actions** tab in the [file type editor](../filetype_editor/README.md) lets you configure the behavior of various "actions" - standard commands (verbs) that the system defines and uses for files of various types. The settings on this tab are global - they affect the behavior of the file type throughout the system. [File type groups](../file_type_groups.md) and most of the special [Directory Opus File Types](../directory_opus_file_types.md) don't have an actions tab.

![](/Manual/images/media/filetypes_-_actions.png)

  
This screenshot shows the **Actions** tab for a **.doc** file (Word document). The available actions are:

- **explore**: This action only makes sense for folders, it defines the function for the "explore" verb. Normally this is used when you right-click on a folder and choose **Explore** from the context menu.
- **find**: This action is also only generally used for folders, it defines the function for the "find" verb.
- **open**: This is *usually* the default action for a file type - when you double-click on a file, the "open" verb is the one most often invoked. It's also generally what will happen if you right-click on a file or folder and choose **Open** from the context menu.
- **print**: The "print" verb is usually invoked when you right-click on a file and choose **Print** from the context menu. It lets default print handlers be defined for different file types.
- **printto**: This is a variant of the "print" verb that's used when printing to a specific printer.

Of the above actions, **explore**, **open** and **print** are the ones most often used. When an action is displayed in the context menu it can have a label that doesn't necessarily have to correspond with the name of the verb. If such a label is defined then it is displayed in the actions list rather than the name of the verb. This has actually happened in the above screenshot although it's not immediately obvious - the label for the "open" action has been set to Open (with a capital letter).

At the bottom of the actions tab, the **Edit** button lets you edit the selected action (or you can just double-click it), the **Delete** button lets you delete it (clear out the definition), and the **Set Default** button lets you set the default action for a file type (what happens when you double-click it). Normally you wouldn't want to change this from **open** - in the above screenshot, the **open** action is shown in bold to indicate it is the default action.

You can also right-click on the items in the actions list to display a context menu for the item. This context menu lets you use **Copy** and **Paste** to copy the definition from one action to another.

Editing an action displays the **Edit** action dialog. Because actions are global settings (used by Windows as well as Opus), this is not a full-blown [function editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md) dialog, and you can't configure actions to use internal Opus commands. Instead, two types of function can be defined for an action.

![](/Manual/images/media/open_action_-_run.png) 

  
The first type (selected from the **Type** drop-down) is *Run an application.* This lets you define an action that simply runs an executable program. The name of the file can be passed to the program using the **%1**[control code](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md). For example, the command line for the open action for .jpg files is:

    C:\Windows\System32\rundll32.exe "C:\Program Files\Windows Photo Viewer\PhotoViewer.dll", ImageView_Fullscreen %1

  
The **Action** field lets you configure the label that's displayed in the context menu for this action.

![](/Manual/images/media/open_action_-_dde.png) 

  
The second type of action is *DDE command*. This uses the (rather antiquated) [DDE system](http://en.wikipedia.org/wiki/Dynamic_Data_Exchange) to send a command to an application that may or may not be already running. The above image shows the **print** action for Word documents. You can see that the label for the action has been set to **&Print** - in context menus, this would result in the command being displayed as **Print** with an underscore under the **P** (to represent the key that can be pressed for the function).

It's beyond the scope of this document to explain how DDE works unfortunately, but luckily it's extremely unlikely you'll ever actually need to use this system. The parameters that can be specified for a DDE function are:

- **Application**: The command line that's used to start the application if it's not already running.
- **DDE Message**: The message that's sent to the application to make it take the desired action on the file.
- **AppName**: The DDE name of the application.
- **Topic**: The DDE topic that's used to initiate the DDE conversation.
- **Not Running**: An alternate message that's used if the application wasn't already running and needed to be launched.
