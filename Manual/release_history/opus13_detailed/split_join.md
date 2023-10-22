##### Directory Opus 13 - Detailed release notes

# Split / Join

- Improved UI.
- Added option for Base64 encoding (with or without splitting).
- When splitting, the start of the file's data is displayed to help choose the most appropriate splitting method.
- Can now split text files on line boundaries. In this mode, a line count per file is used instead of a byte count.
- When splitting, handles ANSI / UTF8 / UTF16 transparently.
- When joining, a new *Normalize Text Encoding* mode allows you to join text files in different encodings.
  - If all files use the same encoding, it is left as-is (other than removing extra BOMs).
  - With multiple encodings, the output is converted to UTF-8.
- Option to replicate first line of original file in all output files (e.g. for CSV data).
- Commands:
  - \`Split LINES SIZE=n\` -- Split file into *n* line chunks.
  - \`Join CONVERT\` -- Specify encoding/conversion mode, like drop-down in the UI.

------------------------------------------------------------------------

Next: [archives](/Manual/release_history/opus13_detailed/archives.md)
