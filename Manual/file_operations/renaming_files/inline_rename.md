# Inline Rename

*Inline Rename* is the method of renaming files you're probably most familiar with, as it is the method that File Explorer uses. You edit the name of the file directly in the Lister, and pressing the <kbd>Enter</kbd> key applies the change immediately. It's straightforward, but only lets you rename one file at a time.

![](/Manual/images/media/13/inline_rename.png)

To enter *Inline Rename* mode in Opus is basically the same as in File Explorer - select the file and press <kbd>F2</kbd>, click it twice (with a long delay between clicks), or right-click and choose Rename from the context menu. However you get there, simply edit the filename as desired and press <kbd>Enter</kbd> to accept the change.

To exit *Inline Rename* mode without changing the name of the file, press the <kbd>Escape</kbd> key.

Opus provides some additional functionality in this mode that may not be immediately apparent, including:

### Changing what's selected by default

Initially only the stem of the filename is selected, not the entire name. Normally you don't want to change a file's extension, so auto-selecting only the stem saves you having to deselect the extension manually. You can change what's initially selected with the **Default selection mode** option on the [Renaming Files](/Manual/preferences/preferences_categories/file_operations/renaming_files/README.md) Preferences page.

You can also control the intiial selection using the `Rename INLINE` raw command. For example, this would let you configure one [hotkey](/Manual/customize/the_customize_dialog/keys.md) to enter inline rename with the filename stem selected, and another hotkey with the file extension selected instead.

### Select different parts of the name

- <kbd>Ctrl+A</kbd> to select all
- <kbd>Ctrl+N</kbd> or <kbd>Ctrl+F</kbd> to select the stem
- <kbd>Ctrl+E</kbd> to select the extension
- <kbd>F2</kbd> to cycle between selecting the stem, selecting the extension, and selecting the whole name.

### Change case

- <kbd>Ctrl+L</kbd> to lower-case all
- <kbd>Ctrl+U</kbd> to upper-case all
- <kbd>Ctrl+W</kbd> to capitalize all words
- <kbd>Ctrl+P</kbd> to capitalize the first word

### Replace dots and underscores with spaces

- <kbd>Ctrl+.</kbd> (on the main keyboard, not the numeric keypad) to replace dots and underscores with spaces in the current selection.

Dots with numbers on both sides are left alone: For example, *"setup_ultima_underworld2_2.1.0.20"* would become *"setup ultima underworld2 2.1.0.20"*.

### Move to next or previous file

- <kbd>Down</kbd> (or <kbd>Tab</kbd>) to move to the next file
- <kbd>Up</kbd> (or <kbd>Shift+Tab</kbd>) to move to the previous file

Any changes you have made to the current file will be applied and the rename field will be moved to the next or previous file automatically. If you use this you can turn on the **Retain cursor position when moving to next/previous file** option on the [Renaming Files](/Manual/preferences/preferences_categories/file_operations/renaming_files/README.md) Preferences page to have the cursor position retained from one file to the next.

### History of previously used names

- <kbd>Ctrl+Up</kbd> (or <kbd>Shift+Up</kbd>) to move up through the history
- <kbd>Ctrl+Down</kbd> (or <kbd>Shift+Down</kbd>) to move down through the history

### Copy names from adjacent files

- <kbd>Ctrl+Shift+Up</kbd> (or <kbd>Ctrl+'</kbd>) to copy the name from the previous file
- <kbd>Ctrl+Shift+Down</kbd> to copy the name from the next file
- <kbd>Ctrl+Shift+Home</kbd> to reset the item to its original name and reset the up/down position (except in Thumbnails and Large Icon modes, where it selects to the start of the filename, not just the start of the current line)

Continue to press the keys to move up/down the list of neighboring files to copy their filenames. Hold the <kbd>Alt</kbd> key down as well as the above keys to also copy the extension.

### Fully configurable key strokes

A number of other key strokes are defined by default - and they are all configurable via the [Renaming Files / Control Keys](/Manual/preferences/preferences_categories/file_operations/renaming_files/control_keys.md) page in Preferences. You can see what keys are defined, change their assignments and behaviors, and even create your own.
