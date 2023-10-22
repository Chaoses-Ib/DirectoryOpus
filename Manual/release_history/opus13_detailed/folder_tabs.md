##### Directory Opus 13 - Detailed release notes

# Folder Tabs

- Tab context menu:
  - The folder tab context menu is now configurable via Customize \> Context Menus \> Folder Tab Context. Add or remove items as you wish.
  - Functions from the old, fixed menu have been converted to commands which will show or hide themselves, and in some cases change labels, dynamically to mimic the old menu.
  - Options in the menu to change where the tab bar appears without going into Preferences.
- Locked tabs:
  - (Configured via Preferences / Folder Tabs / Locking.)
  - New option to prevent closing locked tabs.
  - New option to hide folder icons from tabs.
  - New option to hide padlock icons from locked tabs.
  - New option to change the edge color of locked tabs. If a tab already has an edge color, the locked color is shown as well (either as a checkerboard pattern or a dot of color, depending on tab layout).
  - New option lets you choose whether a locked tab resets to its original folder as soon as you switch to another tab, or only if you switch back and then, with the locked tab already active, click it a second time.
  - Within a locked tab, if you double-click a folder which is already open in the same tab bar, Opus now switches to the existing tab instead of opening a new one. (A new option exists to restore the old behavior.)
- Tab switcher:
  - New popup tab switcher, similar in function to the Windows `Alt+Tab` switcher, or `Ctrl+Tab` in Visual Studio.
  - Preferences / File Displays / Options / Tab Key: Configure how the tab key behaves in Listers, including the new switcher.
  - By default, `Ctrl+Tab` displays the switcher.
  - The default for Tab (without `Ctrl`) is now to switch sides in dual-display windows.
  - Tabs now remember the order they were last activated. The default selection in the switcher is the previously selected tab. This lets you switch between two tabs by repeatedly pressing and releasing `Ctrl+Tab` (similar to how Alt+Tab works in Windows).
  - The switcher stays open as long as one of the qualifier keys (e.g. `Ctrl`) that triggered it is held.
  - Can be cancelled by pressing `Esc` or clicking outside it.
  - Within the switcher, tab or cursor keys move the selection. When the qualifier is released, or return is pressed, the highlighted tab will be activated and set as the source.
  - Space activates the selected tab without closing the switcher.
- Tab Groups:
  - The Folder Tab Group editor now has a drop-down on the "Edit Format" button which lets you copy the format from one tab to all other tabs in the group.
  - New option within Tab Groups, "Make format the default for this tab". When set, the format specified will "stick" to the tab through folder changes (rather than it resetting to the default format), unless a saved format takes precedence.
  - When saving over a Folder Tab Group, if the existing group had tabs on both sides but you selected "Save" instead of "Save Both Sides", you will be asked if you want to save just one side or both.
- Miscellaneous:
  - Preferences / Folder Tabs / Edge Colors is the new place to define tab accent colors for specific folders or folder types. (Used to be done through Folder Formats. Now separate to simplify configuration of unrelated concepts.)
  - You can now scroll the tab bar with the mouse wheel when there are too many tabs to fit on screen. (Previously, this only worked if the tabs were on the left or right. It now also works for the top and bottom.)
  - When labels are too wide, tabs now let you choose between fading them out and truncating them with "...".
  - A linked tab now shows a colored link icon on the right instead of replacing its main folder icon. (Linking two tabs means activating a tab on one side will automatically activate the linked tab on the other side.)
  - New option to automatically close tabs for removable drives when they are unplugged:
    - If turned off (the default), the file display will navigate to This PC instead.
    - If turned on, and "Lister closes when last tab closes" is also on, the entire window may close if there are no other tabs.
    - A locked tab which cannot close will go to the folder it is locked to instead of This PC.
  - Search results are no longer loaded by default if they are a tab's initial folder. This can be changed via Preferences / Folders / Automatic Reading.
  - Lister window title can now be configured to show the name of the last loaded Folder Tab Group (if any).
- Commands:
  - Variables tell commands in the tab menu which tab was right-clicked:
    - \`%tab_path%\` -- Tab's path.
    - \`%tab_id%\` -- Tab's index.
    - \`%tab_hwnd%\` -- Tab's window handle (decimal).
  - \`Go TABLOCK=menu\` -- Generates the tab lock menu dynamically.
  - \`Go TABLINK=menu\` -- Generates the tab link menu dynamically.
  - \`Go TABNAME=!edit\` -- Starts renaming a tab (combine with PATH to specify another tab's index).
  - \`Go TABCOLOR=edit\` -- Edits a tab's edge/accent color (combine with PATH to specify another tab's index).
  - \`Set TABPOSITION\` -- Can be given "save" parameter to change the global configuration, instead of only temporarily moving the current window's tab bar.
  - Commands can be disabled or hidden depending on the number of tabs and the selected tab index. (See [Miscellaneous Commands](misc_commands.md).)
  - \`Go TABSWITCHER\` -- Makes the new switcher appear. Can be bound to a mouse button or alternative hotkey.
- Evaluator:
  - Several variables are passed to Evaluator code in the folder tab context menu.
  - \`count\` -- Total number of tabs on the same side.
  - \`countdual\` -- Number of tabs on the other side.
  - \`dual\` -- True if the tab is part of a dual file display.
  - \`path\` -- The tab's path, if any.
  - \`right\` -- True if the tab is on the right (or bottom) of a dual file display, rather than the left (or top).
  - \`sel\` - The selected tab's index, or -1 if the tab bar background was right-clicked.

------------------------------------------------------------------------

Next: [Location Bar](/Manual/release_history/opus13_detailed/location_bar.md)
