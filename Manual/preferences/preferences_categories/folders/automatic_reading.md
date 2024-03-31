# Automatic Reading

The options on this page allow you to prevent Opus from automatically loading certain types of folders (e.g. when a Lister opens, it will normally automatically load a folder).

This can be very useful if you have Opus set to re-open the last location when it runs, or to open a specific Lister layout that displays network drives or another slow drive type. It stops Opus from attempting to automatically read the specified types of folders when a Lister first opens. For example, you could have a layout that reads a network drive - with this option on, opening that layout would not automatically connect to the network drive, but instead you will be prompted to click a link in order to read the folder.

- **CD-ROM/DVDs**: Folders located on CDs and DVDs will not be automatically loaded.
- **Drives that are powered down**: Hard drives that are in sleep mode (have powered down) will not be automatically loaded. This stops Opus from waking them up until you manually read the folder.
- **FTP sites**: Connections to FTP sites will not be automatically reconnected until you manually load the folder.
- **Network drives**: Folders located on network drives will not be automatically loaded.
- **Removable devices**: This applies to things like USB thumb drives and some (but not all) external hard drives.
- **Search results**: If you close a Lister with the results of a quick search shown, this would stop the search being automatically re-run when it reopens.
- **Zip files and other archives**: Irrespective of the device they reside on, archives will not be automatically loaded.
- **All other drive types**: Applies to everything not listed separately.

For each folder type, you can select from three options:

- **Load normally**: Loads the folder.
- **Prevent loading**: Prevents automatic loading of the folder. A message will be displayed at the top of the file display with a link you can click to trigger the read.
- **Load on tab activation**: Prevents the loading initially if the tab isn't the active one, but will load the folder automatically the first time the tab is activated.

### Specific folders

At the bottom of the page is a list that lets you apply the same options to specific folders or wildcard patterns. E.g. you could have network drives set to generally not load automatically using the option above, but override it for one specific server by adding the path to the Folders list.
