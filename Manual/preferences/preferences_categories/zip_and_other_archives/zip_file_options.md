# Zip Files

Support for zip files is built-in to Opus, so options affecting zip files are found on this page rather than on the [Archive Plugins](archive_and_vfs_plugins.md) page.

- **Enable internal Opus Zip support**: Turn this on to enable Zip file support in Opus. If this is turned off then the built-in zip support is disabled completely; Opus would not be able to handle zip files unless a third-party plugin were installed to do so.
- **Ask for encryption/compression settings when copying into Zip files**: If you copy files to an existing zip archive, Opus will prompt you for encryption and compression settings on the fly.
- **Use temporary file when copying to Zip files**: If you add files to an existing archive, Opus makes a temporary copy of the zip file before modifying it. This is safer as if something goes wrong (power failure, etc) the contents of the original zip file will be unaffected. However it can slow down the process of adding files to archives.
- **Use temporary folder when copying to Zip files on removable drives**: Normally when copying to zip files on a removable drive (e.g. a USB drive) Opus will first write the archive to the system temporary folder, and then copy it to the destination. Turn this option off if you want to write data to removable drives directly.
- **Set archive date to date of newest file within it**: If this is turned on, the "last modified" timestamp of the zip file will be automatically set to the time of the newest (most recent) file within the archive. The timestamp is updated whenever files are added to or removed from the archive.

##### Compression settings

- **Compression level**: This lets you set the default compression level when adding files to zip files. If you are using the [Add to Archive](/Manual/file_operations/creating_archives/RAEDME.md) dialog you can override this at the time. There are six compression levels available, ranging from *Store* (which does no compression at all and so is the fastest) to *Best* (which produces the highest level of compression but takes longer to archive).
- **Enhanced compression level**: This activates an [enhanced compression algorithm](http://en.wikipedia.org/wiki/DEFLATE#Deflate64.2FEnhanced_Deflate) that may not be backwards compatible with some zip tools - if you're sending zip files to other people you should make sure they can decompress such archives.

##### File extensions

- **Zip file extensions**: This lets you specify the file extensions that Opus will treat as Zip files. Many common file formats are actually zip files "in disguise", for example **[.jar](http://en.wikipedia.org/wiki/JAR_file)** files are readable with Zip tools.
- **Hide extensions from folder tree**: This option is used to specify which file extensions (from the list above) are not to be displayed in the tree. If you turn on the option in [Folder Tree / Contents](../folder_tree/contents.md) to display archives in the tree, this lets you stop certain zip formats from appearing there. For example, **.exe** files can be treated as zip files if they are self-extracting archives, but you probably don't want every **.exe** file on your machine appearing in the folder tree.
