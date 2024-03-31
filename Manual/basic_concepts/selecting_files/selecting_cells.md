# Selecting Cells

As well as selecting files to perform operations on them, in *details* and *power* mode you can select individual cells (or whole columns) and copy their contents to the clipboard.

### Selecting cells

Cell selection is performed using the right mouse button with the <kbd>Ctrl</kbd> key held down:

- To select a single cell, hold <kbd>Ctrl</kbd> and right click the cell
- To select a whole column, hold <kbd>Ctrl</kbd> and right click the column header
- To select a group of cells, hold <kbd>Ctrl</kbd> and then click and drag with the right button to draw a lasso around the cells you want to select

Selected cells are highlighted in yellow by default. You can configure this color from the [Directory Opus Colors](/Manual/preferences/preferences_categories/colors_and_fonts/directory_opus_colors.md) Preferences page.

### Copying cell data

Once you have one or more cells selected, right click one of the selected cells **without** the <kbd>Ctrl</kbd> key held down. This displays the **Copy Highlighted Cells** context menu.

![](/Manual/images/media/13/cell_highlights.png)

The commands on the context menu can be used to copy the highlighted data to the clipboard in various ways.

### Deselecting cells

- To deselect a selected cell, hold <kbd>Ctrl</kbd> and right click it again (the selection operation is a toggle).
- To clear all selections, push <kbd>Esc</kbd>, or click the left button anywhere in the file display.

### Configuring the context menu

The context menu is configurable from the [Customize / Context Menus](/Manual/customize/the_customize_dialog/context_menus.md) tab. The standard context menu uses the `Clipboard COPYCOLUMNS` command to implement the various "copy to clipboard" functions, and the `Select HIGHLIGHTCLEAR` command to implement the "clear highlighted cells" command.

A script can use the **[Item](/Manual/reference/scripting_reference/scripting_objects/item.md).highlighted** property to query any currently highlighted cells.
