# Find-as-you-type Field

The Find-as-you-type field (*FAYT*) is a multi-purpose text field that pops up at the bottom of the file display when you type a key (letter or number) that hasn't been otherwise assigned to a hotkey.

The FAYT started out as a visible implementation of the Explorer feature that lets you jump to a specific file by simply typing the first letter or letters of its name. In its default mode that's exactly what it does, and the behaviour is exactly the same except that you can see what you've typed.

As well as typing to jump to a file, the FAYT has other modes, most of which can be triggered by first pressing a specific key.

These are the different FAYT modes:

- **Find**: Type a part of a filename to jump to the first matching file in the current directory.
- **Command**: Enter a command and run it immediately without having to set up a button. (Default key: greater-than **\>**)
- **DOS Command**: Similar to command mode, but the command will run in a DOS window letting you view any text output. (Default key: question-mark **?**)
- **WSL Command**: Assuming the Windows Subsystem for Linux has been installed from the Windows Store, this mode lets you run a Linux command in a shell window. (Default key: vertical bar **\|**).
- **Error**: More a color than a real mode; if what you type is not recognised, the FAYT changes to a red background (by default) to indicate the problem.
- **Go**: Type a folder path (e.g. C:\Windows) or folder alias (e.g. /home) into the FAYT to navigate to that location without having to activate the path field.
- **Filter**: Filter out files that don't match the specified pattern. (Disabled by default in favor of the separate *[Filter Bar](../searching_and_filtering/filter_bar.md)*.)
- **Range**: This lets you select a range of files by index. (Default key: hash/pound **\#**)
- **Search**: Trigger a Windows Search indexed search. (Default key: equals **=**)
- **Select**: Select files by entering a wildcard pattern. (Default key: colon **:**)
- **Tabs**: Search and switch to open folder tabs by path or title. (Default key: at symbol **@**)

To initiate the FAYT field simply start typing into the file display (you may need to give it input focus first). If the first key you press is one of the assigned mode keys (these can be configured from the **[File Displays / Find-As-You-Type](/Manual/preferences/preferences_categories/file_displays/fayt_and_filter_bar_keys.md)** Preferences page), the FAYT will be set to the appropriate mode, which is indicated by its background color. If the first key you press is not one of the assigned keys, the FAYT defaults to **Find** mode - which provides the same functionality as typing into an Explorer window to jump to a specific file.

![](/Manual/images/media/fayt1.png) 

One small difference between the FAYT's **Find** mode and the traditional "type to jump to a file" feature in Explorer arises when you want to skip through multiple files beginning with the same letter. For example, in Explorer if you wanted to skip through all files beginning with N, you would simply press N N N N... to jump from one file to the next. In Opus, doing that will actually search for a file beginning with "nnnnn". Instead, to skip to the next match in Opus you press **F3** (and you can press **Shift-F3** to skip back to the previous match). If you'd like to change this behaviour to be the same as Explorer's, set the **fayt_firstchar_repeat** option to **True** on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page of Preferences. You can also press **Ctrl-T** in the FAYT itself to toggle this setting.

By default the FAYT will match the entered text anywhere in the filename, but you can change this in Preferences to only match at the start of the name. There's also an option in Preferences to ignore diacritics (accents), which means pressing e would also match files containing **é**, for example.

The FAYT will switch into **Go** mode if what you type into Find mode is recognised as the start of a folder path or alias. The FAYT will then act like a path field, offering automatic path-completion and navigating to the location you specify when you push return. The advantage of this over the standard path field on the toolbar is that you can start typing a path immediately, without first having to activate the path field. You can even remove the path field from your toolbar if you want to.

The **Command** mode lets you enter a command and execute it immediately. You can run any Opus internal command, or launch an external program. Any function you can run from a button or hotkey can be run as an ad-hoc command through the FAYT.

![](/Manual/images/media/fayt2.png) 

As you can see from this screenshot, you can use any of the [external control codes](/Manual/reference/command_reference/external_control_codes/RAEDME.md) in your command - the above example would open any selected files in Paint. As a shortcut when typing the command, you can also press **Ctrl-Enter** to automatically insert the names of any selected files in the command line. The command mode has a history of your most recently executed commands - press the **Up** or **Down** cursor keys to access it.

The **DOS Command** mode is very similar to the **Command** mode, except that it lets you run DOS commands and will display a DOS window showing you the output of any such commands.

![](/Manual/images/media/fayt3.png)

If the Windows Subsystem for Linux has been installed from the Windows Store, the **WSL Command** mode lets you run Linux commands in a Linux shell in the same way DOS commands can be run in a DOS window.

The **Range** mode is only used when the file display is in details or power mode. It lets you select files by index or a range of indexes. The **Index** column is added automatically if it's not already displayed when you use this mode (and removed again when the FAYT field closes).

![](/Manual/images/media/fayt4.png) 

  
In this example, the specified range selects file numbers 12 and 14, as well as the range from 16 through 18. You can also select a range based on the current focus position. For example, **\#+10** will select the next 10 files from the current position, and **\#-5** will select the previous 5. You can also use, for example, **\#-5+5** to select 5 files either side.

The **Search** mode lets you initiate an indexed [Windows Search](../searching_and_filtering/windows_search.md) in the current folder. It is equivalent to entering a search string into the toolbar search field - but if you would rather remove the search field to save space on your toolbars, you can still access the search function through the FAYT.

![](/Manual/images/media/fayt5.png) 

The **Select** mode lets you select all items in the current folder that match the text you enter.

![](/Manual/images/media/fayt6.png) 

  
The match is automatically performed in *partial match* mode - meaning that you can either enter a sub-string to match on, or a full wildcard pattern. For example, to quickly select all JPEG files, you could either type **:\*.jpg** or simply **.jpg** (although the latter would also match any files that had **.jpg** as part of their name as well as their extension). To invert the selection (i.e. to select all files that don't match the string) type a tilde character (~) at the start.

The **Tabs** mode lets you search all open folder tabs, by folder path and tab title. The match is automatically performed in *partial match* mode - meaning that you can either enter a sub-string to match on, or a full wildcard pattern.

![](/Manual/images/media/fayt_tabs.png)

  
Matching tabs are displayed in a popup list and you can switch to one of the matching tabs by selecting it from the list (either using the mouse or keyboard).

The **Filter** mode lets you filter the display to exclude all items that don't match the text or wildcard pattern you enter.

![](/Manual/images/media/fayt7.png) 

  
By default, **Filter** mode is not enabled in the FAYT - instead, the *[Filter Bar](../searching_and_filtering/filter_bar.md)* is used to perform a similar function (the dedicated Filter Bar has additional functionality that makes it more powerful than the FAYT for this task). You can enable Filter mode in the FAYT by configuring a key for it on the **[File Displays / Find-As-You-Type](/Manual/preferences/preferences_categories/file_displays/fayt_and_filter_bar_keys.md)** Preferences page. To invert the filter (i.e. to hide all files that don't match the string) type a tilde character (~) at the start.

  
If you have filtered the display with the FAYT (or with the Filter Bar) you can quickly clear the filter and redisplay the original contents by pressing the **Escape** key.
