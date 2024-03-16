# Counting Files

The way file systems work is that you can only find out how many files a folder (and its sub-folders) contain by reading the folder contents and counting the files. Unfortunately we need to do this if we want to provide an accurate progress indication when copying folders. You might select a single folder that contains 10,000 files but unless Opus had counted its contents it would only see it as a single item.

- **Count files in folders before copying**: This option lets you control whether Opus counts files in folders before copying or not. Counting files can slow down the copy operation slightly, depending on the number of files involved and what drives you are copying from. You can choose to enable counting for only some drive types, all drives or none.
- **Count files in folders before deleting**: Similar to the option above, this controls whether Opus counts files in folders before deleting them. This only applies when not deleting to the recycle bin, as Windows displays its own progress dialog for recycle bin deletes.
- **Use Everything to count files where possible**: If [Everything by Voidtools](https://voidtools.com) is installed, Opus can leverage its index to calculate folder sizes much faster than normal.
  - **Count automatically even if automatic counting is otherwise disabled**: Even if the two *Count* options on this page are turned off, Opus will still count folder sizes if Everything is installed and the folder in question is indexed.
