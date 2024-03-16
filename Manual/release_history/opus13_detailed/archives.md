##### Directory Opus 13 - Detailed release notes

# Archives

- Performance improvements when adding multiple items to separate archives as a batch, and support for doing so with non-Zip archives.
- The Archives plugin (used for everything except Zip) now handles the rare situation of archives containing multiple files where some of the files do not have names. The unnamed files will be given arbitrary names, while previously the archive would have been rejected as invalid.
- The Archives plugin now lets you put archives into read-only mode like the internal Zip support.
- When dragging out of a read-only archive (internal Zip or Archives plugin), the drag is restricted to Copy mode so you don't have to hold <kbd>Ctrl</kbd> to avoid trying to Move (which would fail) if you've configured drag & drop to always Move by default.
- Added an option to the "Add to Archive" dialog to "Remove sub-folder", which gives the same behaviour as the \<ib:inline-code\>`Copy ARCHIVE`\</ib:inline-code\> command.
- Commands:
  - Added "nokeepfolder" and "keepfolder" arguments for \<ib:inline-code\>`Copy ADDTOARCHIVE`\</ib:inline-code\> command.
  - The \<ib:inline-code\>`Copy ARCHIVE`\</ib:inline-code\> command now allows archiver-specific parameters to be provided on the command line in the same way as the ADDTOARCHIVE command does. For example, \<ib:inline-code\>`Copy ARCHIVE=.zip,fullpaths,comp:best`\</ib:inline-code\>
  - Added new "comp:" and "enhanced" args for Zip archiver parameters. "comp:" can take a keyword (store, fastest, fast, normal, good, best) or a number from 0 to 19. Numbers 10 and above enable enhanced compression; otherwise the "enhanced" or "noenhanced" args can also be used to override the default.

------------------------------------------------------------------------

Next: [Cloud Storage](/Manual/release_history/opus13_detailed/cloud_storage.md)
