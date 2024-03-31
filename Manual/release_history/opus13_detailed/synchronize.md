### Directory Opus 13 - Detailed release notes

# Synchronize

- Similar to Find panel (see above for detail):
  - Improved UI.
  - Reset menu.
  - Presets.
  - Exclude folders by path, wildcard or hidden/system attributes.
  - "Automatically shrink" moved to Shrink button context menu.
- Miscellaneous:
  - Performance improvements when comparing a large number of files.
  - New option, "Synchronize everything (including hidden files)": Turns on "Show everything" mode to ensure nothing is missed due to filters when synching.
  - New "Size (smaller)" and "Size (larger)" comparison modes.
  - Commands:
    - `Find SYNC` -- Triggers a synchronize comparison without opening the panel:
      - `Copy SYNC` -- Perform the actual data synchronization after the comparison.
      - `Set CLEARSYNC` -- Exit "sync mode" when finished.
    - `Find SYNC RUNINPANEL` lets a single command configure the panel and then start the operation.
    - `Find SYNC COMPARE=smaller`
    - `Find SYNC COMPARE=larger`
    - `Find SYNC PRESET="My Preset" NOAUTORUN` -- Similar to Find panel. Use !list as preset name to generate a list of presets.
    - `Set Utility=Sync PRESET="My Preset"` -- Similar to Find panel.

------------------------------------------------------------------------

Next: [Other Utility Panels](/Manual/release_history/opus13_detailed/other_util.md)
