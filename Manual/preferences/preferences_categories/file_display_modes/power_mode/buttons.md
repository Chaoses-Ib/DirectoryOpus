# Buttons

This page lets you control exactly what all three mouse buttons do in a *Power* mode file display. You can select actions for what happens when you click on a file, and also what happens when you drag and drop files with each of the three buttons.

##### Button click actions

For each of the three buttons, the options for clicking are:

- **Auto-deselect**: Similar to the left mouse button in *Details* mode. Clicking a file selects that file and deselects all others. Clicking an empty part of the display deselects everything. Range selection is supported via dragging (unlike *Details* mode, you can drag up and down the filenames, not just via a marquee), or by clicking one file and then, while holding <kbd>Shift</kbd>, clicking another. Holding <kbd>Ctrl</kbd> and clicking will toggle the selection of individual items.
- **Context Menu**: Selects the file under the mouse, and displays its context menu.
- **Context Menu (auto-deselect)**: Similar to the right mouse button in *Details* mode. Clicking a file which is already selected will show a context menu for that file and any other selected files. Clicking a file which is not already selected will deselect all other files, select the clicked file, and show a context menu for it. Clicking an empty space in the file display will deselect all files and show the context menu for the folder background. Range selection is supported via the <kbd>Shift</kbd> key.
- **Context Menu (no select)**: Displays the context menu for any currently selected items, but does not select the one under the mouse.
- **Context Menu (select)**: Lets you drag-select one or more files, and then displays the context menu for them.
- **Deselect only**: Deselects the file under the mouse and any you drag-select.
- **Disabled**: The mouse button will do nothing.
- **Drag select**: Inverts the selection state of the item under the mouse, and then applies the same state to any items you drag-select over.
- **Full toggle**: Clicking an item, or drag-selecting over items, will invert their selection state. (Somewhat similar to the middle mouse button in *Details* mode.)
- **Inline Rename**: Immediately enters inline rename for the item under the mouse.
- **Partial toggle**: Clicking an unselected item and then drag-selecting will select all the items; clicking an already selected item and then drag-selecting will deselect all the items.
- **Select only**: Selects the file under the mouse and any you drag-select.
- **Set focus (no select)**: Gives focus to the file under the mouse but does not select it.

Some button modes that don't show a context menu explicitly also support showing one if the button is held down for a certain amount of time; the **Context menu after...** option lets you configure this time in milliseconds.  

##### Drag and drop options

The options for drag and drop are:

- **Disabled**: Drag and drop can not be initiated with this mouse button.
- **Immediate action**: Dragging an item and releasing it will immediately perform the default drop action.
- **Show menu**: Dragging an item and releasing it will display the drag and drop action menu.

##### Range selection

The **Range selection in *select* and *toggle* modes** option lets you enable additional keyboard support for range selection with certain mouse button choices. Normally, you select a range of files in *Power* mode by clicking and dragging with the mouse. The options here mean you can also select multiple files by clicking the first file and holding <kbd>Shift</kbd>, <kbd>Ctrl</kbd> or <kbd>Alt</kbd> while clicking a second file to select everything between the two.

The range selection options affect buttons set to *Drag select*, *Partial toggle*, *Full toggle*, and *Select only*. Buttons set to *Auto-deselect* and *Context Menu (auto-deselect)* always support (only) the <kbd>Shift</kbd> key for range selection and <kbd>Ctrl</kbd> for toggling individual items (to remain more similar to *Details* mode).
