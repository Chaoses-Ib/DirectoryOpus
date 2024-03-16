# Expand / Collapse

This page contains options relating to expanding and collapsing of branches in the folder tree.

##### Folder content population

The **Automatically expand to current folder** option controls how the tree expands folders as you navigate in the file display.

If this option is turned on, the tree will expand to track your location as you navigate in the file display. If turned off the tree won't automatically track your location - you can still navigate with the tree by expanding and selecting folders yourself, but it won't follow you when you navigate by other methods.

Note that this option only applies when branches in the tree have *never* been expanded before (it's designed to allow control over when the tree tries to read the contents of a sub-folder). If a branch has already been expanded manually, the tree already knows its contents, and so this option won't apply. To stop the tree from ever automatically expanding a folder, enable the lock button from the [Folder Tree / Appearance](appearance.md) page and then turn on the lock whenever you want to preserve the tree's current state.

You can choose how the folders are populated when they expand automatically to show you your current location:

- **Fully populate contents**: All automatically expanded folders are fully populated - the tree will show the full contents of all folders leading up to your current location.
- **Populate contents for local devices only**: Only folders on local devices (hard drives, USB drives, etc) will be full populated. Folders on network drives or FTP sites will only display the member folder that forms part of your current location.
- **Don't populate contents**: No automatically expanded folders will be fully populated - you will need to manually populate them by clicking their expansion button to reveal their full contents.

The tree will always show you your current folder (and the path leading to it) so the population options only affect the display of other items in the expanded folders. When you expand an item manually, its contents are always fully populated - so if the tree has partially expanded an item, you can click on its expansion button to fully expand it and reveal the rest of its contents. These options can dramatically improve performance when navigating folders on slow devices like networks - rather than having to read the full contents of all folders leading up to your current location (which can be very slow over a network), the tree will simply display the folders leading to your current path (and since it already knows what those folders are, it doesn't have to read any information from the network to do this).\</WRAP\>

##### Other options

- **Animate expanding branches**: When a branch expands the contents slide out instead of appearing instantly.
- **Collapse non-selected branches**: The tree will automatically collapse any expanded branches that aren't needed to show you your current location. This can help keep the tree compact and easier to navigate as you move around the file system.
  - **Unless open in other tabs**: Branches won't be collapsed if they contain a folder that is currently displayed in another folder tab.
- **Expand selected branch**: The tree will automatically expand the branch that represents your current location. Normally only folders leading up to your current location are expanded - with this option on, the current location's branch will also be expanded.
  - **Expand selected branch when changing tabs**: The tree will automatically expand the branch for the current tab when you change which tab is active. Without this option, branches are only expanded when you actually navigate to a new folder in a tab.
- **Expand/collapse all child branches when parent double-clicked**: When you double-click a folder's expand/collapse icon, the first level of its child folders will also be expanded or collapsed.
- **Prevent scrolling when branches expand**: Stops the tree jumping down to show as much of the expanded branch as possible when a branch expands.
- **Remember expanded root items in layouts**: In [Lister layouts](/Manual/basic_concepts/the_lister/layouts/RAEDME.md), including the [the default Lister](/Manual/basic_concepts/the_lister/the_default_lister.md), the expansion state of root items will be remembered.
  - **Remember all expanded items**: All expanded folder states will be remembered, not just root items.
  - **Only remember if pinned**: Only pinned folders will be remembered - other folders won't have their expansion state preserved.
- **Remember expanded items for tabs**: The expansion state of folders in the Folder Tree will be preserved between tabs. That is, when you switch away from a tab, Opus remembers which folders in the folder tree were expanded and which were collapsed, and restores this state when you switch back to that tab.

##### Drag-and-drop

- **Expand branches when dragging over the tree**: When you drag files over the tree, the tree will automatically expand any collapsed folders that you hover over with the mouse. This lets you drag and drop files to sub-folders that aren't necessarily visible when the drag and drop begins.
- **Collapse after drag (spring-loaded)**: Folders that automatically expand during drag-and-drop will collapse again when the drag is complete.
- **Expansion delay**: Configure how long (in milliseconds) you have to hover the mouse over a folder during drag-and-drop before it expands.
