# DOpusRT Reference

DOpusRT is a separate program (**dopusrt.exe**) that performs various support functions for Directory Opus:

- If [Double-click on the desktop](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_desktop.md) is enabled, it runs in the background on startup to detect double-clicks and launch Opus when it's not already running.
- If [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) mode is enabled, it is used as the default "handler" when opening a folder (and again, it can launch Opus when not already running).
- You can use it to run internal commands from outside of Opus.
- You can use it to display a picture with the standalone viewer from outside of Opus.
- You can use it to manipulate [file collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md) from outside of Opus.
- You can use it to [retrieve information about currently displayed folders and files](/Manual/reference/dopusrt_reference/retrieving_file_and_folder_information.md) from outside of Opus.

The program **dopusrt.exe** is located in the main Opus program folder (normally *C:\Program Files\GPSoftware\Directory Opus*). Note that if you are invoking DOpusRT from an Opus button or hotkey, you don't need to use the full path - you can use the **dopusrt** keyword as a shortcut for the actual location of the .exe. Otherwise, you would normally need to specify the full path of the command when using it (for example, in a shortcut or a batch file). In the examples below, the full path is omitted for clarity.

The DOpusRT command line consists of a *command* followed by *arguments* appropriate to that command. For completeness, all **dopusrt.exe** commands are listed here - but many are designed to only be used by Opus itself. The commands you will most probably be interested in are are **/cmd** and **/col**.

\<commandtable columns="3" id="cmdtable_1"\> \$\$ Command \$\$ Arguments \$\$ Description \$\$ **/acmd** \$\$ *\<command and arguments\>* \$\$ Invokes an Opus command from outside of Opus. If one or more Opus listers are open, the command is sent to the one which is, or was most recently, the active window.

//<Example://> **dopusrt.exe /acmd Go "C:\Program Files"**  
**                    -** *navigates to "C:\Program Files" in the last-active window (or in a new window if there isn't one)*  
\$\$ **/argsmsgbox** \$\$ *(no arguments)* \$\$ Displays any remaining arguments in a message box. This can be useful when you wish to see the exact command-line that an Opus command is generating when calling an external command.

//<Example://> **dopusrt.exe /argsmsgbox Hello World**  
**                   ** *- display "Hello World" in a message box*  
\$\$ **/argstoclip** \$\$ *(no arguments)* \$\$ Puts any remaining arguments into the clipboard. As with **/argsmsgbox**, this can be useful for checking what Opus would pass to an external command.

Note that Opus has a built-in **[Clipboard](command_reference/internal_commands/clipboard.md)** command which is a better choice if you just want to put some text or filenames into the clipboard.

//<Example://> **dopusrt.exe /argstoclip Hello World**  
**                   ** *- put "Hello World" into the clipboard*  
\$\$ **/changelanguage** \$\$ *\<language\>* \$\$ Changes the user-interface language. Opus will restart, and toolbars and menus will be translated (if possible).

//<Example://> **dopusrt.exe /changelanguage deutsch**  
**                   ** *- change language to German*  
\$\$ **/cmd** \$\$ *\<command and arguments\>* \$\$ Invokes an Opus command from outside of Opus. If one or more Opus listers are open, the command is sent to the Source window. (Compare this with\*\* /acmd\*\*, above.)

//<Example://> **dopusrt.exe /cmd Go C:\\ NEW=0,0,640,480**  
**                    -** *opens a new Lister showing C:\\ at the specified coordinates*  
\$\$ **/col** \$\$ *\<collection command\>* \$\$ Lets you manipulate file collections from outside of Opus. See the [External Manipulation of File Collections](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.md) page for more information.

*<Example://> **dopusrt.exe /col create "Holiday Photos"**  
**                    ***- creates a collection called// Holiday Photos  
\$\$ **/dblclk**  
\$\$ *(no arguments)* \$\$ Runs in the background to manage the double-click on the desktop feature.

You do not need to run this command manually - Opus starts it automatically when the desktop double-click option is enabled.  
\$\$ \$\$ **=off** \$\$ Deactivate a running double-click manager. You can use this command if you want to temporarily disable the desktop double-click feature (rather than using Task Manager to kill the **dopusrt.exe** instance).

*<Example://> **dopusrt.exe /dblclk=off**  
**                    ***- shuts down the double-click on desktop handler//  
\$\$ **/dde** \$\$ *(no arguments)* \$\$ Run a DDE server to listen for DDE commands relating to opening folders.

This is used in Explorer Replacement mode when you double-click on a folder. You do not need to run this command manually.  
\$\$ **/delay** \$\$ ***=*\<seconds\>**** \$\$ Only valid after **/dblclk**. Causes the desktop double-click functionality to wait the specified number of seconds before setting itself up. This can be used to work around conflicts with other software that will break desktop double-click if it starts later in the Windows boot cycle.

*<Example://> **dopusrt.exe /dblclk /delay=10**  
**                    ***- waits 10 seconds before desktop double-click initializes//  
You do not normally need to use this argument yourself, but may see it in the registry. You can specify a delay via Preferences when configuring desktop double-click.  
\$\$ **/flushplugins** \$\$ *(no arguments)* \$\$ Flush viewer plugins from memory. If Opus is running, any plugins not currently in use will be unloaded. You can use this if you are developing a plugin and want to replace the DLL file without having to quit Opus.

*<Example://> **dopusrt.exe /flushplugins**  
**                    ***- flushes unused viewer plugins//  
\$\$ **/help** \$\$ *\<help path\>* \$\$ Displays the specified document from the local help in your web browser. This is used to implement the **opushelp://** URL scheme, which Opus registers when it's installed. \$\$ **/info** \$\$ *\<information command\>* \$\$ Lets you retrieve information about the currently displayed folders and files from outside of Opus. See the [Retrieving File and Folder Information](/Manual/reference/dopusrt_reference/retrieving_file_and_folder_information.md) page for more information.

//<Example://> **dopusrt.exe /info path_list.txt,paths**  
- *creates an XML file (path_list.txt) listing the currently displayed paths in all currently open Listers*  
\$\$ **/open** \$\$ *\<folder path\>* \$\$ Opens a new Lister showing the specified path.

*<Example://> **dopusrt.exe /open "C:\Program Files"**  
**                    ***- open a Lister showing the// C:\Program Files// folder//  
\$\$ **/restart**  
\$\$ *(no arguments)* \$\$ Restarts Opus if it is already running. If Opus is not already running it will be started.

*<Example://> **dopusrt.exe /restart**  
**                    ***- restarts or launches Opus//  
\$\$ \$\$ **:norun** \$\$ Restarts Opus if it is already running, but does not start it if it is not running.

*<Example://> **dopusrt.exe /restart:norun**  
**                    ***- restarts Opus if it's already running//  
\$\$ **/runopus** \$\$ *(no arguments)* \$\$ Starts Opus if it is not already running. Under Vista and above, this will always launch Opus as non-elevated, even if the process invoking **dopusrt.exe** is elevated.

*<Example://> **dopusrt.exe /runopus**  
**                    ***- runs Opus (non-elevated) if not already running//  
\$\$ **/runstd** \$\$ *\<command line\>* \$\$ Lets you launch another program. Under Vista and above, this will run the specified command as non-elevated, even if the process invoking **dopusrt.exe** is elevated (this is really the only point of this command).

*<Example://> **dopusrt.exe /runstd notepad.exe**  
**                    ***- runs notepad.exe as non-elevated//  
\$\$ **/show** \$\$ *\<filename\>* \$\$ Shows the specified file using the Opus [standalone viewer](/Manual/additional_functionality/viewing_images/RAEDME.md). You could use this to make the Opus viewer the default system image viewer for a file type.

*<Example://> **dopusrt.exe /show %1 **  
**                    ***- shows the selected image (definition for context menu item)*  
\$\$ **/vcmd** \$\$ \<*command and arguments//\> \$\$ Invokes an Opus command from outside of Opus, in the context of the currently (or most recently) active image viewer. If no image viewers are open the command will be ignored.

//<Example://> **dopusrt.exe /vcmd Show VIEWERCMD=selectall**  
**                    -** *selects the image in the currently active viewer* \$\$ *\<filename\>* \$\$ *(no arguments)* \$\$ DOpusRT can be called with the name of an external file to launch various Opus files. This behaviour is used by the default file type associations that Opus creates - for example, a **.dcf** file (an Opus command file, created by dragging a toolbar button to the desktop in Customize mode) is launched by passing its filename to **dopusrt.exe**.

The file types that can be invoked in this way are **.dcf** (command files), **.dpf** (exported Preferences files from older versions of Opus) and **.dop** (toolbars).

*<Example://> **dopusrt.exe C:\Commands\NewLister.dcf**  
**                    ***- executes the command in the exported command file//

\</commandtable\>

More:

[External Manipulation of File Collections](/Manual/reference/dopusrt_reference/external_manipulation_of_file_collections.md)  
[Retrieving File and Folder Information](/Manual/reference/dopusrt_reference/retrieving_file_and_folder_information.md)  
