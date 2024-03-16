# Find-as-you-type Field

The Find-as-you-type field (*FAYT*) is a multi-purpose text field that pops up at the bottom of the file display when you type a key (letter or number) that hasn't been otherwise assigned to a hotkey.

The FAYT started out as a visible implementation of the Explorer feature that lets you jump to a specific file by simply typing the first letter or letters of its name. In its default mode that's exactly what it does, and the behaviour is exactly the same except that you can see what you've typed.

As well as typing to jump to a file, the FAYT has many other modes, most of which can be triggered by first pressing a specific key.

##### Bringing up the FAYT

To initiate the FAYT field simply start typing into the file display (you may need to give it input focus first). If the first key you press is one of the assigned mode keys, the FAYT will be set to the appropriate mode, which is indicated by its background color.

If the first key you press isn't one of the assigned keys, the FAYT defaults to **Find** mode - which provides the same functionality as typing into an Explorer window to jump to a specific file.

The assigned keys, and the default mode, can be configured from the **[Quick Keys](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md)** Preferences page.

##### Find

The default FAYT mode; type a part of a filename to jump to the first matching file in the current directory. Any names that match what you type are highlighted in the file display and also indicated in the scrollbar, and the selection is moved to the first (and then subsequent) matching name.

One small difference between the FAYT's **Find** mode and the traditional "type to jump to a file" feature in Explorer arises when you want to skip through multiple files beginning with the same letter.

For example, in Explorer if you wanted to skip through all files beginning with \<ib:inline-code\>`N`\</ib:inline-code\>, you would simply press \<ib:inline-code\>`N N N N...`\</ib:inline-code\> to jump from one file to the next.

In Opus, doing that will actually search for a file beginning with "nnnnn". Instead, to skip to the next match in Opus you press <kbd>F3</kbd> (and you can press <kbd>Shift+F3</kbd> to skip back to the previous match). There's an option in Preferences to change this behaviour to be the same as Explorer's. You can also press <kbd>Ctrl+T</kbd> in the FAYT itself to toggle this setting.

By default **Find** mode will match the entered text anywhere in the filename, but you can change this in Preferences to only match at the start of the name. There's also an option in Preferences to ignore diacritics (accents), which means pressing \<ib:inline-code\>`e`\</ib:inline-code\> would also match files containing \<ib:inline-code\>`é`\</ib:inline-code\>, for example.

The [Find-As-You-Type / Find Mode](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/find_mode.md) Preferences page has a number of options that control **Find** mode.

##### Go

Type a folder path (e.g. \<ib:inline-code\>`C:\Windows`\</ib:inline-code\>) or folder alias (e.g. \<ib:inline-code\>`/home`\</ib:inline-code\>) into the FAYT to navigate to that location without having to activate the path field.

The FAYT will switch into **Go** mode if what you type into **Find** mode is recognised as the start of a folder path or alias. The FAYT will then act like a path field, offering automatic path-completion and navigating to the location you specify when you push return. The advantage of this over the standard path field on the toolbar is that you can start typing a path immediately, without first having to activate the path field. You can even remove the path field from your toolbar if you want to.

##### Command

Default key: \<ib:inline-code\>`>`\</ib:inline-code\>. Enter a command and run it immediately without having to set up a button.

The **Command** mode lets you enter a command and execute it immediately. You can run any Opus internal command, or launch an external program. Any function you can run from a button or hotkey can be run as an ad-hoc command through the FAYT.

You can also use any of the [external control codes](/Manual/reference/command_reference/external_control_codes/RAEDME.md) in your command. As a shortcut when typing the command, you can also press <kbd>Ctrl+Enter</kbd> to automatically insert the names of any selected files in the command line. The command mode has a history of your most recently executed commands - press the <kbd>Up</kbd> or <kbd>Down</kbd> cursor keys to access it.

##### DOS Command

Default key: \<ib:inline-code\>`?`\</ib:inline-code\>. Similar to command mode, but the command will run in a DOS window letting you view any text output.

The **DOS Command** mode is very similar to the **Command** mode, except that it lets you run DOS commands and will display a DOS window showing you the output of any such commands.

##### Everything (Local)

Default key: \<ib:inline-code\>`-`\</ib:inline-code\>. Performs a local [quick search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) using ([Everything](https://www.voidtools.com)).

Assuming *Everything* by voidtools is installed, this mode performs an indexed search below the current folder.

##### Everything (Global)

Default key: \<ib:inline-code\>`+`\</ib:inline-code\>. Performs a global [quick search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) using ([Everything](https://www.voidtools.com)).

Assuming *Everything* by voidtools is installed, this mode performs a global indexed search of all indexed locations.

##### Filter

The **Filter** mode lets you filter the display to exclude all items that don't match the text or wildcard pattern you enter.

\<WRAP round info\>By default, **Filter** mode is not enabled in the FAYT - instead, the [filter bar](../searching_and_filtering/filter_bar.md) is used to perform a similar function. The dedicated filter bar has additional functionality that makes it more powerful than the FAYT for this task.

You can enable Filter mode in the FAYT by configuring a key for it on the [Quick Keys](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md) Preferences page.\</WRAP\>

To invert the filter (i.e. to hide all files that don't match the string) type a tilde character (~) at the start.

If you have filtered the display with the FAYT (or with the Filter Bar) you can quickly clear the filter and redisplay the original contents by pressing the <kbd>Esc</kbd> key.

##### Opus search

Default key: \<ib:inline-code\>`'`\</ib:inline-code\>. Performs a [quick search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) using the internal Opus find tool.

Uses Opus's built-in Find Files functionality to search below the current folder.

If a plain string or a wildcard is entered, it will be treated as a wildcard name match. If a string beginning with \<ib:inline-code\>`=`\</ib:inline-code\> is entered, it'll be processed by the [evaluator](/Manual/evaluator/RAEDME.md) and can perform more complex queries (e.g. \<ib:inline-code\>`=size>100kb`\</ib:inline-code\>).

##### Range

Default key: \<ib:inline-code\>`#`\</ib:inline-code\>. Lets you select a range of files by index.

The **Range** mode is only used when the file display is in details or power mode. It lets you select files by index or a range of indexes. The **Index** column is added automatically if it's not already displayed when you use this mode (and removed again when the FAYT field closes).

A range is given in the form \<ib:inline-code\>`#a-b`\</ib:inline-code\>, for example \<ib:inline-code\>`#5-10`\</ib:inline-code\> would select files five through ten. You can select individual files too - \<ib:inline-code\>`#5`\</ib:inline-code\> would just select file number five. You can use commas to combine one or more single numbers and ranges. For example, \<ib:inline-code\>`#12,14,16-18`\</ib:inline-code\> would select files 12, 14, 16, 17, 18.

You can also select a range based on the current focus position. For example, **\#+10** will select the next 10 files from the current position, and **\#-5** will select the previous 5. You can also use, for example, **\#-5+5** to select 5 files either side.

##### Folders

Default key: \<ib:inline-code\>`]`\</ib:inline-code\>. Shows a popup list of folders drawn from various sources (e.g. recent, favorites and aliases).

You can choose the sources from the [Find-As-You-Type / Folders Mode](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/folders_mode.md) Preferences page.

##### Windows Search

Default key: \<ib:inline-code\>`=`\</ib:inline-code\>. Performs a Windows Search indexed search below the current folder.

The **Search** mode lets you initiate an indexed [Windows Search](../searching_and_filtering/windows_search.md) in the current folder. It is equivalent to entering a search string into the toolbar search field - but if you would rather remove the search field to save space on your toolbars, you can still access the search function through the FAYT.

##### Select

Default key: \<ib:inline-code\>`:`\</ib:inline-code\>. Select files by entering a wildcard pattern.

The **Select** mode lets you select all items in the current folder that match the text you enter.

The match is automatically performed in *partial match* mode - meaning that you can either enter a sub-string to match on, or a full wildcard pattern. For example, to quickly select all JPEG files, you could either type \<ib:inline-code\>`:*.jpg`\</ib:inline-code\> or simply \<ib:inline-code\>`:.jpg`\</ib:inline-code\> (although the latter would also match any files that had \<ib:inline-code\>`.jpg`\</ib:inline-code\> as part of their name as well as their extension). To invert the selection (i.e. to select all files that don't match the string) type a tilde character (\<ib:inline-code\>`~`\</ib:inline-code\>) at the start.

##### Tabs

Default key: \<ib:inline-code\>`@`\</ib:inline-code\>. Search and switch to open folder tabs by path or title.

The **Tabs** mode lets you search all open folder tabs, by folder path and tab title. The match is automatically performed in *partial match* mode - meaning that you can either enter a sub-string to match on, or a full wildcard pattern.

Matching tabs are displayed in a popup list and you can switch to one of the matching tabs by selecting it from the list (either using the mouse or keyboard).

##### WSL Command

Default key: \<ib:inline-code\>`|`\</ib:inline-code\>. Runs a Linux command in a shell window.

If the Windows Subsystem for Linux has been installed from the Windows Store, the **WSL Command** mode lets you run Linux commands in a Linux shell in the same way DOS commands can be run in a DOS window.
