##### Directory Opus 13 - Detailed release notes

# Duplicate Files Finder

- Similar to Find panel (see above for detail):
  - Improved UI.
  - Reset menu.
  - Presets.
  - Exclude folders by path, wildcard or hidden/system attributes.
  - Show Results in left/right tab.
  - Indexed search as a pre-filter.
  - "Suppress UAC prompts" option.
  - "Duplicate Files" now has its own folder format, distinct from the more general "Collection" format.
- Duplicate selection UI:
  - New user interface for selecting which files should be deleted and which should be kept.
  - After searching for duplicates, click the Select button to open the new UI.
  - Folders containing duplicates are listed in a tree, allowing you to select or deselect different branches, among other options.
  - Shift-click to change multiple checkboxes at once, or use the various tools above the tree.
  - "Preferred locations" list for selecting duplicates by location. Can be saved for reuse.
- Miscellaneous:
  - Removed separate "Delete mode" and Delete button. No longer needed.
  - New option, "Ignore hard links".
  - New option, "Ignore offline files".
  - New option, "Minimum size".
  - When matching by checksum, an initial checksum is calculated of just the start of potential matches. The full checksum is only calculated if the partial checksums match.
  - Panel supports auto-shrink (previously only Find and Synchronize did).
  - Commands:
    - \<ib:inline-code\>`Find DUPES`\</ib:inline-code\> supports MINSIZE, OFFLINE, IGNORELINKS, NOAUTORUN, PRESET, SHOWRESULTS, QUERY, QUERYENGINE args.
    - \<ib:inline-code\>`Find DUPES`\</ib:inline-code\> now defaults to \<ib:inline-code\>`RECURSE CLEAR UAC=no`\</ib:inline-code\>.
    - \<ib:inline-code\>`Find DUPES RUNINPANEL`\</ib:inline-code\> lets a single command configure the panel and then start the operation.
    - \<ib:inline-code\>`Set Utility=Dupe PRESET="My Preset"`\</ib:inline-code\> -- similar to Find panel.
    - \<ib:inline-code\>`Select DUPES`\</ib:inline-code\> -- Same as the panel's Select button, allowing you to set a hotkey or use it with the panel hidden.

------------------------------------------------------------------------

Next: [synchronize](/Manual/release_history/opus13_detailed/synchronize.md)
