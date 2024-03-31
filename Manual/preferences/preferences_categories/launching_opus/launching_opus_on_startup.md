# Startup

The settings on this page let you set Opus to run automatically when Windows starts up. You can also control what Listers are opened automatically when Opus starts, whether on Windows startup or if you start it up manually later on.

- **Launch Directory Opus automatically on system startup**: When Windows boots, Directory Opus will start running automatically. Having Opus always running means opening a Lister is much quicker, and it also lets you take advantage of configurable [system-wide hotkeys](/Manual/additional_functionality/system-wide_hotkeys.md) and [floating toolbars](/Manual/additional_functionality/floating_toolbars/README.md). Run-on-startup is implemented by adding a shortcut to the *Startup* program group in the Start menu.
  - **Don't open any Listers**: No Listers will open when Opus runs on system startup. The options below still apply if you quit Opus and then start it up again manually.

### What happens when Opus starts up

- **Open the Default Lister**: The Default Lister is opened.
- **Open the Listers that were open when the program was last closed**: When Opus quits it remembers which Listers were opened, and restores them the next time it starts.
  - **Backup open Listers automatically**: Opus will automatically save open Listers on the configured schedule (as well as when it shuts down).
  - **Restore each Lister to its original virtual desktop**: If using virtual desktops under Windows 10 or better, Listers will be put back on their original desktops when they reopen.
- **Open a saved Lister layout**: Opens a saved [Lister layout](/Manual/basic_concepts/the_lister/layouts/README.md).
- **Run a command**: Lets you enter a command to be run on startup. This can be used to perform more complex actions including running external programs. This must be a command that would make sense on a button or hotkey. You can use [Opus internal commands](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) or external programs (passing arguments to them using the [standard control codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)). If you want to run more than a simple single-line command, you can create a more complicated [user-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md) and then specify the name of the user command here.
