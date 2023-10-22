# Inline Rename

*Inline Rename* is the method of renaming files you're probably most familiar with, as it is the method that File Explorer uses. You edit the name of the file directly in the Lister, and pressing the **Enter** key applies the change immediately. It's straightforward, but only lets you rename one file at a time.

![](/Manual/images/media/inline_rename.png)

To enter *Inline Rename *mode in Opus is basically the same as in File Explorer - select the file and press **F2**, click it twice (with a long delay between clicks), or right-click and choose Rename from the context menu. However you get there, simply edit the filename as desired and press **Enter** to accept the change.

Opus provides some additional functionality in this mode that may not be immediately apparent:

1.  Initially only the stem of the filename is selected, not the entire name. Actually, File Explorer behaves like this too these days, but in Windows XP it selected the whole filename by default. Normally you don't want to change a file's extension, so auto-selecting only the stem saves you having to deselect the extension manually. You can change what's initially selected with the **[Default selection mode](/Manual/preferences/preferences_categories/file_operations/inline_rename.md)** option in Preferences.  
    - You can press **F2** to cycle between selecting the stem, selecting the extension, and selecting the whole name. You can also select these parts of the name by pressing **Ctrl+A** (select all), **Ctrl+N** or **Ctrl+F** (select stem) and **Ctrl+E** (select extension).  
    - You can change the case of the filename by pressing **Ctrl+L** (lower-case all), **Ctrl+U** (upper-case all), **Ctrl+W** (capitalize all words) or **Ctrl+P** (capitalize first word).  
    - You can replace dots and underscores with spaces in the selection by pressing **Ctrl+.** (on the main keyboard, not the numeric keypad). Dots with numbers on both sides are left alone: For example, *"setup_ultima_underworld2_2.1.0.20"* would become *"setup ultima underworld2 2.1.0.20"*.  
    - You can move to the next or previous file in the list by pressing **Cursor Down** (or **Tab**) or **Cursor Up** (or **Shift+Tab**). Any changes you have made to the current file will be applied and the rename field will be moved to the next or previous file automatically. If you use this you can turn on the **[Retain cursor position when moving to next/previous file](/Manual/preferences/preferences_categories/file_operations/inline_rename.md)** option in Preferences to have the cursor position retained from one file to the next.  
    - You can access a history of previously used filenames by holding either the **Ctrl** or **Shift** keys and pressing **Cursor Up** / **Down**.  
    - You can copy the name from the previous file by pressing **Ctrl+Shift+Up** (or **Ctrl+'**), or from the next file by pressing **Ctrl+Shift+Down** (hold the **Alt** key down as well to also copy the extension). Continue to press the keys to move up/down the list of neighboring files to copy their filenames. Pushing **Ctrl+Shift+Home** will reset the item to its original name and reset the up/down position.

To exit *Inline Rename* mode without changing the name of the file, press the **Escape** key.

As well as choosing the initial selection in Preferences (as described above), you can also control it using the **[Rename INLINE](/Manual/reference/command_reference/internal_commands/rename.md)** raw command. For example, this would let you configure one [hotkey](/Manual/customize/the_customize_dialog/keys.md) to enter inline rename with the filename stem selected, and another hotkey with the file extension selected instead.
