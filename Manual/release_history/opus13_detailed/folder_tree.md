### Directory Opus 13 - Detailed release notes

# Folder Tree

- Contents:
  - (Configured via Preferences / Folder Tree / Contents.)
  - Root items in the folder tree can be rearranged or turned off.
  - Individual folders under the Profile directory can be shown or hidden.
  - Windows 11: Opus now filters out the plethora of random folders Microsoft added under Desktop. A new option lets you add them back.
  - Option to hide non-drives under This PC. (Will only show drive letters and MTP devices, no "media" devices.)
  - Option to show only labels for drives.
  - Option to show full paths for Smart Favorites.
  - The user profile folder (normally your user name) is now displayed as "Profile" by default. It can be changed back if you wish.
  - Support for Linux virtual folder \\wsl\$\\ when present on supported Windows versions. Can be hidden if not wanted.
  - New option, "Remove dynamically added folders". When on, root folders that were added dynamically (to show a branch that is normally hidden) are removed again when you navigate away. When off, they stay until the window closes.
  - Changes to the Quick Access folder are now reflected sooner in the folder tree (and on toolbars, if the folder has been added to them).
  - The Favorites branch now supports separators in the tree.
  - Removed the "Start Desktop at..." dropdown. This confused people, and most of what it did can now be achieved in other ways. For example, This PC can be moved to a separate group, which is similar to the "start at Computer" option, and "non-drive folders" can be turned off, which is similar to the "start at Drives" option.
- Network servers:
  - The Network branch now updates automatically when machines come and go (as long as Windows itself notices).
  - The list of computers under Network in the folder tree is now cached for faster access, including across restarts.
  - Caching can be configured under Preferences / Folders / Network Folders.
  - You can also specify one or more servers which should always be listed, even if Windows fails to find them.
- Cloud storage:
  - Option to put Cloud Storage folders in their own part of the tree, or hide them entirely.
  - Synology shares are now shown properly in the tree (and on the Desktop) as links directly to the share folder, rather than the intermediate folder containing shortcuts.
- Expansion and pinned branches:
  - (Configured via Preferences / Folder Tree / Expand/Collapse.)
  - Tree header has new "collapse all" button. Collapses all folders except those leading to the current path.
  - Tree header has new button to manage expansion presets:
    - Save a list of which folders are expanded and collapsed into a named preset.
    - Load a preset to expand and collapses folders to match what was saved.
    - Use multiple presets for different situations.
  - New option, "Expansion pins on folder tree branches":
    - Pinned branches remain expanded and cannot be collapsed. They remain expanded when you click the "collapse all" button.
    - Expansion pins, if enabled, display on mouseover, on the right of each branch.
    - Click pin once to pin a folder and again to un-pin it.
    - Ctrl+Space toggles the selected branch's pin, if the tree has keyboard focus.
  - New option to remember the expansion state of *all* tree items (not just the root items as in Opus 12).
  - New option to remember the expansion state of root items. (Opus 12 always did this; now it's optional.)
  - New option to only remember expansion state of pinned items.
  - Tree branches now animate briefly when expanded by mouse or keyboard. New option, "Animate expanding branches" to turn it off.
  - The old "Expand My Computer branch" option has been removed, since the state of all folders is remembered automatically.
- Miscellaneous:
  - Tree item height, indentation and spacing are now configurable.
  - New option to prevent scrolling when branches expand. (Stops the tree jumping down to show as much of the expanded branch as possible.)
  - "Position selected item" setting has a new "25% from the top of the tree" option, in addition to the older "top" and "middle" choices.
  - New option show or hide the tree header's lock button. (Off by default. People tended to click it without understanding what it did.)
  - You can now create hotkeys which only apply when the folder tree has focus.
- Commands:
  - `Go TREEEXPAND=...` and `Go TREECOLLAPSE=...` -- Expand or collapse multiple tree branches in various ways. Parameters include:
    - "focus": Expand/collapse the tree item with input focus.
    - "all": Expand/collapse the current branch and everything within it.
    - "first": Expand/collapse the current branch only.
    - "second": Expand/collapse current branch on first use, then expand/collapse all its children on second use.
    - (The old `Go EXPANDTREE` is hidden, but still works. `Go TREEXPAND` with no additional parameters does the same thing.)
  - `Go REMEMBERTREEEXPANSION` and `Go RESTORETREEEXPANSION` -- Save and load which tree items are expanded and collapsed.
    - NAME argument can specify preset to load or save.
    - If no preset is specified, expansin state is stored in memory temporarily until the window closes.
  - `Go RESTORETREEEXPANSION=list` -- Displays a list of saved presets which you can load. (You'd normally access this via the tree header, but that can be hidden.)
  - `Go RESTORETREEEXPANSION=reset` -- Reset tree expansion to its initial state.
  - `Go TREESETPINSTATE` -- Toggles the selected item's pin.

------------------------------------------------------------------------

Next: [File Display](/Manual/release_history/opus13_detailed/file_display.md)
