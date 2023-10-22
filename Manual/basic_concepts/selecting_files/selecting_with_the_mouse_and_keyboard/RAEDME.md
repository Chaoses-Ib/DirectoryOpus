# Selecting with the mouse and keyboard

Selecting files with the mouse or keyboard, in all [view modes](../the_lister/view_modes.md) except Power mode, works similarly to Explorer:

Using the mouse,

- Left-clicking a single file will select that file and deselect all others.
- **Control** + left-clicking a single file will toggle the selection state of that file, leaving all others unchanged (i.e. **Control**+click to select, repeat to deselect).
- **Shift** + left-clicking lets you select a range of files. Click normally to select the first file in the range, then hold the **Shift** key and click again on the last file in the range. All files between and including those two will be selected.
- You can combine **Control** and **Shift** to add a range to already selected files - without the **Control** key held down, the first click in a range selection normally deselects all but the file you clicked on.
- Clicking on an empty part of the file display (i.e. not on a file) will deselect all files.
- Click on an empty part of the file display and (with the button still down) move to mouse to drag out a selection rectangle. All files you drag that rectangle over will be selected.
- If you hold the **Control** key down when you click to drag the selection rectangle, existing selections will be left unchanged. Additionally, files that you drag over will have their selection states inverted.
- You can middle-click on a file to toggle its selection state (equivalent to **Control** + left-clicking). You can also use the middle button to drag a selection rectangle that inverts the selections of files you drag over (equivalent to **Control** + left-drag). Note that some mouse drivers map the middle mouse button to another function by default - if you find middle-click isn't working as expected, see the [FAQ](https://resource.dopus.com/t/how-to-make-logitech-mid-back-forward-buttons-work-in-opus/2972) for some hints on how to fix it. You can also configure Opus to treat a single middle-click as a double middle-click, which lets you obtain behavior similar to a web browser (e.g. single middle-click to open a folder in a new tab). See the **[File Displays / Mouse](/Manual/preferences/preferences_categories/file_displays/mouse/RAEDME.md)** Preferences page for details on that.
- You can also use the right button to drag a selection rectangle; once the button is released, the context menu will be shown for all selected items.

Using the keyboard,

- **Ctrl+A** is the default hotkey to select all items in the list (the same as selecting the **Select All** command from the **Edit** menu).
- **Ctrl+I** will invert the selection state of all items in the list (the same as the **Edit / Invert Selection** command).
- The cursor keys (up/down/left/right, plus Page Up/Down and Home/End) can be used to move the selection (and deselect all other items) in the file display when it has input focus - click on it or use the **Tab** key if it doesn't already have this.
- You can combine **Shift** with the cursor keys to perform range selection using the keyboard - move the selection to the first file in the range, and then hold **Shift** and use the cursor keys to expand the range to the last item.
- Holding the **Control** key lets you move the focus rectangle without changing the selection. You can use this to select multiple, non-contiguous files. For example, use the cursor keys to place the selection on a given file. Then hold the **Control** key down and use the cursor keys to move the focus rectangle to another file - note that the first file is not deselected.
- Pressing the **Space** bar when an item has input focus will select it. You can toggle the selection on the currently focused item by pressing **Control+Space**.
- Pressing the **Insert** key toggles the selection of the current item, and automatically moves the input focus to the next item in the list.
- Typing a partial filename will activate the [find-as-you-type](../the_lister/find-as-you-type_field.md) field and place the selection on the first file matching the entered string.

In power mode, mouse and keyboard selection works slightly differently by default (although the behaviour of the mouse can be modified quite a lot from the **[File Display Modes / Power Mode](/Manual/preferences/preferences_categories/file_display_modes/power_mode/RAEDME.md)** Preferences page).

Using the mouse,

- Left-clicking a single file will invert the selection state of that file, but will not disturb the selection state of any other items.
- You can select a range of files by simply clicking and dragging up or down (i.e. keep the mouse button down and move the mouse cursor up or down). If the file you click on first is already selected, dragging up or down will deselect all files dragged over.
- Clicking an empty part of the file display does not, by default, deselect any files. You can drag a selection rectangle by clicking on an empty part of the file display and dragging with the button held down - the selection rectangle will invert the selection state of any items you drag over.
- Note that because dragging up or down is used to select files, a drag and drop operation can only be initiated by dragging left or right.

Using the keyboard,

- Power mode is primarily a mouse-based interface, and by default Power mode file displays are not in "keyboard mode" - so pressing the cursor keys will simply scroll the list (if it can scroll) and will not select any files.
- Pressing the **Control** key toggles the file display in and out of keyboard mode. When in keyboard mode, a focus indicator is shown and the cursor keys will move the focus indicator from one file to the next (although they will not, by themselves, cause any files to be selected).
- Pressing the **Space** bar when in keyboard mode will invert the selection state of the file that currently displays the focus indicator.
- When in keyboard mode you can select a range of files by holding the **Shift** key and using the cursor keys to move the focus indicator. The state of the first file when the **Shift** key was pushed determines the selection state applied - if the first file was not already selected, all files in the range will be selected, and vice versa.
- When range-selecting with the **Shift** key, reversing direction will undo the selection you just applied. For example, if you press **Shift+Cursor Down** four times to select the first four files, and then (while still holding **Shift**), press **Cursor Up** twice, the last two selected files will be deselected.
- **Ctrl+A** and **Ctrl+I** work the same as with the other view modes (see above), as does the [find-as-you-type](../the_lister/find-as-you-type_field.md) field.

The default behaviour of power mode is for file selections to be persistent (that is, files do not deselect by themselves - you have to deselect them manually). In other file display modes you can simply click on an empty area to deselect all files, but in power mode:

- You can either press **Ctrl+A** followed by **Ctrl+I** (select all, followed by invert selection) to deselect all files, or
- Use the **[Customize](/Manual/customize/RAEDME.md)** dialog to add the **[Select None](/Manual/customize/the_customize_dialog/commands/edit_category_pre-defined_commands.md)** command to your toolbars (e.g. in the **Edit** menu). This is not included in the default toolbar set, but you may want to add it manually and assign a hotkey to it if you are going to be using power mode.

More:

[Single-click mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/single-click_mode.md)  
[Checkbox Mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md)  
