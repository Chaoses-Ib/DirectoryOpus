##### Directory Opus 13 - Detailed release notes

# File & Folder Labels

- Improved the implementation of labels which pin a file or folder to the top of its parent:
  - Previously, the pinned item did not move to the top until it became visible. It now happens as soon as the folder loads, even if the item is initially out of view.
  - Caveat: Items pinned by older versions need to be scrolled into view once for the new behavior to be applied.

- The order labels are shown in menus can now be changed on the Preferences / File and Folder Labels / Labels page.
- Where Preferences shows label lists, multi-selecting some and pushing Space now toggles all of them instead of just the one with focus.
- *Command:* \`Properties SETLABEL=!compact\` -- Generates a compact list of label buttons. Each is only icon (if there is an icon or icon-tint color) or the characters "Aa" to show the label's colors. Hovering over a button reveals its full name.

------------------------------------------------------------------------

Next: [aliases](/Manual/release_history/opus13_detailed/aliases.md)
