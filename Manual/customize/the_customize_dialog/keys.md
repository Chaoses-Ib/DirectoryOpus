# Keys

The Keys page lets you view and configure "keyboard shortcuts" or "hotkeys" (combinations of keys) that can be used to run commands or launch programs. Opus lets you assign one or more keys to a toolbar button or menu command, and pressing the key has the same effect as clicking the button. You can also create "hotkey-only" functions, which only exist as key assignments and aren't linked to a toolbar.

You can quickly get to this page of the Customize dialog via **Help \> Keyboard Map** in the default menus. You'll see a list of all the defined hotkeys, grouped into the following categories:

- **Hotkeys**: These are functions that exist purely on this page as a hotkey function. They are active only inside a Lister.
- **Toolbars**: These are hotkeys assigned to a toolbar button. They are active only inside a Lister.
- **Favorite Folders**: These are hotkeys assigned to [Favorite](/Manual/basic_concepts/the_lister/navigation/favorites.md) folders. They are active only inside a Lister.
- **Hotkeys (System-wide)**: These are hotkey-only functions that are active throughout Windows - they work whether Opus is active or not.
- **Floating Toolbars (System-wide)**: These are hotkeys assigned to a toolbar button in a [floating toolbars](/Manual/additional_functionality/floating_toolbars/RAEDME.md). They are active globally, but the toolbar must have its **Enable Hotkeys** option turned on to enable them.
- **Tray Menu (System-wide)**: These are any hotkeys assigned to functions in the [taskbar icon context menu](context_menus.md). They are active throughout Windows.
- **Image Viewer (Keys)**: These are hotkeys that are only active in the [standalone image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md).
- **Image Viewer (Toolbar)**: These are hotkeys assigned to a toolbar button in the currently designated toolbar for the [standalone image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md).

![](/Manual/images/media/customize_-_keys.png)

The checkboxes next to each key in the list let you temporarily disable a hotkey without having to delete it.

Use the toolbar at the top of the page to manipulate the hotkeys. The buttons are ![](/Manual/images/media/favorites_-_add.png) (create new hotkey), ![](/Manual/images/media/filters_-_duplicate.png) (duplicate an existing key), ![](/Manual/images/media/favorties_-_edit.png) (edit the selected key) and ![](/Manual/images/media/favorites_-_delete.png) (delete the selected key).

The ![](/Manual/images/media/keys_-_locate_toolbar.png) (Locate toolbar) button is active whenever a hotkey in a **Toolbars** category is selected - clicking it will highlight the toolbar button that the hotkey comes from (it will also open any sub-menus needed to make the button visible).

You can only delete items in the **Hotkeys** category* *through this page - toolbar buttons can only be deleted from the toolbar itself. *Favorites*-type keys can't actually be edited from this page at all - they are shown in the list as a convenience, but you have to use the [Favorites](/Manual/preferences/preferences_categories/favorites_and_recent/favorites.md) page in Preferences to edit them.

Clicking the ![](/Manual/images/media/favorites_-_add.png) button to create a new hotkey displays the standard [Command Editor](../creating_your_own_buttons/command_editor/RAEDME.md)with the addition of the **System-wide Hotkey** option, which you can turn on to make the new hotkey global.

Clicking the ![](/Manual/images/media/favorties_-_edit.png) button will display the standard [Command Editor](../creating_your_own_buttons/command_editor/RAEDME.md) for the selected key, but if all you want to change is the key itself (and not the function), you can use the **Change Key** field at the top of the page. Select the key you want to change, click in the change key field, press the new key combination and then use the ![](/Manual/images/media/change_key.png) button to accept the change.  

The **Change Key** field, as well as the hotkey field in the Command Editor (and the filter field at the bottom of this page) are all special controls designed to make it easy to enter a key combination. See the page on [Using the Hotkey Control](../creating_your_own_buttons/command_editor/using_the_hotkey_control.md) for more information.

You can also define keys that use the **Windows** key. Windows itself defines many hotkeys using the **Windows** key (e.g. **Windows+E** opens an Explorer window), but Opus lets you override these for global hotkeys. To override one of the standard Windows hotkeys, create a new hotkey, turn on the **System-wide Hotkey** option, and then use the key field to enter the key combination as you would any other. (Note: How well this works depends on the version of Windows, since hotkeys involving the **Windows** key may be intercepted by the operating system at a low level. If you are on Windows 10 or above and just want to change what the **Windows + E** hotkey does, [Preferences / Launching Opus / From the Win + E hotkey](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.md) may be easier and more reliable.)

At the bottom of the page is a filter field that lets you filter the hotkey list. This filter has two modes. The default mode is to show hotkeys that use a specified key combination. For example, click in the field, press the **A** key and then click the filter button to the right to show all functions that use the **A** key in some way. Click the red X button to clear the filter and re-display all the keys.

![](/Manual/images/media/key_filter.png)

Click the keyboard icon (![](/Manual/images/media/key_filter_button.png)) to switch the filter to the other mode, in which it filters based on the name, function and description of the hotkey. For example, in this mode typing "rename" would filter the list to show all hotkeys related to renaming functions.

The **Export Keys **command in the *File* menu for this page let you export your hotkeys list in three different formats (use the **Save as type** drop-down in the save dialog to choose what type to use).

- *Importable Hotkey Format* is a format that you can use to export your hotkeys in order to re-import them into Directory Opus (e.g. on another computer, or to share your keys with a friend). Selecting this format actually exports the functions as well as the key information. When this format is selected only your *Hotkeys* and *Media Keys* are exported.
- *Comma-Separated List* exports a list of all the hotkeys along with their names and descriptions (but not the functions they run) as a **.csv** file. For example, you could use this if you wanted to make yourself a printable key reference. You could import this file into Excel or Word and perform further manipulation on it before printing. In this mode, all types of hotkeys are exported.
- *Text Format* exports a list of all your hotkeys as a plain text file. Like the *Comma-Separated List* option, all types of hotkeys are exported in this mode.

The **Import Keys **command in the *File* menu lets you import a previously-exported *Importable Hotkey Format* file. You will be given the choice of merging the keys in the imported file with your existing ones, or replacing your existing hotkeys completely.
