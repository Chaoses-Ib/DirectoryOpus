# Context Menu

The Context Menu tab lets you add commands to the context menu for files and folders. For example, Opus uses this system to display the "standard" context menu items of *Cut* / *Copy* / *Paste* etc. via the **All files and folders** file type.

![](/Manual/images/media/context_menu_-_all_files.png) 

When you right-click a file or folder to display its context menu, Opus searches the system registry and its own file type settings for the commands to display on the menu. The context menu is built from **all** the file types that match the file you have clicked on. So for example, the context menu for a **.jpg** file would include commands from the **JPEG Image** file type, the **Images** [file type group](../file_type_groups.md), the **[Recognized images](../directory_opus_file_types.md)** file type, the **[All files](../directory_opus_file_types.md)** file type, and the **[All files and folders](../directory_opus_file_types.md)** file type.

You can add two types context menu items using this page of the [file type editor](../filetype_editor/RAEDME.md):

- **Global**: Context menu items that are saved in the system registry, and will be displayed on the context menu in Explorer and other programs as well as in Opus. These commands must invoke external executable programs.
- **Opus-only**: Context menu items that are only displayed on context menus in Opus - they will not appear in Explorer. These commands can use internal Opus commands as well as invoking external programs.

Context menu commands that come from the system but aren't provided as "static verbs" in the registry (e.g. they use *context menu extension handlers*) can't be configured through this system. It is possible (with some fiddling) to control the display of these context menu items as well - see this [FAQ](https://resource.dopus.com/t/tip-organise-and-speed-up-context-menus/1204) for more information.

The **New** button at the bottom of this page lets you add a new context menu item to the file type. The **Edit** button lets you edit an existing one (or just double-click it in the list) and the **Delete** button lets you delete it. The **Set Default** button lets you set a *global* (but not *Opus-only*) context menu item as the default action for the file type - the command that will normally be run when you double-click the file.

You can also right-click on the items in the context menu list to display the context menu context menu (heh, sorry!). This context menu lets you use **Copy** and **Paste** to copy the definition from one command to another. There is also the **Begin a group** option which lets you place separators between context menu items. When you right-click on an item and choose **Begin a group**, a separator will appear above it (as you can see above the **Create Shortcut** command in the above screenshot).

You can use drag and drop to reorder the context menu items in the list, or to add or remove separators (by dragging the item a small distance and dropping it on itself). If you have two [File Type editor](../filetype_editor/RAEDME.md) dialogs open at once you can also drag and drop context menu definitions from one editor to another, to copy commands from one file type to another.

------------------------------------------------------------------------

When you add a new context menu item to a system file type, you need to choose whether it is going to be *global* or *Opus-only.*

![](/Manual/images/media/edit_new_action_for_type_jpeg_image.png) 

This is accomplished using the **Type** drop-down. This drop-down initially has four options:

- **Run an application**: Defines a context menu command that runs an external program. This will establish the item as global - it will show in the context menu in both Opus and Explorer.
- **DDE command**: Defines a command that communicates with an external program using DDE. This will also define the item as global - it will work in both Opus and Explorer.
- **Run an Opus function**: This will establish the item as Opus-only. Commands of this type can use Opus [internal commands](/Manual/reference/command_reference/internal_commands/RAEDME.md) as well as launch external programs. It will only be shown in context menus inside of Opus.
- **Sub-menu**: This is a special type (explained below) that lets you create sub-menus in context menus. This is also Opus-only.

Once a function has been defined as **Run an application** or **DDE command**, you can't turn it into a **Run an Opus function**-type item; and vice versa. If you click **OK** to save the new context menu item, and then select it and click **Edit** you will see that the **Type** field has disappeared (in the case of Opus-only functions), or now only contains options for **Run an application** and **DDE commands** (for global menu items).

If you add a context menu item to a [file type group](../file_type_groups.md) the first two type options aren't available - as groups only work inside of Opus it's not possible to add global menu items to them.

For all context menu item types, the **Action** field defines the label that is shown for the command in the context menu. The small box to the right of the **Action** field lets you specify an icon that's also shown in the context menu to the left of the label. The icon is only displayed when the context menu is opened in Opus - it's not supported by Explorer.

The **Application** field for a **Run an application**-type context menu command is where you define the path to the external program and any arguments you are passing it. For example, a command that opens the selected file in Notepad might look like this:

![](/Manual/images/media/context_menu_-_open_in_notepad.png) 

The **Application** command passes the selected filename to Notepad.exe using the **%1**[control code](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md).

**DDE Commands** are also supported in both Opus and Explorer. Although it's pretty unlikely you will ever need to define a DDE command these days, you can find more information about these in the [help for the Actions tab](actions.md).

The **Run an Opus function** type uses a variant of the standard [command editor](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.md) to define a function that can use both Opus [internal commands](/Manual/reference/command_reference/internal_commands/RAEDME.md) and external programs. You can see an example of this in the context menu for the default **Images** file type group:

![](/Manual/images/media/context_menu_-_convert_image.png) 

This screenshot shows that a context menu item to invoke the [Image Conversion](/Manual/additional_functionality/image_conversion/RAEDME.md) function has been defined for this file type. Because it uses an internal Opus command (**[Image](/Manual/reference/command_reference/internal_commands/image.md)**) this context menu won't appear in Explorer, only in Opus. Actually because this context menu is on the **Images** file type group it has to be an Opus-only command anyway, but it could also appear on the context menu for a system file type like **JPEG Images**.

![](/Manual/images/media/context_menu_-_convert_image_def.png) 

You can see that there is no **Type** drop-down, as the type of the item can't be changed from Opus-only. The standard [command editor](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.md) controls let you define the function. The label of the context menu item (**&Convert Image...**) is given in the **Action** field - the ampersand (**&**) in the label specifies which letter of the label is to be underlined in the context menu.

------------------------------------------------------------------------

The fourth option in the **Type** drop-down when creating a new menu item is **Sub-menu**. This lets you create sub-menus in context menus - you can move groups of commands off the main context menu and into a sub-menu to keep related commands together, or to keep the main context menu tidy. Sub-menus only work when context menus are displayed in Opus - they won't appear in Explorer. If a global context menu item is added to a sub-menu in Opus, it will appear on the main context menu in Explorer.

The only options for **Sub-menu** are **Label** and icon (to set the icon click the small box to the right of the **Label** field).

![](/Manual/images/media/context_menu_-_sub_label.png) 

In the context menu list, items that are in a sub-menu are shown as indented.

![](/Manual/images/media/context_menu_-_subs.png) 

In the above screenshot, the **Notepad** item will appear on the main context-menu, followed by a sub-menu called **Open in Something Else**. Inside that sub-menu are two items, **Notepad++** and **Opus Viewer**. Following the sub-menu (on the main menu) is another item, **Textpad**.

All context menu items that appear below a sub-menu in the list will automatically be placed in that sub-menu. To specify the item that marks a return to the top-level menu, you must right-click on it in the list and choose the **Decrease Indent** command. In the above screenshot, this command was run on the **Textpad** entry, which decreased its indent level and moved it back to the main menu.

![](/Manual/images/media/context_menu_-_context_menu.png) 

Sub-menus can be nested (you can have a sub-menu inside a sub-menu inside a sub-menu, and so on).

If you right-click on the first item below a sub-menu in the context menu editor, an option called **Button** will also be available. If you turn this option on, the sub-menu will act like a "menu button" - that is, you'll be able to click the sub-menu itself to run the first command within it, as well as popping the menu open to access its other commands.
