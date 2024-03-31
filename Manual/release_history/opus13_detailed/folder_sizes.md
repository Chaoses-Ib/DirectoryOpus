### Directory Opus 13 - Detailed release notes

# Folder Sizes

- General:
  - (Configured via Preferences / Folders / Folder Sizes.)
  - Per-folder overrides to size calculation can now be specified here, instead of being tied to Folder Formats.
  - New option, "Update folder sizes after file operations":
    - When on, actions like dragging a file into a folder will update the folder's displayed size afterwards.
    - Limited to local and removable disks only. Network drives, FTP sites, and archives would be too slow, as they can't use indexing.
    - Sizes will only be refreshed if they were already displayed and calculated.
  - Added option to clear cached folder sizes when going back or forward through a tab's navigation history.
- Everything instant calculation:
  - If you aren't familiar with Voidtools Everything, see the separate section for it, earlier in these release notes.
  - If Everything (1.4.1 or later) is installed, Opus can use it to calculate folder sizes on NTFS drives.
  - For drives indexed by Everything, folder-size calculation is essentially instant.
  - You can configure Opus to perform automatic folder-size calculation when it's instant and avoid it when it will be slow.
  - Works with folder sizes displayed in tooltips as well as in the file display itself.
  - When returning to a folder via a tab's navigation history, if a sub-folder's size came from Everything before then it will be refreshed automatically, using Everything.
  - Caveat 1: The "Size on disk" column will be less accurate for folders when Everything. That column reports the actual space a file uses, which is sometimes larger (due to padding) or smaller (with filesystem compression) than the data inside it. Since Everything doesn't index the information, it will be approximated using the drive's sector size.
  - Caveat 2: Everything's "index attributes" option should be turned on for accurate calculation of folder sizes when junctions, softlinks, etc. are involved.
  - *Command:* `GetSizes EVERYTHING` allows Preferences to be overridden.
- Junctions and links:
  - (Configured via Preferences / Folders / Folder Sizes / Junctions and Links.)
  - You can now configure whether Opus skips or includes junctions, softlinks, etc. when calculating folder sizes and folder counts.

------------------------------------------------------------------------

Next: [Status Bar](/Manual/release_history/opus13_detailed/status_bar.md)
