##### Directory Opus 13 - Detailed release notes

# File Types

- General:
  - Improved UI.
  - Search field under the file type list, for quickly finding matching types and groups.
  - Added "Library Item" type, for items in libraries.
  - Added "Flat View Item" type, for items in sub-folders when using Flat View or Expandable Folders. Includes context menu items to open the parent folder directly or in a new tab.
  - Added "No filename extension" file type. Lets you configure actions and context menus for files with no suffix (e.g. "README").
  - File Type editor's extension list has "edit as text" option for easier mass-editing or copy & paste of whole lists.
  - The File Type action editor now allows the script language to be selected from a dropdown when in script mode (like the main button editor). Manual adding of a `@script` line is no longer required.
  - You can now reset the context menus of various file-types by right-clicking on the tab in the file-type editor (e.g. on the Context Menu or Drop Menu tab for "All files & folders").
  - The `grp:` pattern-matching syntax for matching file-type groups now lets you use the English group names in all languages (for easier command sharing) and always ignores diacritics when looking for a matching group name.
- Info tips:
  - Thumbnails in info tips now allow text on lower lines to flow under them.
  - Info tips can now have tables with properly aligned columns:
    - Use `\<tab>` to mark the end of each column (backslash followed by a tab).
    - Use multiple `\` before the `<tab>` to increase the gap between columns.
    - Use a `\` at the end of the line to mark the end of a table. The next line can then use columns with independent alignments.
    - A new table can also inherit some column widths from the previous one without inheriting all of them:
      - `\\` at the end of the line would inherit the first column's width, but reset the other columns.
      - `\\\` at the end of the line would inherit the first and second columns' widths, and so on.
  - Info tips (and similar tile definitions) can use the Evaluator:
    - `{!=<bool expression>=}text to show{!}` -- Displays "text to show" if the bool expression is true.
    - `{=<calculation>=}` -- Inserts the calculated value.
    - *Example 1:* `{=picwidth * picheight=} total pixels.`
    - *Example 2:* `{=picwidth > 2048 ? "HighRes" : "LowRes"=}`
  - Improved default info tips for file type groups, especially Movies. (If updating: Settings \> File Types, expand File Type Groups, right-click each group and choose Reset to Defaults.)

------------------------------------------------------------------------

Next: [setattr](/Manual/release_history/opus13_detailed/setattr.md)
