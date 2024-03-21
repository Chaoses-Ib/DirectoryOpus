# From the Win + E hotkey

This page lets you configure what happens when you push the <kbd>Win+E</kbd> hotkey.

This page is only shown on Windows 10 and above, and where Explorer Replacement is available (a normal installation or a portable install with Explorer Replacement enabled in the [portable .ini file](/Manual/additional_functionality/exporting_to_usb.md).)

The <kbd>Win+E</kbd> hotkey is what many people are used to using to open a new File Explorer window. When using Opus instead of Explorer, you'll probably want the hotkey to open Opus instead.

The options below let you configure what happens when you push the hotkey:

- **Open File Explorer as normal**: The <kbd>Win+E</kbd> hotkey will open File Explorer the same as it would have before Directory Opus was installed.
- **Bring the last active Lister to the front**: If there are one or more Listers already open, the <kbd>Win+E</kbd> hotkey will activate the one you were using most recently and bring it to the front. If no Listers are open, a new one is opened using the Default Lister settings. If you are using Windows 10's *virtual desktops* feature, only windows on the currently active desktop will be considered, unless you turn off the advanced **[Advanced](../miscellaneous/advanced_options.md)** setting.
- **Open the Default Lister**: Always opens a new Lister using the settings for the [Default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md).
- **Open a saved Lister layout**: Opens a saved [Lister layout](/Manual/basic_concepts/the_lister/layouts/README.md). If you turn on the **Close existing Listers** option then any existing Listers will be closed before opening the layout - if this is off, existing Listers will be unaffected.
- **Run a command**: Lets you enter a command to be run whenever the hotkey is pushed. This can be used to perform more complex actions including running external programs. This must be a command that would make sense on a button or hotkey. You can use [Opus internal commands](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) or external programs (passing arguments to them using the [standard control codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)). If you want to run more than a simple single-line command, you can create a more complicated [user-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md) and then specify the name of the user command here.

##### Win+E before Windows 10

On earlier versions of Windows, we do not have as much control over the Win + E hotkey and it will typically cause the *This PC* to open in the default file manager, which will be Opus if it is set to replace Explorer.

If you wish to customize what <kbd>Win+E</kbd> does on earlier versions of Windows, try creating a [System-Wide Hotkey](/Manual/additional_functionality/system-wide_hotkeys.md) which overrides the standard one. (Note that if you set up a hotkey that way on Windows 10, it may override the settings on this Preferences page. Only use one method or the other.)
