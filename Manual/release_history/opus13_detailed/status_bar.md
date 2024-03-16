##### Directory Opus 13 - Detailed release notes

# Status Bar

- General:
  - If upgrading, you may need to reset Preferences / File Displays / Status Bar to get all new functionality.
- File type summary:
  - Default configuration now includes a compact summary of selected file extensions (or file type groups) with a total count or size for each one.
  - This is handy when using select-all in a large folder, in case any unexpected types are included.
  - Hovering over the summary displays the same information as a pie chart.
  - Clicking the summary displays the pie chart in a dialog, with controls to change what's displayed.
  - See *New status bar codes*, below for more detail.
- Media duration:
  - Default configuration now includes selected and total audio/video duration.
  - Status Bar no longer triggers audio/video duration calculation by default, and instead only displays that information if a column in the file display has already triggered it.
  - You can change this via Preferences / Miscellaneous / Advanced: \[Behavior\] status_metadata_trigger.
- Format lock:
  - By default, the Status Bar's old format lock (padlock icon) is now a more passive "info" icon.
  - Hovering shows information about the current Folder Format, as before, but left-clicking doesn't do anything.
  - Right-clicking opens a menu of options related to folder formats, with the format lock at the top. It can also be accessed via the default toolbars, in the Folder menu.
  - Preferences has an option to make it look and act as it did in previous versions.
- New status bar codes:
  - Evaluator code (discussed in its own section) can be used in the Status Bar between `{=...=}` tags.
    - This allows for more advanced logic and text formatting.
    - The standard status bar codes are available as Evaluator variables (e.g. "tf" for total files), and a "path" variable gives you the current path.
  - `{var:sys:CopySpeed}` displays the total current copy speed.
  - `{sel:namelen}` and `{sel:pathlen}` display the length of the selected file name and full path, respectively.
  - `{ft}` shows the summary of file extensions or types discussed above:
    - Shows counts by default. `{ft:size}` shows size instead of count. {ft:size,count} shows both.
    - Shows all files by default. `{ft:sel}` shows the selected files instead of all files.
    - Buckets by extension by default. `{ft:group}` buckets by file type group instead. For example, .jpg and .psd files would both be in the Images file type group.
    - When bucketing by extension, a few common types are handled specially. For example, .jpg and .jpeg are treated as the same extension.
    - Shows the largest (count or size) items first by default. `{ft:asc}` shows the smallest items first instead.
    - When many types are selected, aggregates the smaller ones into a single item like "3 more". `{ft:only}` hides the aggregate item.
    - Shows up to three items (plus the aggregate) by default. `{ft:5}` increases it to five. `{ft:-1}` shows all items, no matter how many.
    - `{ft:0}` shows a single item with a count of distinct extensions.
    - `{ft:frame}` draws a frame around each item, instead of drawing them as normal status bar text.

------------------------------------------------------------------------

Next: [rename](/Manual/release_history/opus13_detailed/rename.md)
