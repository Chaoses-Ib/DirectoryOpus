# Selecting with the mouse and keyboard

Selecting files with the mouse or keyboard, in all [view modes](../the_lister/view_modes.md) except Power mode, works similarly to Explorer.

##### Selecting files with the mouse

- Left-click a single file to select that file and deselect all others.
- <kbd>Ctrl</kbd>+left-click a file will toggle the selection state of that file, leaving all others unchanged.
- <kbd>Shift</kbd>+left-click a file to select a range of files. Click normally to select the first file in the range, then hold the <kbd>Shift</kbd> key and click again on the last file in the range. All files between and including those two will be selected.
- Use <kbd>Ctrl+Shift</kbd>+left-click to add a range to already selected files.
- Click on an empty part of the file display (i.e. not on a file) to deselect all files.
- Click on an empty part of the file display and (with the button still down) move to mouse to drag out a selection rectangle. All files you drag that rectangle over will be selected.
- Hold <kbd>Ctrl</kbd> when you click to drag the selection rectangle and any existing selections will be left unchanged. Additionally, files that you drag over will have their selection states inverted.
- **Middle**-click on a file to toggle its selection state (equivalent to <kbd>Ctrl</kbd>+left-click). You can also use the middle button to drag a selection rectangle that inverts the selections of files you drag over (equivalent to <kbd>Ctrl</kbd>+left-drag).
- You can also use the right button to drag a selection rectangle; once the button is released, the context menu will be shown for all selected items.

##### Selecting files with the keyboard

- <kbd>Ctrl+A</kbd> is the default hotkey to select all items in the list (the same as the **Edit / Select All** command).
- <kbd>Ctrl+I</kbd> inverts the selection state of all items in the list (the same as **Edit / Invert Selection**).
- The cursor keys (<kbd>Up</kbd>/<kbd>Down</kbd>/<kbd>Left</kbd>/<kbd>Right</kbd>, plus <kbd>Page Up</kbd>/<kbd>Page Down</kbd> and <kbd>Home</kbd>/<kbd>End</kbd>) can be used to move the selection (and deselect all other items) in the file display when it has input focus.
- You can combine <kbd>Shift</kbd> with the cursor keys to perform range selection using the keyboard - move the selection to the first file in the range, and then hold <kbd>Shift</kbd> and use the cursor keys to expand the range to the last item.
- Hold the <kbd>Ctrl</kbd> key to move the focus rectangle without changing the selection. You can use this to select multiple, non-contiguous files. For example, use the cursor keys to place the selection on a given file. Then hold the <kbd>Ctrl</kbd> key down and use the cursor keys to move the focus rectangle to another file - note that the first file is not deselected.
- <kbd>Space</kbd> when an item has input focus will select it. You can toggle the selection on the currently focused item by pressing <kbd>Ctrl+Space</kbd>.
- <kbd>Ins</kbd> toggles the selection of the current item, and automatically moves the input focus to the next item in the list.
- Typing a partial filename will activate the [find-as-you-type](../the_lister/find-as-you-type_field.md) field and place the selection on the first file matching the entered string.

##### Middle mouse button

Note that some mouse drivers map the middle mouse button to another function by default - if you find middle-click isn't working as expected, see the [FAQ](https://resource.dopus.com/t/how-to-make-logitech-mid-back-forward-buttons-work-in-opus/2972) for some hints on how to fix it. You can also configure Opus to treat a single middle-click as a double middle-click, which lets you obtain behavior similar to a web browser (e.g. single middle-click to open a folder in a new tab). See the **[File Displays / Mouse](/Manual/preferences/preferences_categories/file_displays/mouse/RAEDME.md)** Preferences page for details on that.

##### Power mode

In power mode, mouse and keyboard selection works slightly differently by default (although the behaviour of the mouse can be modified quite a lot from the **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/RAEDME.md)** Preferences page).

##### Selecting with the mouse in Power mode

- Left-clicking a single file will invert the selection state of that file, but will not disturb the selection state of any other items.
- You can select a range of files by simply clicking and dragging up or down (i.e. keep the mouse button down and move the mouse cursor up or down). If the file you click on first is already selected, dragging up or down will deselect all files dragged over.
- Clicking an empty part of the file display does not, by default, deselect any files. You can drag a selection rectangle by clicking on an empty part of the file display and dragging with the button held down - the selection rectangle will invert the selection state of any items you drag over.
- Note that because dragging up or down is used to select files, a drag and drop operation can only be initiated by dragging left or right.

##### Selecting with the keyboard in Power mode

- Power mode is primarily a mouse-based interface, and by default Power mode file displays are not in "keyboard mode" - so pressing the cursor keys will simply scroll the list (if it can scroll) and will not select any files.
- Pressing the <kbd>Ctrl</kbd> key toggles the file display in and out of keyboard mode. When in keyboard mode, a focus indicator is shown and the cursor keys will move the focus indicator from one file to the next (although they will not, by themselves, cause any files to be selected).
- Pressing <kbd>Space</kbd> when in keyboard mode will invert the selection state of the file that currently displays the focus indicator.
- When in keyboard mode you can select a range of files by holding the <kbd>Shift</kbd> key and using the cursor keys to move the focus indicator. The state of the first file when <kbd>Shift</kbd> was pushed determines the selection state applied - if the first file was not already selected, all files in the range will be selected, and vice versa.
- When range-selecting with <kbd>Shift</kbd>, reversing direction will undo the selection you just applied. For example, if you press <kbd>Shift+Down</kbd> four times to select the first four files, and then (while still holding <kbd>Shift</kbd>), press <kbd>Up</kbd> twice, the last two selected files will be deselected.
- <kbd>Ctrl+A</kbd> and <kbd>Ctrl+I</kbd> work the same as with the other view modes (see above), as does the [find-as-you-type](../the_lister/find-as-you-type_field.md) field.

##### Power mode selection is persistent

The default behaviour of power mode is for file selections to be persistent (that is, files do not deselect by themselves - you have to deselect them manually). In other file display modes you can simply click on an empty area to deselect all files, but in power mode:

- You can either press <kbd>Ctrl+A</kbd> followed by <kbd>Ctrl+I</kbd> (select all, followed by invert selection) to deselect all files, or
- Use **[Customize mode](/Manual/customize/RAEDME.md)** to add the `Select NONE` command to your toolbars (e.g. in the **Edit** menu). This is not included in the default toolbar set, but you may want to add it manually and assign a hotkey to it if you are going to be using power mode.

More:  
[Single-click mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/single-click_mode.md)  
[Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md)  
