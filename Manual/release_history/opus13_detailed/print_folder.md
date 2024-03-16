##### Directory Opus 13 - Detailed release notes

# Print / Export Folder Listing

- UI now has a presets system, allowing you to save and load named configurations for future use.
- Added option to auto-size columns. Works for both printing and plain text output. (Hidden for CSV and TSV outputs, which auto-size inherently.)
- Now always uses full dates, never day names for recent dates.
- Moved output format (Comma-Separated CSV, Tab-Separated TSV, Plain text) and encoding options (ANSI, UTF8, UTF8 with BOM) to main dialog.
- Commands:
  - \<ib:inline-code\>`Print FOLDER PRESET="My Preset"`\</ib:inline-code\>
  - \<ib:inline-code\>`Print FOLDER PRESET="!reset"`\</ib:inline-code\> -- Opens UI with default settings.
  - \<ib:inline-code\>`Print FOLDER AUTOSIZECOLUMNS=yes`\</ib:inline-code\>
  - \<ib:inline-code\>`Print FOLDER KEYWORDS`\</ib:inline-code\> -- Uses unique column keywords for headings, instead of (not always unique) friendly names. Intended for output that will be processed by a tool.

------------------------------------------------------------------------

Next: [Split / Join](/Manual/release_history/opus13_detailed/split_join.md)
