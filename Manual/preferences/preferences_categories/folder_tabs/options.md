# Options

This page contains general options relating to [folder tabs](/Manual/basic_concepts/the_lister/tabs/README.md).

- **Display drive letter in tab label**: The drive letter will be displayed in the tab along with the name of the folder.
- **Display folder icons**: The folder's icon will be shown in the tab.
- **Drag over tabs brings them to the front**: Lets you adjust the time you have to hover over a tab while dragging a file before the tab comes to the front. If you turn this option off then dragging over tabs won't bring them to the front at all.
- **Process file changes in background tabs**: When this option is turned on, tabs that aren't visible still process any file changes that occur in the folder they're displaying. If you turn it off, changes won't be processed for non-visible tabs - instead, the tab will be marked as dirty and automatically reloaded when you switch back to it. Turning off background change processing can enhance performance when you're working with lots of tabs simultaneously.
- **Treat tab label as folder when dragged or right-clicked**: Normally you can drag tabs around, or access their context menu, by clicking anywhere on the tab. If this option is turned on, the tab is split into two parts for the purpose of mouse clicks. The icon acts as the hotspot for the tab, and the label acts as the hotspot for the folder displayed on the tab. So with this option on, you need to click and drag the icon if you want to drag the tab, or right-click the icon if you want to access the tab's context menu. Right-clicking the label will display the context menu for the folder, not the tab, and dragging from the label will represent a drag of the actual folder, which lets you copy the folder or create a shortcut to it using drag and drop.
- **Truncate long labels with "..." instead of fading out**: If a tab label has to be truncated to fit, the label will end with an ellipsis rather than the tab itself fading out.

### When currently selected tab is clicked

Controls what happens when you click the already selected tab.

- **Rename tab**: The tab will go into inline rename mode, letting you assign a custom label to it.
- **Go to previous**: Clicking the already selected tab will activate the previously selected tab.
- **Do nothing**: Clicking the tab does nothing.

### Closing tabs

Besides the below options, you can close tabs by clicking them with the middle mouse button (if you have one) or by right-clicking them and choosing **Close Tab** from the context menu.

- **Close tab on device ejection**:
- **Double-click tabs to close them**: Double-clicking a tab with the left button will close it.
- **Folder tab close buttons**: Each tab will have a close button (whenever there is more than one tab open).
  - **Small close buttons**: Makes the close buttons smaller to save space.
- **Lister close button closes active tab**: If multiple tabs are open, clicking the Lister close button (the main close button for the whole window) will close only the active tab instead of the whole Lister.
- **Lister closes when last tab closes**: Listers will close when the last tab within them is closed (similar to how web browsers work).
