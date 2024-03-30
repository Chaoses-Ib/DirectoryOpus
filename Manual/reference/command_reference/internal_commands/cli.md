# CLI

The **CLI** internal command can be used to:

- Open the [CLI / Ad-Hoc Script Editor](/Manual/additional_functionality/cli.md) window
- Open an MS-DOS prompt (with the current directory set to the current folder in the Lister)
- Cause the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field to appear in its various modes.

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

Opens an instance of the [CLI / Ad-Hoc Script Editor](/Manual/additional_functionality/cli.md) window.
</td></tr><tr><td>
DOSPROMPT</td><td>
/O</td><td>

*(no value)*</td><td>

Opens a DOS prompt with the current directory set to the folder displayed in the source file display. You can override the current directory by using the **cd** directive before the **CLI** command (requires using the advanced command editor).

*Example:* `CLI DOSPROMPT`
</td></tr><tr><td>
</td><td>
</td><td>

**selfolder**</td><td>

Uses the first selected sub-folder in the source display as the CD for the DOS prompt.

*Example:* `CLI DOSPROMPT=selfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**admin**</td><td>

On Vista and above, opens the DOS prompt elevated (after a UAC prompt).

*Example:* `CLI DOSPROMPT=admin`
</td></tr><tr><td>
</td><td>
</td><td>

**noadmin**</td><td>

Prevents the DOS prompt from being elevated.

*Example:* `CLI DOSPROMPT=noadmin`
</td></tr><tr><td>
</td><td>
</td><td>

**powershell**</td><td>

Opens a PowerShell prompt rather than a DOS prompt.

*Example:* `CLI DOSPROMPT=powershell,admin`

The separate **EXEC** and **TITLE** arguments can be used to choose which version of PowerShell to run and set the window title.
</td></tr><tr><td>
</td><td>
</td><td>

**powershellise**</td><td>

Opens a PowerShell ISE rather than a DOS prompt.

*Example:* `CLI DOSPROMPT=powershellise`

When launching a PowerShell ISE, any color parameters are ignored. This limitation affects the ISE only; DOS prompts and normal PowerShell windows can both have colors specified.
</td></tr><tr><td>
</td><td>
</td><td>

**color=***\<color\>*</td><td>

Sets the text and background colors of the DOS window. You can use this by itself, or in conjunction with the admin argument to override the default color when the prompt is elevated.  
The \<color\> value is specified with two hexadecimal digits - the first corresponds to the background color, and the second to the foreground. The possible colors depend on your system's settings but are as below by default:

**Supported color values**  
\<WRAP\>

|               |                  |                  |                  |
|---------------|------------------|------------------|------------------|
| 0 = Black     | 1 = Blue         | 2 = Green        | 3 = Aqua         |
| 4 = Red       | 5 = Purple       | 6 = Yellow       | 7 = White        |
| 8 = Gray      | 9 = Light Blue   | A = Light Green  | B = Light Aqua   |
| C = Light Red | D = Light Purple | E = Light Yellow | F = Bright White |

\</WRAP\>\<wrap clear/\>

Note that you must enclose the entire value of the **DOSPROMPT** argument in quotes when using the **color** parameter (otherwise the embedded **=** sign will confuse the command parser).

*Example:* `CLI DOSPROMPT="admin,color=97"`
</td></tr><tr><td>
</td><td>
</td><td>

**nocolor**</td><td>

Prevents the color of the DOS prompt from being set when elevated.

*Example:* `CLI DOSPROMPT=admin,nocolor`
</td></tr><tr><td>
</td><td>
</td><td>

**wsl**</td><td>

Opens a WSL (Windows Subsystem for Linux) shell window. Note that WSL must be installed from the Windows Store.

*Example:* `CLI DOSPROMPT=wsl`
</td></tr><tr><td>
EXEC</td><td>
/K</td><td>

*\<command\>*</td><td>

Overrides the default executable to launch when opening a PowerShell prompt. For example, you may wish to create a button which runs PowerShell 7 instead of Windows PowerShell.

*Example:* `CLI DOSPROMPT=powershell EXEC="C:\Program Files\PowerShell\7\pwsh.exe"`
</td></tr><tr><td>
QUICKCMD</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Command mode, which lets you enter an ad-hoc Opus command to execute in the current file display. This lets you bind a [hotkey](/Manual/customize/the_customize_dialog/keys.md) to bring the FAYT field up in the specific mode.

*Example:* `CLI QUICKCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Command mode, and initialises it with the specified command.

Prefix with **noselect:** to place the cursor at the end of the command instead of initially selecting it for typing over.

*Example:* `CLI QUICKCMD Help`  
*Example:* `CLI QUICKCMD noselect:Help`
</td></tr><tr><td>
QUICKDOSCMD</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in DOS Command mode, which lets you enter a command to execute in a DOS prompt.

*Example:* `CLI QUICKDOSCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in DOS Command mode, and initialises it with the specified command.

Prefix with **noselect:** to place the cursor at the end of the command instead of initially selecting it for typing over.

*Example:* `CLI QUICKDOSCMD dir`  
*Example:* `CLI QUICKDOSCMD noselect:dir`
</td></tr><tr><td>
QUICKFILTER</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Filter mode, which lets you filter the current file list.

*Example:* `CLI QUICKFILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Filter mode, and initialises it with the specified pattern.

Prefix with **noselect:** to place the cursor at the end of the pattern instead of initially selecting it for typing over.

*Example:* `CLI QUICKFILTER \*.(jpg\|png)`  
*Example:* `CLI QUICKFILTER noselect:\*.jpg`
</td></tr><tr><td>
QUICKFIND</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Find mode, which lets you scroll to the first file matching the entered string.

*Example:* `CLI QUICKFIND`
</td></tr><tr><td>
</td><td>
</td><td>

*\<search string\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Find mode and initialises it with the specified string.

Prefix with **noselect:** to place the cursor at the end of the string instead of initially selecting it for typing over.

*Example:* `CLI QUICKFIND di`  
*Example:* `CLI QUICKFIND noselect:di`
</td></tr><tr><td>
QUICKFINDREPEAT</td><td>
/O</td><td>

*(no value)*</td><td>

Repeats the last **QUICKFIND**. The behaviour of this command depends on the state of the **Keep highlights visible after field closes** Preferences setting.

If highlights are shown even after the FAYT field closes, **QUICKFINDREPEAT** shifts focus to the next match. If highlights are not shown, **QUICKFINDREPEAT** repeats the last find, searching for matches again in the current folder, using the same search string as last time.

*Example:* `CLI QUICKFINDREPEAT`
</td></tr><tr><td>
</td><td>
</td><td>

**next**</td><td>

Explicitly searches for the next match, whether highlights are visible or not.

*Example:* `CLI QUICKFINDREPEAT=next`
</td></tr><tr><td>
</td><td>
</td><td>

**prev**</td><td>

Explicitly searches for the previous match, whether highlights are visible or not.

*Example:* `CLI QUICKFINDREPEAT=prev`
</td></tr><tr><td>
QUICKFOLDERS</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Folders mode, which shows a list of folders drawn from the tab history list, recent list, favorites and Quick Access. The sources for this list can be configured from the [Folders Mode](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/folders_mode.md) Preferences page.

*Example:* `CLI QUICKFOLDERS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<search string\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Folders mode, and initialises it with the specified search string.

Prefix with **noselect:** to place the cursor at the end of the string instead of initially selecting it for typing over.

\`\`CLI QUICKFOLDERS noselect:C:\\\`
</td></tr><tr><td>
QUICKFTPCMD</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in a special mode that lets you enter a command to send directly to a remote FTP server. This command only works when you are currently connected to an FTP site. You can view the results of your command in the [FTP log](/Manual/ftp/ftp_log.md).

*Example:* `CLI QUICKFTPCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in FTP command mode, and initialises it with the specified command.

Prefix with **noselect:** to place the cursor at the end of the command instead of initially selecting it for typing over.

*Example:* `CLI QUICKFTPCMD chmod \* 755`  
*Example:* `CLI QUICKFTPCMD noselect:chmod` \*
</td></tr><tr><td>
QUICKGO</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in a special mode ("go" mode) that lets you navigate to another folder in the current file display.

*Example:* `CLI QUICKGO`
</td></tr><tr><td>
</td><td>
</td><td>

*\<path\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in "go" mode, and initialises it with the specified path.

Prefix with **noselect:** to place the cursor at the end of the path instead of initially selecting it for typing over.

*Example:* `CLI QUICKGO C:\Program Files`  
\`\`CLI QUICKGO noselect:C:\\\`
</td></tr><tr><td>
QUICKRANGE</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Range mode, which lets you select files by index (or by a range of indices). This only works when the Index column has been added to the file display.

*Example:* `CLI QUICKRANGE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<range\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Range mode, and initialises it with the specified range string.

Prefix with **noselect:** to place the cursor at the end of the range string instead of initially selecting it for typing over.

*Example:* `CLI QUICKRANGE 1-10,20-30`  
*Example:* `CLI QUICKRANGE noselect:1-10`
</td></tr><tr><td>
QUICKSEARCH</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Search mode, which lets you initiate a [Windows Search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) of the current folder.

*Example:* `CLI QUICKSEARCH`
</td></tr><tr><td>
</td><td>
</td><td>

*\<query term\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Search mode, and initialises it with the specified query term.

Prefix with **noselect:** to place the cursor at the end of the query string instead of initially selecting it for typing over.

*Example:* `CLI QUICKSEARCH author:davidson`  
*Example:* `CLI QUICKSEARCH noselect:author:davidson`
</td></tr><tr><td>
QUICKSEARCHENGINE</td><td>
/K</td><td>

*\<engine\>\[,\<options\>\]*</td><td>

Use with the **QUICKSEARCH** argument to specify the search engine to use in Search mode. Each search engine has its own set of options which can also be included in the command.

Note that the **everything** and **everythingglobal** engines require [Everything](/Manual/additional_functionality/everything_integration.md) to be installed.

| Engine           | Description                                                                           | Options        |
|------------------|---------------------------------------------------------------------------------------|----------------|
| everything       | Search the current folder using *Everything*                                          | case           |
|                  |                                                                                       | diacritics     |
|                  |                                                                                       | wholeword      |
|                  |                                                                                       | regexp         |
| everythingglobal | Search the whole system using *Everything*                                            | case           |
|                  |                                                                                       | diacritics     |
|                  |                                                                                       | wholeword      |
|                  |                                                                                       | regexp         |
| opus             | Search using the Opus [find tool](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) | anywords       |
|                  |                                                                                       | case           |
|                  |                                                                                       | content        |
|                  |                                                                                       | nodiacritics   |
|                  |                                                                                       | nonames        |
|                  |                                                                                       | nopartial      |
|                  |                                                                                       | nowild         |
|                  |                                                                                       | utf8           |
| windows          | Search the current folder using Windows Search                                        | noautowildcard |
|                  |                                                                                       | nqs            |

*Example:* `CLI QUICKSEARCH A\*.jpg QUICKSEARCHENGINE everything,case`
</td></tr><tr><td>
QUICKSELECT</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Select mode, which lets you select files in the current folder by [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md).

*Example:* `CLI QUICKSELECT`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Select mode and initialises it with the specified pattern.

Prefix with **noselect:** to place the cursor at the end of the pattern instead of initially selecting it for typing over.

*Example:* `CLI QUICKSELECT \*.doc`  
*Example:* `CLI QUICKSELECT noselect:\*.doc`
</td></tr><tr><td>
QUICKTABS</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Tabs mode, which lets you search and switch folder tabs.

*Example:* `CLI QUICKTABS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<pattern\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in Tabs mode and initialises it with the specified text.

Prefix with **noselect:** to place the cursor at the end of the text instead of initially selecting it for typing over.

*Example:* `CLI QUICKTABS docu`  
*Example:* `CLI QUICKTABS noselect:docu`
</td></tr><tr><td>
QUICKWSLCMD</td><td>
/O/R</td><td>

*(no value)*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in WSL script mode, which lets you enter a command to execute in a WSL (Windows System For Linux) window. Note that WSL needs to be installed from the Windows Store.

*Example:* `CLI QUICKWSLCMD`
</td></tr><tr><td>
</td><td>
</td><td>

*\<command\>*</td><td>

Displays the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in WSL script mode, and initialises it with the specified command.

Prefix with **noselect:** to place the cursor at the end of the command instead of initially selecting it for typing over.

*Example:* `CLI QUICKWSLCMD ls`  
*Example:* `CLI QUICKWSLCMD noselect:ls`
</td></tr><tr><td>
SCRIPTMODE</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the CLI in Script Mode, which provides a simple way to test [scripts](/Manual/scripting/README.md) before adding them to buttons.

*Example:* `CLI SCRIPTMODE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<language\>*</td><td>

Displays the CLI in Script Mode with the language type set to the specified language. If you don't specify a language the CLI will remember the previous language used.

*Example:* `CLI SCRIPTMODE=jscript`
</td></tr><tr><td>
TITLE</td><td>
/K</td><td>

*\<command\>*</td><td>

Defines the window title when opening a PowerShell prompt.

*Example:* `CLI DOSPROMPT=powershell TITLE="Windows PowerShell"`
</td></tr></tbody>
</table>

