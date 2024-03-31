# From the Desktop

The options here let you launch Opus or run another command by double-clicking on the Windows desktop. This can provide an extremely quick way to access a Lister when you have no windows currently open - simply find an empty area of the desktop (one with no icons on it) and double-click.

- **Disable**: Select this to disable double-click on the desktop.
- **Bring the last active Lister to the front**: If there are one or more Listers already open, a double-click on the desktop will bring to the front the one you used most recently. If no Listers are open a new one is opened using the Default Lister settings. If you are using Windows 10's *virtual desktops* feature, only windows on the currently active desktop will be considered, unless you turn off the advanced **[Advanced](../miscellaneous/advanced_options.md)** setting.
- **Open the Default Lister**: Opens a new Lister using the settings for the [Default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md).
- **Open a saved Lister layout**: Opens a saved [Lister layout](/Manual/basic_concepts/the_lister/layouts/README.md). If you turn on the **Close existing Listers** option then any existing Listers will be closed before opening the layout - if this is off, existing Listers will be unaffected.
- **Run a command**: Lets you enter a command to be run whenever the desktop is double-clicked. This can be used to perform more complex actions including running external programs. This must be a command that would make sense on a button or hotkey. You can use [Opus internal commands](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) or external programs (passing arguments to them using the [standard control codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)). If you want to run more than a simple single-line command, you can create a more complicated [user-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md) and then specify the name of the user command here.

### DOpusRT

When any of the double-click options are enabled, Opus launches a small helper application called **[DOpusRT.exe](/Manual/reference/dopusrt_reference/README.md)** that runs continuously in the background. This is added to the registry to run automatically on startup, and means that double-click on the desktop works even when Opus itself isn't running (**DOpusRT.exe** will launch Opus automatically if it's not already running when you double-click).

In order to trap double-clicks on the desktop (which runs in another process to Opus) it's necessary to "inject code" into Explorer - if you have an anti-virus or anti-spyware tool installed you may find it detects this and complains. If you find that double-click on the desktop isn't working check if something is blocking **DOpusRT.exe** from hooking into Explorer or from running on startup.

The **Restart DOpusRT.exe** button can be used when troubleshooting problems. It will attempt to stop any current instance of DOpusRT.exe and start a new one. It will also tell you if the whole Opus process is running elevated, which can cause problems by preventing messages from Explorer reaching Opus.

If you click the **Restart DOpusRT.exe** button and find that desktop double-click starts working, but then fails again after the next reboot, one possibility is a conflict with another program which is started after DOpusRT.exe when you reboot. You can use the **Delay DOpusRT.exe** option to make it wait a specified number of seconds before starting to work around that kind of problem. The exact delay needed will depend on the software causing the conflict.
