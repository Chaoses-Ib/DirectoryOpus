# Zip Files

Support for Zip files is built-in to Opus, and so options affecting Zip files are found on this page rather than on the [Archive Plugins](archive_and_vfs_plugins.md) page.

- **Enable internal Opus Zip support**: Turn this on to enable Zip file support in Opus. If this is turned off then the built-in Zip support is disabled completely; Opus would not be able to handle Zip files unless a third-party plugin were installed to do so.
- **Ask for encryption/compression settings when copying into Zip files**: If this is turned on and you copy files to an existing Zip archive, Opus will prompt you for encryption and compression settings on the fly.
- **Use temporary file when copying to Zip files**: If this is turned on and you add files to an existing Zip archive, Opus makes a temporary copy of the Zip file before modifying it. This is safer as if something goes wrong (power failure, etc) the contents of the original Zip file will be unaffected. However it can slow down the process of adding files to archives.
- **Use temporary folder when copying to Zip files on removable drives**: Normally when copying to Zip files on a removable drive (e.g. a USB drive) Opus will first write the archive to the system temporary folder, and then copy it to the destination. Turn this option off if you want to write data to removable drives directly.
- **Set archive date to date of newest file within it**: If this is turned on, the "last modified" timestamp of the Zip archive will be automatically set to the time of the newest (most recent) file within the archive. The timestamp is updated whenever files are added to or removed from the archive.
- **Compression level**: This lets you set the default compression level when adding files to Zip files. If you are using the [Add to Archive](/Manual/file_operations/creating_archives/RAEDME.md) dialog you can override this at the time. There are six compression levels available, ranging from *Store* (which does no compression at all and so is the fastest) to *Best* (which produces the highest level of compression but takes longer to archive).
  - **Enhanced compression level**: This activates an [enhanced compression algorithm](http://en.wikipedia.org/wiki/DEFLATE#Deflate64.2FEnhanced_Deflate) that may not be backwards compatible with some Zip tools - if you are sending Zip files to other people you should make sure they can decompress such archives.

- **Zip Extensions**: This lets you specify the file extensions that Opus will treat as Zip files. Many common file formats are actually Zip files "in disguise", for example **[.jar](http://en.wikipedia.org/wiki/JAR_file)** files are readable with Zip tools.

![](/Manual/images/media/zip_extensions.png)

This is specified as a semicolon-separated list of file extensions.  
\* **Hide from Tree**: This option is used to specify which file extensions (from the Zip Extensions list) are not to be displayed in the tree. If you turn on the option in [Folder Tree / Contents](../folder_tree/folder_tree_contents.md) to display archives in the tree, this lets you stop certain Zip formats from appearing there. For example, **.exe** files can be treated as Zip files if they are self-extracting archives, but you probably don't want every **.exe** file on your machine appearing in the folder tree.

- **Packed column**: When you are viewing the contents of a Zip file in a file display you can add several Zip-specific columns to the file display, including the **Packed** column. This column displays the compressed or "packed" size of files within the archive. You can use this option to change the units the **Packed** column displays file sizes in (*bytes*, *KB *or *auto* - which means Opus chooses the most appropriate unit automatically).
