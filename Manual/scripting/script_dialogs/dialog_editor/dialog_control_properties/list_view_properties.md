# List View Properties

The specific properties applicable to the *List View* control are:

- **Content**: Lets you specify the initial contents of the list view control. Each value you enter (one per line) will appear in the list view. You can also manipulate the contents of the list view from your script.
- **Sort**: Set to **True** to have the contents of the list view control automatically sorted alphabetically.
- **Selection**: Controls the selection type of the list view. Options are:
  - **Single**: The user can select at most one item from the list.
  - **Multiple**: The user can select more than one item by holding the **Control** and/or **Shift** keys when clicking on the list, or by dragging a marquee around the items with the mouse.
  - **None**: Does not allow items to be selected; the list will be for display only.
- **Columns**: Lets you add columns to the list view when it's in *Details* mode. Each value you enter (one per line) will appear as a new column in the list view.
- **View Mode**: Controls the initial display mode of the list view. The view mode can be changed later on in your script. Options are:
  - **Large Icons**: Large (32x32 nominal) icons with labels underneath.
  - **Small Icons**: Small (16x16 nominal) icons with labels to the right.
  - **List**: Similar to *Small Icons* but with a horizontal layout.
  - **Details**: Multiple columns, one item per row. 
- **Edit Labels**: Set to **True** to allow the item labels (column 0) to be edited.
- **Full-row Select**: Set to **True** if you want the full width of a row in *Details* mode to be used for selection.
- **No Header**: Set to **True** to hide the column headers in *Details* mode.
- **No Sort Header**: Set to **True** to disable the ability to resort the list by clicking the column headers in *Details* mode.
- **Small Icons**: Set to **True** to enable icons in the "small" modes (*Small Icons*, *List*, *Details*). Icons can not be disabled in *Large Icon* mode.
- **Drag Source**: When set to **True** the control will send a **drag** event when the user clicks on an item and drags with the mouse (to e.g. begin a drag and drop action).
- **Checkboxes**: Set to **Automatic** or **Manual** to enable checkboxes for each list item. In **Automatic** mode, the checkbox state is changed automatically when user clicks the checkbox. In **Manual** mode, you're notified of the click (via a **checked** event) but must change the state yourself using the **DialogListItem.checked** property.
