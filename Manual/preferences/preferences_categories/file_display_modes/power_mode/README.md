# Power Mode

This page contains options that control the appearance and behavior of file displays when they are set to *Power* mode. *Power* mode is like *Details* mode except that you have far more control over the behavior of the file display in this mode.

- **Always in *keyboard mode***: *Power* mode file displays are not in *keyboard mode* by default - the cursor keys scroll the list rather than moving the focus from one item to another. When this option is on, power mode file displays are always in *keyboard mode* - the cursor keys act like they do in a details mode file display.
- **Activate Keyboard Mode when a partial filename is typed:** If this option is turned on, typing into the file display to activate the [Find-as-you-type field](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) will also place the file display in keyboard mode.
- **Automatically select first file in folder**: When navigating to a new folder, this option causes the first item in the list to be selected automatically.
- **Display Power mode toolbar buttons**: Buttons that turn on Power mode are hidden by default because Power mode tends to be confusing for people who don't realise what it is. Turn this option on to make those buttons visible.
- **<kbd>Enter</kbd> key opens all selected files**: \<wrap\>When the file display isn't in *keyboard mode*, the <kbd>Enter</kbd> key normally does nothing - with this option on, any selected files will be opened when <kbd>Enter</kbd> is pressed.

When the file display is in *keyboard mode*, this option controls whether all selected files are opened when <kbd>Enter</kbd> is pressed, or only the file that currently has input focus. \</wrap\>

- **Sort-field specific key scrolling**: Normally, when you type in the file display (and the [Find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field comes up in Find mode), Opus will search for items by name and scroll to show them. If this option is on, the current sort field can affect this behavior - for example, if the list is sorted by the *Type* column, the FAYT field will search for items by file type rather than by name.
