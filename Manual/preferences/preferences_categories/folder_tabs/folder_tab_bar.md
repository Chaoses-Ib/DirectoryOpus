# Folder Tab Bar

This page contains various options that control the appearance and behavior of the tab bar where [Folder Tabs](/Manual/basic_concepts/the_lister/tabs/RAEDME.md) appear.

##### Opening new tabs

From the tab bar itself there are two ways to open new tabs:

- **Display new tab button**: Adds a small `+` button at the end of the folder tabs, which you can click to quickly open a new tab.
- **Double-click to open a new tab**: If this option is on, double-clicking an empty spot on the tab bar will open a new tab.

For both of these, the initial folder can be configured from the drop-down:

      * **Current folder**: Duplicates the current tab's folder. 
      * **Default folder**: Opens the "default folder", which is actually the folder that the [[:basic_concepts:the_lister:the_default_lister|Default Lister]] opens. To change it you need to change the Default Lister. 
      * **Home folder**: Opens the [[..:frequently_used_paths:home_folder|home folder]].
      * **Empty tab**: Doesn't automatically read a folder, leaving the new tab empty. 
      * **Location**: Opens a specific folder.

You can also control where the new tab is positioned:

- **Open new tabs next to the active tab**: Normally new tabs open at the end of currently existing tabs - with this option turned on, new tabs will open immediately to the right of the currently selected tab.

  

##### Use popup menu

When the tab bar is horizontal, there are two options for how tabs are handled when the available space is not enough to show them all at once (when tabs are displayed vertically, a scrollbar will appear that lets you scroll up and down the tabs if they don't all fit.)

- ![](/Manual/images/media/13/tab_scroll.png) Scroll arrows at the end of the tab bar, or
- ![](/Manual/images/media/13/tab_overflow.png) A button to trigger the popup overflow menu

The options that control this are:

- **Use popup menu when tabs exceed available space**: Enables the popup overflow menu instead of the scroll arrows.
  - **Show all tabs in menu**: The popup menu will include all currently open tabs, not just the ones that don't fit.
  - **Show menu when tabs are reduced**: Shows the tab menu when tab size is reduced to fit the available space (even if they don't actually overflow). This can be handy to see the full names of tabs when they're truncated in the tab bar.

  

##### Other settings

- **Display folder tab bar**: Controls when the tab bar is displayed. You can't have zero tabs - there's always at least one tab open, but you can choose whether or not to display the tab bar when there is only one tab.
  - **Always**: Folder tabs will always be displayed, even if there's only one tab open.
  - **When needed**: Tabs will only be displayed when needed, that is, when there is more than one tab open. If you have multiple tabs open, the tab bar will be hidden when the second-last tab is closed.
  - **When needed (balanced)**: If the Lister is in dual-display mode, and one side of it has more than one tab open, tabs will be displayed on the other side as well. This is more for aesthetic reasons than functional; it can look strange to have tabs visible on one side but not the other.

- **Tab bar position**: Controls where the tabs appear in relation to the file display they're attached to. Note that this can be overridden on a per-Lister basis using the `Set TABPOSITION` command.
  - **Below**: Folder tabs will be displayed horizontally, below the file display.
  - **Above**: Folder tabs will be above the file display.
  - **Left**: Folder tabs will be displayed vertically, to the left of the file display.
  - **Right**: Folder tabs will be to the right of the file display.

- **Dual display position**: Controls where the tabs appear when the Lister is in [dual-display mode](/Manual/basic_concepts/the_lister/dual_display/RAEDME.md). Note that this can be overridden on a per-Lister basis using the `Set TABPOSITION` command.
  - **Normal**: Both tab bars appear in the same relative position (as set by the **Tab position** option).
  - **Together**: The tab bars appear together. For example, the top file display's tabs would be below the file display, and the bottom file display's tabs would be above the file display - resulting in the two tab bars being next to each other.
  - **Apart**: The tab bars appear apart. For example, the left file display's tabs would be to the left of the file display, and the right file display's tabs would be to the right.
