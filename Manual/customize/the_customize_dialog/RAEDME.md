# The Customize Dialog

The *Customize* dialog appears when you enter [Customize](/Manual/customize/RAEDME.md) mode. It is divided into a number of tabbed pages.

- **[Toolbars](/Manual/customize/the_customize_dialog/toolbars.md)**: Displays a list of your toolbars, lets you turn them on or off, and create and edit new ones.
- **[Context Menus](/Manual/customize/the_customize_dialog/context_menus.md)**: This is where various context menus can be edited. The context menus for files and folders are not edited through here - instead they are controlled through the [File Types](/Manual/file_types/RAEDME.md) system. The context menus here are for user interface elements like the column header in a details mode file display, the taskbar icon and so on.
- **[Keys](/Manual/customize/the_customize_dialog/keys.md)**: Displays a list of all configured hotkeys and lets you edit them and create new ones.
- **[Commands](/Manual/customize/the_customize_dialog/commands.md)**: Displays a list of commands that you can easily add to toolbars by drag and drop. You can also build commands manually using the underlying [command set](/Manual/reference/command_reference/RAEDME.md).
- **[User Commands](/Manual/customize/the_customize_dialog/user_commands.md)**: Lets you add your own commands to the internal command set. You can use user commands anywhere the internal commands can be used.
- **[Default Toolbars](/Manual/customize/the_customize_dialog/default_toolbars.md)**: Shows the default toolbars and lets you drag buttons out to your own toolbars. This page can also highlight new commands that were added at various points in time, making it easier to keep your own custom toolbars up to date.

##### Page menu

At the top-right of the Customize dialog the ![](/Manual/images/media/13/prefs_menu.png) page menu contains a number of commands:

- **Import**: The behavior of this command depends on the currently selected page in the Customize dialog.
- **Export**: Same for this; what is actually exported depends on the current page.
- **Save Floating Toolbars**: This command saves the state and position of any floating toolbars that are currently displayed. For example, if you want to set up a floating toolbar to act as a program launcher, you would float it, position it as desired, and then choose this command to make Opus remember this for the future. If you turn on the **Save state of floating Toolbars automatically on exit** option on the [Toolbar Options](/Manual/preferences/preferences_categories/toolbars/toolbar_options.md) Preferences page, your floating toolbars will be remembered automatically when Opus shuts down.
- **Factory Reset**: Lets you reset the selected item in some contexts.
- **Undo Changes**: This command depends on the current selection in the current page. For example, on the Toolbars page it lets you restore the currently selected toolbar, undoing any changes to it since Customize mode was entered.
- **Undo All Changes**: This command will undo all changes to everything it is possible to undo since Customize mode was entered. Clicking the **Cancel** button on the Customize dialog has the same effect.

##### Customize shortcut

When you're in Customize mode, a mini-toolbar appears in the title bar of any open Listers.

![](/Manual/images/media/13/mini_customize.png)

This makes it easy to get back to the Customize dialog even if it's hidden below the Lister. Click the main part (the label) of the toolbar to bring the Customize dialog to the front. The checkmark and cross buttons also let you OK/Cancel the Customize dialog without needing to bring it forward first.
