# Options

This page contains general folder tree-related items.

### Single/dual tree

- **Open second Folder Tree in dual display mode**: If you set a Lister to dual-display mode, a second tree for the second file display will be automatically displayed. If this option is turned off you can open the second tree manually if desired (from the default *Lister* menu).
- **Share single tree between dual file displays**: If you have dual file displays but only one tree, the single tree will be shared by both file displays. Whichever file display is source has "ownership" of the tree, and the tree will reflect the current folder shown in that file display only. When you switch source and destination displays the tree will automatically update to reflect the new location (if any). If this option is turned off, and you have dual displays with only one tree, then the tree is owned by the left/top file display only, and the right display doesn't have one.

### Horizontal scrolling

Controls how and when the tree scrolls horizontally. The following choices are available:

- **Manual scrolling with automatic adjustment on folder changes**: The tree has a horizontal scroll bar (when needed) which lets you scroll manually. When you change folders, the tree will automatically scroll left or right if the new folder is out of view.
- **Manual scrolling only**: The horizontal scroll bar remains (when needed), and you can still scroll left and right manually, but the tree will never scroll left or right by itself.
- **No horizontal scrolling at all**: The tree never scrolls left or right at all, and no horizontal scroll bar is shown. If items are out of view to the right of the tree, you will need to resize it to see them.

Additional options:

- **Prevent horizontal scrolling during drag and drop**: This option prevents the tree from scrolling left or right during a drag and drop operation. It doesn't affect how horizontal scrolling works normally.

### Vertical scrolling

- **Position selected item**: The tree will automatically scroll vertically to keep the selected item as close to the specified position as possible. The scrolling only happens when the tree selection is changed automatically (to follow your navigation), so if you're navigating using the tree itself this option has no effect.
