##### Directory Opus 13 - Detailed release notes

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
    - \<ib:inline-code\>`Find SYNC`\</ib:inline-code\> -- Triggers a synchronize comparison without opening the panel:
      - \<ib:inline-code\>`Copy SYNC`\</ib:inline-code\> -- Perform the actual data synchronization after the comparison.
      - \<ib:inline-code\>`Set CLEARSYNC`\</ib:inline-code\> -- Exit "sync mode" when finished.
    - \<ib:inline-code\>`Find SYNC RUNINPANEL`\</ib:inline-code\> lets a single command configure the panel and then start the operation.
    - \<ib:inline-code\>`Find SYNC COMPARE=smaller`\</ib:inline-code\>
    - \<ib:inline-code\>`Find SYNC COMPARE=larger`\</ib:inline-code\>
    - \<ib:inline-code\>`Find SYNC PRESET="My Preset" NOAUTORUN`\</ib:inline-code\> -- Similar to Find panel. Use !list as preset name to generate a list of presets.
    - \<ib:inline-code\>`Set Utility=Sync PRESET="My Preset"`\</ib:inline-code\> -- Similar to Find panel.

------------------------------------------------------------------------

Next: [Other Utility Panels](/Manual/release_history/opus13_detailed/other_util.md)
